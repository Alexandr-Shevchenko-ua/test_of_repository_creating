# Metadata Extraction Script

Table of Contents
=================

* [Metadata Extraction Script](#metadata-extraction-script)
   * [Supported file extensions](#supported-file-extensions)
   * [Installing all the dependencies](#Installing-all-the-dependencies)
   * [Running Metadata Extraction Script](#running-metadata-extraction-script)


## Supported file extensions

We support the next extensions - ['.png', '.jpg', '.jpeg', '.docx', '.doc', '.txt', '.pdf']

## Installing all the dependencies

### For Linux

1. Install or update Anaconda for Linux. See details in chapter "Installing on Linux" in: https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html#installing-on-linux

Basic **command line usage**:

	conda create -n metadata_extraction python=3.9
	
	activate metadata_extraction
	
	pip install -r requirements.txt
	
### For Windows

1. Install or update Anaconda for Linux. See details in chapter "Installing on Windows" in: https://docs.conda.io/projects/conda/en/latest/user-guide/install/windows.html#installing-on-windows

2. Download tesseract tesseract-ocr-w32-setup-v5.1.0.20220510.exe (32 bit) OR tesseract-ocr-w64-setup-v5.1.0.20220510.exe (64 bit): https://github.com/UB-Mannheim/tesseract/wiki

3. Install tesseract tesseract-ocr-w32-setup-v5.1.0.20220510.exe (32 bit) OR tesseract-ocr-w64-setup-v5.1.0.20220510.exe (64 bit)

4. Add environment variable TESSDATA_PREFIX with the folder value "tessdata" in the path to the installed tesseract(default path for TESSDATA_PREFIX: "C:\Program Files\Tesseract-OCR\tessdata")

5. Open Anaconda Prompt

Basic **command line usage**:

	conda create -n metadata_extraction python=3.9
	
	activate metadata_extraction
	
	conda install -c conda-forge tesserocr
	
	pip install -r requirements.txt


## Running Metadata Extraction Script

Basic **command line usage**:
    
If you want to run a script on an existing file you need to use the "--file_path" option
	
	python run_metadata_extraction --file_path {path_to_file}
	
OR

If you want to download via S3 link, you need to create a .aws folder in the /home directive and a file called "credentials". After that, enter the credentials themselves. Or use in CLI `aws configure`, after that file with the credentials will be generated and saved in $HOME/.aws/credentials for Unix-based systems or in %UserProfile%\ .aws\credentials for Windows.
For datails see:
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html

use the "--s3_link" option

	python run_metadata_extraction --s3_link {s3_link}
