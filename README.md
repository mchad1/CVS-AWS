#CVS-AWS.py

#Step 1 : Requirement: Using pip install, install arparse and requests

	python 3+
	python -m pip install argparse --upgrade
	python -m pip install requests --upgrade


#Step 2: Authentication

	CVS-AWS.py requires authentication, go to cloud central for
        your CVS AWS account and take down the secretekey, apikey,
        api endpoint a.k.a. url, and region

	CVS-keys.py creates a json file recording the aforementioned
        and stores them by project.

	project is concept unique to csv-aws.py wherein multiple
        keys may be referenced by csv-aws.py enabling the
        administration of several accounts

	python cvs-keys.py
		usage: cvs_keys.py [-h] [--project PROJECT] [--url URL]
       	            [--secretkey SECRETKEY] [--apikey APIKEY] [--region REGION]
		
		cvs_keys.py is used to configure the aws_cvs_config base file
	
		optional arguments:
		  -h, --help            show this help message and exit
		  --project PROJECT, -p PROJECT
		  			To enable use of multiple
                                        Cloud Volume environments, enter
                                        an arbitrary project name. If
                                        none is provided, default is used
		  --url URL, -u URL     Enter the url for the cloud
                                        volumes api service
		  --secretkey SECRETKEY, -s SECRETKEY
		                        Enter the cloud volumes secret-key
		  --apikey APIKEY, -a APIKEY
		                        Enter the cloud volumes api-key
		  --region REGION, -r REGION
	       		                Enter the cloud volumes region
#Step 3: Use cvs-aws.py as such:

	python cvs-aws.py -h	#The --preview flag enables you to
                                run commands non-impacfully before
                                running it for real.  --preview does
                                not work for list commands, why
                                would it though?
