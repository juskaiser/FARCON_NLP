# Intro to Natural Language Processing
## Setup Instructions
Follow the instructions below to get setup for the NLP training session. Use git to download the repository for the session and do a final ```$ git pull``` the day before the training to make sure all the content is up to date. I'll be actively working on the content until close to the day of the training, so make sure to update the day before the training. I'm using Conda to manage and create the python environment in the steps below. For an in-depth explanation of this workflow see the excellent bog post by Tim Hopper, [My Python Environment Workflow with Conda](https://tdhopper.com/blog/2015/Nov/24/my-python-environment-workflow-with-conda/).

### 1. Install Anaconda or MiniConda
*If you already have Anaconda or Miniconda installed, skip to step 2.*

#### Install Anaconda (Recommended)
Download the python 3.6 version of Anaconda for your system from here:
[https://www.continuum.io/downloads](https://www.continuum.io/downloads)

Follow the setup instructions on the Anaconda site.

#### Or Install Miniconda (Takes up Less Space)
If you have limited space on your system you can download Miniconda. This will only install what is needed for the training session and will skip many of the components that are included in the full version of Anaconda. Follow these instructions to install Miniconda on your system: 
[https://conda.io/docs/install/quick.html](https://conda.io/docs/install/quick.html)


### 2. Clone the Training Repository
Use git to clone the repository for the training session down to your computer. Use git so you can easily update the contents of the training repository. Remember to update the repository by running ```$git pull``` the day before the training session to ensure contents are up to date. Here is the link to the repository: [https://github.com/juskaiser/FARCON_NLP](https://github.com/juskaiser/FARCON_NLP).

Navigate to your desired installation location in command line and clone the repository with the following commands:

**Via SSH:** ```git clone git@github.com:juskaiser/FARCON_NLP.git```

or

**Via HTTPS:** ```git clone https://github.com/juskaiser/FARCON_NLP.git```


### 3. Create your Local Environment
In command line, navigate to the folder for the training session that was just cloned. It should be called *FARCON_NLP* unless it was changed. Run ```$ ls``` from within the directory in command line, you should see a result like this:

```
$ ls
README.md   Test.ipynb  data    environment.yml
```
**Note: there may be additional files to those listed above.*

In command line, from within the *FARCON_NLP* folder, run the following command:

```conda env create -f environment.yml ```

This will download and install the python packages needed for the training session and may take a few minutes, depending on the speed of your internet connection. 

See *Use environment from file* in the conda documentation for troubleshooting & reference:
[https://conda.io/docs/using/envs.html#use-environment-from-file](https://conda.io/docs/using/envs.html#use-environment-from-file)

### 4. Verify and Activate the New Environment
To verify the new conda environment was created, run the following command in command line:

```
$ conda env list
```
You should see a result like this:

```
# conda environments:
#
far_nlp                  /Users/Justin/anaconda/envs/far_nlp
py2                      /Users/Justin/anaconda/envs/py2
root                  *  /Users/Justin/anaconda
```

The new conda environment (*far_nlp*) should be listed. **The asterisk indicates the current active environment.**

Activate the new environment with the following command:

**OS X, Linux:** ```$ source activate far_nlp```

**Windows:** ```$ activate far_nlp```

Now, run ```$ conda env list ``` a second time to verify the new environment is active. You should see that the asterisk is now on the line for *far_nlp*, indicating the new environment is active.

```
# conda environments:
#
far_nlp               *  /Users/Justin/anaconda/envs/far_nlp
py2                      /Users/Justin/anaconda/envs/py2
root                     /Users/Justin/anaconda
```

See the conda documentation for more info on managing and switching between environments:
[https://conda.io/docs/using/envs.html](https://conda.io/docs/using/envs.html#)

### 4. Install the English Model for spaCy
**Before proceeding, make sure the new conda environment, *far_nlp*, is activated (see the previous step).** The spaCy NLP package was already installed in previous step, but you need to manually install the English language model for spaCy. Install the English model by entering the following command in command line:

```$ python -m spacy download en```. 

**Note: you can enter this command from any location in the command line.*

SpaCy installation instructions for troubleshooting & reference:
[https://spacy.io/docs/usage/](https://spacy.io/docs/usage/)
### 5. Download the Data
Download the data we'll use in the session from the dropbox link below. Unzip each each data file and place the unzipped file in the data directory.

**Data for NLP training session:** [https://www.dropbox.com/sh/0jl09kew2wg3314/AADRoNVz0nMSbPHFXUgcJW-Ua?dl=0](https://www.dropbox.com/sh/0jl09kew2wg3314/AADRoNVz0nMSbPHFXUgcJW-Ua?dl=0)

The structure for the FARCON_NLP directory should look like this after you've copied in the unzipped data files:

```
FARCON_NLP
├── README.md
├── Test.ipynb
├── data
│   ├── amazon_electronics_reviews_subset.csv
│   ├── sandisk_sd_card_reviews.csv
│   ├── ...other data
│   └── ...other data
├── environment.yml
└── utilities.py

```

### 6. Run the Test Notebook
Now let's use Jupyter Notebook to perform some tests on our installation. Navigate to the FARCON_NLP directory in command line. From within the directory start Jupyter Notebook by running this command from command line:

```
$ jupyter notebook
```

This will open up Jupyter Notebook in your browser. Click on Test.ipynb to launch the test notebook: 

![GitHub Logo](img/jnb.png)

Once the *Test* notebook is open hit ```shift + enter``` to run the cell and proceed to the next cell. Continue on and hit ```shift + enter``` for each cell. If each cell runs without any errors, you are good to go.

#### For a More Thorough Test:
You can perform a more in-depth installation test for spaCy by following these instructions:
[https://spacy.io/docs/usage/#tests](https://spacy.io/docs/usage/#tests)

You can do the same for sci-kit learn by following these instructions:
[http://scikit-learn.org/stable/developers/advanced_installation.html#testing](http://scikit-learn.org/stable/developers/advanced_installation.html#testing)

Each of these tests take a few minutes to run.