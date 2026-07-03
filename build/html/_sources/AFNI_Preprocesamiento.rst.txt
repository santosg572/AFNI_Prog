AFNI Preprocesamiento, QC y Análisis Seed‐based en Resting State
================================================================

https://github.com/neuropsytox/Documentation/wiki/AFNI-Preprocesamiento,-QC-y-An%C3%A1lisis-Seed%E2%80%90based-en-Resting-State

**Primero correr cada sujeto en Freesurfer**

Se corre un N4 para mejorar el contraste.

.. code:: Bash

   fsl_sub -N N4afni N4BiasFieldCorrection -d 3 -i sub-112_T1w.nii -o sub-112_T1w_N4.nii

Ejemplo de script en Cluster C13:

.. code:: Bash

   module load freesurfer/7.4.1 fsl/6.0.7.4 afni/25.2.13 ANTs/2.4.4

   export data=/misc/tezca/egarza/afni_practice2025/raw20/

   for suj in sub-020 sub-021 sub-022 sub-023 sub-024 sub-025 sub-025 sub-026 sub-027 sub-028 sub-029 sub-030 sub-031 sub-032 sub-033 sub-034 sub-035 sub-036 sub-038 sub-091 sub-093;
   do
      fsl_sub -N N4afni${suj} N4BiasFieldCorrection -d 3 -i $data/$suj/anat/${suj}_T1w.nii.gz -o $data/$suj/anat/${suj}_T1w_N4.nii.gz
   done

   ./bash 01_runN4

**Cargar el modulo Freesurfer**

.. code:: Bash

   module load freesurfer/7.4.1

   export SUBJECTS_DIR=/path/to/data/derivatives/freesurfer

   fsl_sub -N sub-112 recon-all -subject sub-112 -i /path/sub-112_T1w_N4.nii -all

**Ejemplo de script en Cluster C13:**

.. code:: Bash

   module load freesurfer/7.4.1 fsl/6.0.7.4 afni/25.2.13 ANTs/2.4.4

   export SUBJECTS_DIR=/misc/tezca/egarza/afni_practice2025/derivatives_raw20/raw20fs
   export data=/misc/tezca/egarza/afni_practice2025/raw20

   for suj in sub-020 sub-021 sub-022 sub-023 sub-024 sub-025 sub-025 sub-026 sub-027       \
      sub-028 sub-029 sub-030 sub-031 sub-032 sub-033 sub-034 sub-035 sub-036 sub-038 sub-091 sub-093;
   do
      fsl_sub -N fs${suj} recon-all -all -subject ${suj}	\
          -i $data/$suj/anat/${suj}_T1w_N4.nii.gz
   done
 
   ./bash 02_runfs

**Convertir de Freesurfer a SUMA**

.. code:: Bash

   @SUMA_Make_Spec_FS -sid sub-20 -NIFTI

**Ejemplo de script en Cluster C13:**

.. code:: Bash

   #!/bin/bash

   module load freesurfer/7.4.1 fsl/6.0.7.4 afni/25.2.13 ANTs/2.4.4

   export data=/misc/tezca/egarza/afni_practice2025/derivatives_raw20/raw20fs

   for suj in sub-020 sub-021 sub-022 sub-023 sub-024 sub-025  \
      sub-025 sub-026 sub-027 sub-028 sub-029 sub-030 sub-031 sub-032 \
      sub-033 sub-034 sub-035 sub-036 sub-038 sub-091 sub-093;

   do
      cd ${data}/${suj}
      fsl_sub -N FS2SUMA_$suj @SUMA_Make_Spec_FS -sid ${suj} -NIFTI
   done

   ./bash 03_runFS2SUMA

**Revisa los resultados de Freesurfer con SUMA**

Dentro del folder de SUMA donde convertiste todo de Freesurfer>

.. code:: Bash

   afni -niml & suma -spec std.141.sub-112_both.spec -sv sub-112_SurfVolcopy.nii

Me salía un error por usar AFNI viejo del cluster C13. Tuve que convertir el NIFTI para que no tuviera un 
problema de header.

.. code:: Bash

   3drefit -newid sub-111_SurfVol.nii

o

.. code:: Bash

   3dcopy sub-112_SurfVol.nii sub-112_SurfVolcopy.nii

**Correr un SSWarper**

Antes de correr afni_proc.py correr este SSWarper para obtener transformaciones y cerebro T1w sin craneo. Se 
corre con el comando siguiente, se puede hacer como script.

.. code:: Bash

   tcsh SSwarper

Primero creo un folder dentro de **derivatives_raw20** llamado **afniproc**. Dentro, creo un folder llamado 
**AFNI_01_SSWarp**

Script

.. code:: Bash

   #!/bin/bash

   module load freesurfer/7.4.1 fsl/6.0.7.4 afni/25.2.13 ANTs/2.4.4

   export data=/misc/tezca/egarza/afni_practice2025/raw20
   export derivatives=/tezca/egarza/afni_practice2025/derivatives_raw20
   export output=/misc/tezca/egarza/afni_practice2025/derivatives_raw20/afniproc/AFNI_01_SSWarp

   for suj in sub-021 sub-022 sub-023 sub-024 sub-025  \
     sub-025 sub-026 sub-027 sub-028 sub-029 sub-030 sub-031 sub-032 \
     sub-033 sub-034 sub-035 sub-036 sub-038 sub-091;
   do

     fsl_sub -N SSWarper_${suj} @SSwarper -input ${data}/${suj}/anat/${suj}_T1w_N4.nii.gz	\
                    -subid ${output}/${suj}	\
                    -odir  ${output}/${suj}_anat_warped	\
                    -base  MNI152_2009_template_SSW.nii.gz

   done

   ./bash 04_runSSWarper

Correr AFNI PROC
Al correr afni_proc.py se corre automaticamente el Quality Control.

Se tiene que estar seguro donde estan los archivos, ya sea ponerlos todos en el mismo folder o solo dar los 
paths correctos.

Primero se crea un script. Hay muchos ejemplos en la página de AFNI, este script lo modifiqué de este: 
https://afni.nimh.nih.gov/pub/dist/doc/htmldoc/programs/alpha/afni_proc.py_sphx.html#example-11-resting-state-analysis-now-even-more-modern

Creo un folder dentro de afniproc llamado AFNI_02_rest y copio dentro el siguiente script:

#!/bin/tcsh

#module load freesurfer/7.4.1 fsl/6.0.7.4 afni/25.2.13 ANTs/2.4.4

# --------------------------------------------------
# note fixed top-level directories

set SUMA=/misc/tezca/egarza/afni_practice2025/derivatives_raw20/raw20fs/
set warp=/misc/tezca/egarza/afni_practice2025/derivatives_raw20/afniproc/AFNI_01_SSWarp/
set data_root = /misc/tezca/egarza/afni_practice2025/
set input_root = $data_root/raw20
set output_root = $data_root/derivatives_raw20/afniproc/AFNI_02_rest

set subjects = (sub-021 sub-022 sub-023 sub-024 sub-025 sub-025	\
sub-026 sub-027 sub-028 sub-029 sub-030 sub-031 sub-032	\
sub-033 sub-034 sub-035 sub-036 sub-038 sub-091)

# process all subjects

foreach suj ($subjects)

#sub-022 sub-023 sub-024 sub-025  \
#sub-025 sub-026 sub-027 sub-028 sub-029 sub-030 sub-031 sub-032 \
#sub-033 sub-034 sub-035 sub-036 sub-038 sub-091;

# --------------------------------------------------
   # note input and output directories
   set subj_indir = $input_root/$suj/func
   set subj_outdir = $output_root/$suj

# --------------------------------------------------
   # if output dir exists, this subject has already been processed
   if ( -d $subj_outdir ) then
      echo "** results dir already exists, skipping subject $suj"
      continue
   endif

# --------------------------------------------------
   # otherwise create the output directory, write an afni_proc.py
   # command to it, and fire it up

   mkdir -p $subj_outdir
   cd $subj_outdir

# create a run.afni_proc script in this directory
   cat > run.afni_proc << EOF

afni_proc.py                                                         \
    -subj_id                  ${suj}.rest                             \
    -blocks                   despike tshift align tlrc volreg blur  \
                              mask scale regress                     \
    -radial_correlate_blocks  tcat volreg regress                    \
    -copy_anat                $warp/${suj}_anat_warped/anatSS.${suj}.nii                          \
    -anat_has_skull           no                                     \
    -anat_follower            anat_w_skull anat $warp/${suj}_anat_warped/anatU.${suj}.nii         \
    -anat_follower_ROI        aaseg anat                             \
                              $SUMA/${suj}/SUMA/aparc.a2009s+aseg_REN_all.nii.gz       \
    -anat_follower_ROI        aeseg epi                              \
                              $SUMA/${suj}/SUMA/aparc.a2009s+aseg_REN_all.nii.gz       \
    -anat_follower_ROI        FSvent epi $SUMA/${suj}/SUMA/fs_ap_latvent.nii.gz        \
    -anat_follower_ROI        FSWe epi $SUMA/${suj}/SUMA/fs_ap_wm.nii.gz               \
    -anat_follower_erode      FSvent FSWe                            \
    -dsets                    $subj_indir/${suj}_task-rest_bold.nii.gz                    \
    -align_unifize_epi        local                                  \
    -align_opts_aea           -cost lpc+ZZ                           \
                              -giant_move                            \
                              -check_flip                            \
    -tlrc_base                MNI152_2009_template_SSW.nii.gz        \
    -tlrc_NL_warp                                                    \
    -tlrc_NL_warped_dsets     $warp/${suj}_anat_warped/anatQQ.${suj}.nii 
$warp/${suj}_anat_warped/anatQQ.${suj}.aff12.1D       \
                              $warp/${suj}_anat_warped/anatQQ.${suj}_WARP.nii                     \
    -volreg_align_to          MIN_OUTLIER                            \
    -volreg_align_e2a                                                \
    -volreg_tlrc_warp                                                \
    -mask_epi_anat            yes                                    \
    -blur_size                4                                      \
    -regress_apply_mot_types  demean deriv                           \
    -regress_motion_per_run                                          \
    -regress_anaticor_fast                                           \
    -regress_anaticor_label   FSWe                                   \
    -regress_ROI_PC           FSvent 3                               \
    -regress_ROI_PC_per_run   FSvent                                 \
    -regress_censor_motion    0.2                                    \
    -regress_censor_outliers  0.05                                   \
    -regress_make_corr_vols   aeseg FSvent                           \
    -regress_est_blur_epits                                          \
    -regress_est_blur_errts                                          \
    -html_review_style        pythonic

EOF
# EOF terminates the 'cat > run.afni_proc' command, above
# (it must not be indented in the script)

   # now run the analysis (generate proc and execute)
   tcsh run.afni_proc

# end loop over subjects
end
Después se corre el script así:

tcsh afniproc_raw

Correr Preprocesamiento
Este script crea el script final para correr el preprocesamiento completo

fsl_sub -N sub20afniproc tcsh -xef proc.sub-020.rest |& tee output.proc.sub-020.rest

En forma de script para muchos sujetos:

for suj in sub-021 sub-022 sub-023 sub-024 sub-025 sub-026 sub-027 sub-028 sub-029 sub-030 sub-031 sub-032 
sub-033 sub-034 sub-035 sub-036 sub-038 sub-091; do fsl_sub -N afniproc_$suj tcsh -xef $suj/proc.$suj.rest 
2>&1 | tee $suj/output.proc.$suj.rest; done
Quality Control
Para entender el QC, pueden revisar esta página: 
https://afni.nimh.nih.gov/pub/dist/doc/htmldoc/tutorials/apqc_html/apqc_ex1.html

open_apqc.py -infiles QC_*/index.html
Extracción de GCOR
Corregir Global Signal es aún un gran tema y soy partidario de no hacerlo, pero hay que hacer algo para 
seguir corrigiendo por señales fisiológicas y movimiento. En AFNI recomiendan GCOR. Este se extrae ya de 
afni_proc.py:

grep GCOR sub-*.rest.results/out.ss_review.*.txt  | awk '{print $5}' > GCOR.txt
Generar semilla del PCC
for suj in sub-021 sub-022 sub-023 sub-024 sub-025 sub-026 sub-027  \
sub-028 sub-029 sub-030 sub-031 sub-032 sub-033 sub-034 sub-035 \
sub-036 sub-038 sub-091;do 3dUndump -prefix seeds/${suj}-lh-PCC-BA31  \
-master $suj.rest.results/errts.$suj.rest.fanaticor+tlrc. -srad 5 -xyz lh-PCC-BA31.txt; done
Generar mapa de semilla por sujeto
#!/bin/bash

module load freesurfer/7.4.1 fsl/6.0.7.4 afni/25.2.13 ANTs/2.4.4

export data=/misc/tezca/egarza/afni_practice2025/raw20
export derivatives=/tezca/egarza/afni_practice2025/derivatives_raw20
export output=/misc/tezca/egarza/afni_practice2025/derivatives_raw20/afniproc/AFNI_02_rest

for suj in sub-021 sub-022 sub-023 sub-024 sub-025 sub-026 sub-027  \
sub-028 sub-029 sub-030 sub-031 sub-032 sub-033 sub-034 sub-035 \
sub-036 sub-038 sub-091;

do

fsl_sub -N CORR-PCC-$suj 3dNetCorr -inset $output/${suj}.rest.results/errts.${suj}.rest.fanaticor+tlrc  \
-in_rois seeds/${suj}-lh-PCC-BA31+tlrc  \
-ts_wb_corr -ts_wb_Z -ts_out -ts_indiv -prefix $output/${suj}.rest.results/${suj}.CORR-PCC

done
Generar mapa de conectividad media
Se puede sacar una lista fácilmente:

ls sub-*.rest.results/sub-*.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD

luego copiar esto a un script

touch meanCorr.sh

3dMean -prefix meanCorr sub-021.rest.results/sub-021.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-022.rest.results/sub-022.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-023.rest.results/sub-023.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-024.rest.results/sub-024.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-025.rest.results/sub-025.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-026.rest.results/sub-026.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-027.rest.results/sub-027.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-028.rest.results/sub-028.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-029.rest.results/sub-029.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-030.rest.results/sub-030.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-031.rest.results/sub-031.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-032.rest.results/sub-032.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-033.rest.results/sub-033.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-034.rest.results/sub-034.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-035.rest.results/sub-035.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-036.rest.results/sub-036.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-038.rest.results/sub-038.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD       \
sub-091.rest.results/sub-091.CORR-PCC_000_INDIV/WB_CORR_ROI_001+tlrc.HEAD
bash meanCorr.sh

Al final obtenemos un mapa de la correlación Promedio de los sujetos. Esto solo para fines de visualización.

meanCorr

Análisis
Ya con todos los mapas de correlacion en Z para análisis, se debe escoger el tipo de análisis. Para este 
ejemplo, usaré 3dttest++ ya que es una comparación simple entre grupos.

3dttest++ -prefix stat.ttest                         \
          -AminusB                                     \
          -setA CN                                   \
            sub-021 "sub-021.rest.results/sub-021.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-022 "sub-022.rest.results/sub-022.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-028 "sub-028.rest.results/sub-028.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-029 "sub-029.rest.results/sub-029.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-031 "sub-031.rest.results/sub-031.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-032 "sub-032.rest.results/sub-032.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-033 "sub-033.rest.results/sub-033.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-036 "sub-036.rest.results/sub-036.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-038 "sub-038.rest.results/sub-038.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
          -setB SU                                   \
            sub-023 "sub-023.rest.results/sub-023.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-024 "sub-024.rest.results/sub-024.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-025 "sub-025.rest.results/sub-025.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-026 "sub-026.rest.results/sub-026.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-027 "sub-027.rest.results/sub-027.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-030 "sub-030.rest.results/sub-030.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-034 "sub-034.rest.results/sub-034.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-035 "sub-035.rest.results/sub-035.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-091 "sub-091.rest.results/sub-091.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
bash ttest_2

Al final ya nos da el archivo stat.ttest+tlrc que podemos abrir con AFNI para revisar los resultados.

Con Covariables
Crear lista de sujetos

grep subject sub-*.rest.results/out.ss_review.*.txt  | awk '{print $4}' > subjects.txt
Crear lista de valores GCOR (En este ejemplo usaremos GCOR que es el Global Signal Media de cada sujeto, 
pero puede ser edad o cualquier otra variable)

grep GCOR sub-*.rest.results/out.ss_review.*.txt  | awk '{print $5}' > GCOR.txt
Combinar

paste subjects.txt GCOR.txt > covariates.txt
Hay que editar para agregar los nombres de cada columna

Script de 3dttest++

3dttest++ -prefix stat.covar.ttest                         \
          -AminusB                                     \
          -setA CN                                   \
            sub-021 "sub-021.rest.results/sub-021.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-022 "sub-022.rest.results/sub-022.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-028 "sub-028.rest.results/sub-028.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-029 "sub-029.rest.results/sub-029.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-031 "sub-031.rest.results/sub-031.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-032 "sub-032.rest.results/sub-032.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-033 "sub-033.rest.results/sub-033.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-036 "sub-036.rest.results/sub-036.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-038 "sub-038.rest.results/sub-038.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
          -setB SU                                   \
            sub-023 "sub-023.rest.results/sub-023.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-024 "sub-024.rest.results/sub-024.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-025 "sub-025.rest.results/sub-025.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-026 "sub-026.rest.results/sub-026.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-027 "sub-027.rest.results/sub-027.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-030 "sub-030.rest.results/sub-030.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-034 "sub-034.rest.results/sub-034.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-035 "sub-035.rest.results/sub-035.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            sub-091 "sub-091.rest.results/sub-091.CORR-PCC_000_INDIV/WB_Z_ROI_001+tlrc.HEAD"    \
            -covariates covariates.txt
bash ttest_3

Pages 45
Home
For Newbies
Lab Manual and Code of Conduct
Lab Data Organization
SUDMEX_CONN
Bruker
Acquire rsfMRI Bruker 7T
Acquire T2w in vivo Bruker
Average T1w or T2w repetitions Bruker 7T
Bruker ClinScan 7T Tips
Convert DICOM from Bruker
Download DICOM from Bruker 7T
MINC
Create image from data for QC
Display & Register
AFNI
AFNI Arreglar scripts
AFNI Preprocesamiento y QC en Resting State
AFNI QC Rápido
fMRIprep
fMRIprep preprocessing
DeepLabCut
Lab Methods
Blood Alcohol Concentration (BAC)
Conditioned Place Preference (CPP)
Elevated Plus Maze (EPM)
Outline IA2BC
Intermittent Access Two Bottle Choice (IA2BC)
Fixed Brains for MRI
Novel Object Recognition (NOR)
Aproximaciones sucesivas con morfina
Surgical implantation of Chronic Neural Carbon Fiber Electrodes
DBM
Deformation Based Morphometry MBM.py no atlas
Deformation Based Morphometry MBM.py with atlas
Two Level DBM model in rodents and humans
Axolotl
Create Template brain
FSL
Topup
MRIQC
MRIQC for BIDS
MRIQC Humans
Preprocessing rats
Functional in vivo
Structural in vivo
Preprocessing extras
Defacing 3D anatomical data
Gibbs Rings
BIDS
Dicom to BIDS
Niagara
First steps on Niagara
TIPS
Visualization Resources
Change Extension in Loops
Useful Bash Commands
Loops
Qbatch
Trackvis and Diffusion
XCPEngine
Clone this wiki locally
https://github.com/neuropsytox/Documentation.wiki.git
Footer






