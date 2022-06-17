# Metadata Extraction Script

Table of Contents
=================

* [Metadata Extraction Script](#metadata-extraction-script)
   * [Supported file extensions](#supported-file-extensions)
   * [Installing all the dependencies](#Installing-all-the-dependencies)
   * [Run script using file path](#run-script-using-file-path)
   * [Run script using S3 link](#run-script-using-s3-link)


## Supported file extensions

We support the next extensions - ['.png', '.jpg', '.jpeg', '.docx', '.doc', '.txt', '.pdf']

## Installing all the dependencies

### For Linux

1. Install or update Anaconda for Linux. See details in chapter "Installing on Linux" in: https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html#installing-on-linux

2. Open CLI:

Basic **command line usage**:

	sudo apt update
	
	sudo apt install -y tesseract-ocr

	conda create -n metadata_extraction python=3.9
	
	conda activate metadata_extraction
	
Move to directory with our script and run:
	
	pip install -r requirements.txt
	
### For Windows

1. Install or update Anaconda for Linux. See details in chapter "Installing on Windows" in: https://docs.conda.io/projects/conda/en/latest/user-guide/install/windows.html#installing-on-windows

2. Download and install tesseract-ocr-w32-setup-v5.1.0.20220510.exe (32 bit) OR tesseract-ocr-w64-setup-v5.1.0.20220510.exe (64 bit): https://github.com/UB-Mannheim/tesseract/wiki

3. Add environment variable TESSDATA_PREFIX with the folder value "tessdata" in the path to the installed tesseract(default path for TESSDATA_PREFIX: "C:\Program Files\Tesseract-OCR\tessdata")

4. Open Anaconda Prompt

Basic **command line usage**:

	conda create -n metadata_extraction python=3.9
	
	conda activate metadata_extraction
	
	conda install -c conda-forge tesserocr
	
Move to directory with our script and run:
	
	pip install -r requirements.txt


## Run script using file path

Basic **command line usage**:
    
	python run_metadata_extraction --file_path {path_to_file}
	
	
## Run script using S3 link

For this you should to create a .aws folder in the /home directive and a file called "credentials". After that, enter the credentials themselves. Or use in CLI `aws configure`, after that file with the credentials will be generated and saved in $HOME/.aws/credentials for Unix-based systems or in %UserProfile%\ .aws\credentials for Windows. For datails see: https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html
After that use the next command in terminal:

	python run_metadata_extraction --s3_link {s3_link}