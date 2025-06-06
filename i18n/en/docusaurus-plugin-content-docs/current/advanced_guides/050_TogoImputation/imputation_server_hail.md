---
id: imputation_server_hail
title: "Tutorial 3 - PRS calculation with hail"
---

<img
  src='https://github.com/genome-analytics-japan/imputation-server-logo/blob/main/logo_color.png?raw=true'
  alt=''
  style={{width:'200px'}}
/>

This Tutorial 3 describes how to set up an environment for analysing the results of an imputation server's imputation results in [&#x1f517;hail](https://hail.is)  to analyse the results of an imputation server.

## Connecting to NIG Guacamole desktop environment {#connect-nig-guacamole}

You need to sign in to NIG Guacamole desktop environment via VPN first.

Next, please launch the terminal from the "Activities" in the Guacamole desktop environment.

You need to run the following tutorial in the terminal that you launched above.

## Preparations

### Installing miniconda

If you can already use the conda command, skip this section and proceed to `Creating a conda environment using conda-forge`.
If you cannot use the conda command, run the following commands to install miniconda.

```
$ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
$ chmod 755 ./Miniconda3-latest-Linux-x86_64.sh
$ ./Miniconda3-latest-Linux-x86_64.sh
```

After running the above commands, the terminal shows the following message continuing to the license terms.

```
Welcome to Miniconda3 py312_24.3.0-0

In order to continue the installation process, please review the license
agreement.
Please, press ENTER to continue
>>>
```

Pressing the ENTER key displays the text of the end user licence agreement.
By pressing the SPACE key several times, the text scrolls and a confirmation question appears asking whether you accept the following licence terms.

```
7. Intellectual Property Notice. You acknowledge that, as between You and
Anaconda, Anaconda owns all right, title, and interest, including all
intellectual property rights, in and to Miniconda(R) and, with respect to
third-party products distributed with or through Miniconda(R), the applicable
third-party licensors own all right, title and interest, including all
intellectual property rights, in and to such products.


Do you accept the license terms? [yes|no]
>>>
```

Type `yes` and press ENTER to continue.

Next, you will see `Miniconda3 will now be installed into this location: /home/<username>/miniconda3:`.
If the installation location is OK, press the ENTER key.
If you want to install in a different location, specify a different path.
You will then be asked `Do you wish to update your shell profile to automatically initialise conda? [yes|no]`.
Type `yes` or `no` and press ENTER to proceed. (We recommend typing `no`.)

Run the following command to set PATH for to the conda command.

```
$ PATH=$PATH:~/miniconda3/bin
```

Then, once sign out and re-enter to the terminal.

Finally, check that the conda command is available by running the following command.

```
$ which conda
$ conda --version
```

### Creating a conda environment using conda-forge {#create-conda-env}

Next, run the following command.
Here, we introduce a way to use a package repository called `conda-forge`, which does not require a paid license.

```
$ conda create -c conda-forge -n hail-python37-openjdk8 python=3.7 openjdk=8
```

## Installing Jupyter and hail

Then, run the following commands to install `hail` and `jupyter`.

```
$ conda activate hail-python37-openjdk8
$ pip install hail
$ pip install jupyter
```

The following commands are also required. This means that 48G of memory is allocated for hail.
If the memory is not enough, hail will output an out-of-memory error and the calculation will not be able to resume.

```
export PYSPARK_SUBMIT_ARGS='--driver-memory 48g --executor-memory 48g pyspark-shell'
```

## Launching Jupyter Notebook

Next, launch Jupyter Notebook with the following command.

```
$ jupyter notebook --notebook-dir=~/imputation-server-test &
```

When you run this command, a new tab will open in Firefox, and the Jupyter Notebook will be displayed in the tab.

Press the `New` button on the right side of the screen, select `Python 3 (ipykernel)`, and click on it.
This will create a new Firefox tab, and the Jupyter Notebook will be displayed.

## Checking Hail startup
Create a new Jupyter Notebook, enter the following in the first cell and run it.

```
import hail as hl
```

Enter the following in the next cell and run it.

```
hl.init()
```

Check that there are no errors.

## Notebook for performing PRS calculations using the imputation results as input to hail {#notebook-prs-calculation-hail-imputation}

Next, use hail in Jupyter according to the following notebook:

&#x1f517;https://nbviewer.org/github/ddbj/imputation-server-wf/blob/main/Notebooks/hail-prs-tutorial.ipynb

When you finish your work, please close the browser tab displaying Guacamole.

## Supplementary information

To open the notebook tutorial in the Guacamole desktop environment, 
type "DDBJ imputation" in the web search field of Firefox and perform a search.
Among the search results, there is "TogoImputation (beta) Tutorial 3 - PRS calculation with hail".
There is a link to https://nbviewer.org/github/ddbj/imputation-server-wf/blob/main/Notebooks/hail-prs-tutorial.ipynb at the bottom of that webpage.

Once you open https://nbviewer.org/github/ddbj/imputation-server-wf/blob/main/Notebooks/hail-prs-tutorial.ipynb from Firefox in the Guacamole desktop environment, 
you can proceed with the tutorial by copying and pasting.
