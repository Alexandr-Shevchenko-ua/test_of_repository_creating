# Metadata Extraction Script

Table of Contents
=================

* [Metadata Extraction Script](#metadata-extraction-script)
   * [Minimal requirements](#minimal-requirements)
   * [Supported file extensions](#supported-file-extensions)
   * [Installing all the dependencies](#Installing-all-the-dependencies)
   * [Running Metadata Extraction Script](#running-metadata-extraction-script)


## Minimal requirements:
* **Installed:**
	* Python: 3.9
	* Pip(package management system for Python software packages.): the newest


## Supported file extensions

We support the next extensions - ['.png', '.jpg', '.jpeg', '.docx', '.doc', '.txt', '.pdf']

## Installing all the dependencies

Basic **command line usage**:

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
