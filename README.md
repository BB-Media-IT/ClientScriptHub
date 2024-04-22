<image
  src="https://s3.invisionapp-cdn.com/storage.invisionapp.com/boards/files/183060432.png?x-amz-meta-iv=1&x-amz-meta-ck=cd20ea812f8ae161523111afa5aea5e8&AWSAccessKeyId=AKIAWCDCF6QSLTS7LRWT&Expires=1717200000&Signature=90X61ZsbGe2EneL7IRbEzerj7Oc%3D"
  height=100
  margin=0>

# BB Media

Award Winning Data Science Company, specialized in Media & Entertainment for over 36 years. 
We study how markets evolve in any of their formats and screens, developing primary survey methodologies for linear and non-linear measurement of content.
We are focused. We are experts. We innovate. We act fast. We are thorough. We deliver.

<image
  src="https://github.com/BB-Media-IT/ClientScriptHub/assets/4085605/46558862-529d-4dec-a7a8-7d956fec88f3"
  height=80
  margin=0>

## BB Media's main customers
![image](https://github.com/BB-Media-IT/ClientScriptHub/assets/4085605/c2df7aca-cf33-4006-9541-3256c1f97abd)

## BB Media Coverage

![image](https://github.com/BB-Media-IT/ClientScriptHub/assets/4085605/8c82551a-5f0c-4fd0-b730-1efb86fd0ed5)


## Data Hub by BB Media





## AWS S3 Object Listing & Download Script

This script connects to an S3-compatible storage (like Digital Ocean Spaces) to list and download objects based on certain prefixes.

## Requirements
- Python 3
- `boto3` library
- A configuration file (`config.cfg`) with necessary credentials and parameters.

## Configuration File (`config.cfg`)

The configuration file should have sections and keys for the AWS/Digital Ocean (or any S3-compatible storage) configurations as well as for defining prefixes and download paths. 

Structure:
```
[aws_digital_ocean]
REGION_NAME = Copy the one we provide 
ENDPOINT = Copy the one we provide
ACCESS_ID = Copy the one we provide
SECRET_KEY = Copy the one we provide
BUCKET = Copy the one we provide

[prefix_buckets]
CONTENTS = Content/latest
EPISODES = Episodes/latest
STATS = Stats/latest
SOURCE = Stats/latest

[paths]
CONTENTS = Datos/Contents
EPISODES = Datos/Episodes
STATS = Datos/Stats
SOURCES = Datos/Sources
```

## How It Works

1. **Variable Collection:** The script starts by reading the `config.cfg` file and obtaining the necessary configurations.

2. **Connection Configuration:** The script establishes a connection to the S3 compatible storage.

3. **Pagination Activation:** Uses paginator to list all objects in the specified bucket.

4. **List Prefix:** It lists all objects based on the specified prefixes in the configuration file.

5. **Download Files:** All objects listed will be downloaded to specified paths based on their prefixes. The script ensures that the directories exist; if not, it creates them.

## How to Run
1. Ensure you have the necessary dependencies installed, mainly `boto3`.
2. Update the `config.cfg` file with the required configurations.
3. Run the script.

## Notes
Remember to never commit your `config.cfg` with sensitive credentials to a public repository.

## Schedule
You can create a .sh, .bat, or any required file and run it with an orchestrator or just with a crontab.

Example:
At 12:00 on Saturday: `0 12 * * 6`
