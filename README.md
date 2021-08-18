# HDDM Tutorial: Carney Computational Modeling Workshop

The HDDM GitHub page can be found [here](https://github.com/hddm-devs/hddm).  
The [online documentation](http://ski.clps.brown.edu/hddm_docs/) is as good as a textbook.  
If you need help, the [mailing list](https://groups.google.com/group/hddm-users/) is very responsive.

Here are some example of studies I've run using HDDM (with scripts):  
Manuscript: https://www.nature.com/articles/s41598-019-48050-2  
Data and scripts: https://osf.io/8ka47/

# Playing around with HDDM on the cloud

Here's how to set up Google Colab for the HDDM tutorial.

1. While logged into a Google account, visit the following website to [set up a Google Colab account](https://colab.research.google.com/). That is pretty much an automatic process once you visit the link.

2. If you're in my workshop group, I've prepared some materials that we'll be going through, including some sample data and scripts. Download the files in this GitHub repository, then upload them to your Google Drive account (in the top level of your Drive, please).
  - If you're familiar with GitHub already, the easiest method is to fork/clone this repo.
  - For those of you who are new to GitHub, just click on the "Code" button towards the top of the page, then click "Download ZIP".

3. Keep reading, but don't move on to step 4. *Right before* the HDDM workshop begins (regardless of whose group you're in), run a notebook code block containing the commands in step 4. This takes a few minutes. If you close out of your Colab session, you'll have to reinstall these packages, so there's no sense in doing it ahead of time.

4. Install the packages. Note that this installs the packages to the notebook in the cloud – nothing is downloaded/installed to your computer. But, it does take a few minutes (or longer, depending on your internet connection).
  - If you're in my workshop group, the following commands are already part of the notebook we'll be working from. Just go ahead and run this code.
  - If you're not in my workshop group, you can use the Google Colab interface to create a new Python notebook. Instructions are below.

In the first cell, copy/paste/run the following code:
```
!pip install pymc
!pip install kabuki
!pip install hddm
```

Then, give your notebook permission to access your Google Drive. You can do this in a new code block by copy/pasting and then running the following code:
```
from google.colab import drive
drive.mount('/content/drive')
```

The output will give you a URL that you click on to give Colab access to your Drive. After this is done successfully, you can access any files you have on your Google Drive using filepaths that look like this:

`'/content/drive/My Drive/HDDM Tutorial/JustCon3_ddm.csv'`

...and that's pretty much it! From there, you can use the Google Colab notebook just like you'd use a Jupyter notebook. This should mean that you're able to follow along without any difficulty.

# Installing HDDM on your personal computer

If you just want to play around with HDDM for the workshop, I'd ***strongly*** recommend using Google Colab. Getting HDDM to install locally has proven to be somewhat challenging in the past, but the mailing list has found great solutions to common problems.

1. Download and install [Anaconda](https://www.anaconda.com/products/individual).

2. If you're on macOS, install the command line tools. You can skip this step if you already have XCode installed.
  - Open Terminal and type: `xcode-select --install`
  - Use graphical installer to finish installation

3. Create a conda virtual environment.
  - On macOS or Linux, open the Terminal and type: `conda create -n pyHDDM python=3.6`
  - On Windows, you'll use **Anaconda Prompt**, which emulates a terminal window.

4. Learn some basic conda commands.
  - Activate: `conda activate pyHDDM`
  - Deactivate: `conda deactivate`
  - If you screw up your virtual environment, you can delete it and start over! `conda remove -n pyHDDM --all`

5. Install packages.
  - macOS: My exact install sequence is included below, [adapted closely from here](https://groups.google.com/g/hddm-users/c/bdQXewfUzLs/m/iVasvmW3BwAJ).
  - Windows 10: https://groups.google.com/g/hddm-users/c/RpS9O9O7Fwc/m/P8ZyCpiqAwAJ
  - I'm told that installation on Linux is not so difficult, but don't have any personal experience one way or another.

Jae's macOS install routine:
```
conda activate pyHDDM
conda install conda-build
conda install pymc=2.3.8 -c conda-forge
conda install pandas patsy
export MACOSX_DEPLOYMENT_TARGET=10.11
pip install cython
pip install hddm
conda install jupyter
```
