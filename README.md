# Metadata Extraction Script

Table of Contents
=================

* [Metadata Extraction Script](#metadata-extraction-script)
   * [Minimal requirements](#minimal-requirements)
   * [Supported file extensions](#supported-file-extensions)
   * [Installing all the dependencies](#Installing-all-the-dependencies)
   * [Running Metadata Extraction Script](#running-metadata-extraction-script)
   * [Example of running](#example-of-running)
   * [Extended features](#extended-features)


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
    
	python run_metadata_extraction --file_path {path_to_file}
	
OR

	python run_metadata_extraction --s3_link {s3_link}

For more information about the various command line options use `run_metadata_extraction.py --help`.


## Example of running

	run_metadata_extraction.py path_to_document.pdf
	
	
## Extended features

If you want to run a script with an S3 link, you need to create a .aws folder in the /home directive and a file called "credentials". After that, enter the credentials themselves.

OR

Basic **command line usage**:

	aws configure

After that file with the credentials will be generated and saved in $HOME/.aws/credentials for Unix-based systems or in %UserProfile%\ .aws\credentials for Windows.
For datails see:
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html