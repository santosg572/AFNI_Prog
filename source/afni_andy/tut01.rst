AFNI Tutorial #1: Downloading the Data
=====================================

**Overview**

For this course we will be analyzing an fMRI dataset that used the Flanker task. The dataset can be found here on the OpenNeuro website, an online repository for neuroimaging data.
../../_images/OpenNeuro_Flanker.png

The OpenNeuro page for the Flanker dataset includes a Dataset File Tree, which includes the folders anat (containing the anatomical image) and func (containing the functional images and onset times for each run). There are additional files containing subject data such as sex and age (participants.tsv) and scanning parameters (task-flanker_bold.json). These data are in a format called BIDS - Brain Imaging Data Structure. A standardized directory tree such as this makes scripting much easier, as we will see in a later tutorial.

Download the dataset by clicking on the “Download” button at the top of the page. The dataset is about 2 Gigabytes, and comes in a zipped folder. Extract it by double-clicking on the folder.
../../_images/OpenNeuro_DownloadButton.png

After you have downloaded and unzipped the dataset, click on the Next button for an overview of the experimental task used in this study.

**Alternative Download Options**

If the download button doesn’t work, try using the Amazon Web Services (AWS) option. Go to this page and download the appropriate AWS client for your operating system. Once it has been installed, open a Terminal, navigate to the Desktop, and type the following:

.. code:: Bash

   aws s3 sync --no-sign-request s3://openneuro.org/ds000102 ds000102-download/

It should take about half an hour to download.

**Video**

For a video tutorial of how to download the data, click here.


