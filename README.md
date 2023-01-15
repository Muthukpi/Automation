
# Project Title
KPI Cloud ANALYTICS AUTOMATION Engine for ORACLE CLOUD Applications

/*Copyright(c) 2022 KPI Partners, Inc. All Rights Reserved.
        #Licensed under the Apache License, Version 2.0 (the "License") you may
        # not use this file except in compliance with the License.
        # Unless required by applicable law or agreed to in writing, software
        # distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
        # WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
        # License for the specific language governing permissions and limitations
        # under the License.
        # author: KPI Partners, Inc.
        # version: 2022.01
        # description: SnowFlake is being used as a Database & Airflow as Scheduler, 
        # to build KPI Cloud Analaytics Framework & to implement the data warehouse*/


>This Automation will automate the manual work of copying the schema from the oracle DMR documentation and creating the DDLs.
>Generate all the required scripts which involves from the BIP Data model creation to loading the data into snowflake stage.
>It will run the required scripts on snowflake and create the respective tables.
>So we can use this automation tool whoever wants to migrate their oracle fusion cloud into the snowflake to do the initial process.

## Acknowledgements

 - [Chrome driver installation steps](https://understandingdata.com/install-google-chrome-selenium-ec2-aws/)
 - [Download Chromedrive](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)
## API Reference

#### exe  files to run...


| exe files | Description                |
| :-------- |  :------------------------- |
| `url_generator.exe`| Generate URLS for the given modules from orcale documentation|
| `script_generator.exe`|Generate DMR scripts by using the URL csv|
| `script_run.exe`| yet to be decided|

#### install the below libraires

```
requests			
pandas			
lxml			
beautifulsoap			
selenium				
logging			
csv			
os,sys			
datetime
pip install -U selenium		
pip install webdriver-manager
```

## Steps to follow For Ret hat users:

Any additional information goes here

https://understandingdata.com/install-google-chrome-selenium-ec2-aws/		
			
#### step_1.check both your chromedriver and chrome version are same>	
			
		TO install the chromedriver use below commands>	
			sudo wget https://chromedriver.storage.googleapis.com/108.0.5359.22/chromedriver_linux64.zip
			sudo unzip chromedriver_linux64.zip
			sudo mv chromedriver /usr/bin/chromedriver
			chromedriver --version
			
		<Then you’ll need to download and install the Google Chrome binary for your EC2 instance>	
			sudo curl https://intoli.com/install-google-chrome.sh | bash
			sudo mv /usr/bin/google-chrome-stable /usr/bin/google-chrome
			google-chrome --version && which google-chrome
			
		<check this repository to get the required versions of chromedrive	
			https://chromedriver.storage.googleapis.com/
			
		<if you want to remove the old chrome driver use the below commands. So that we can ensure that we have removed old version from all the places>	
			sudo rm -f /usr/bin/chromedriver
			sudo rm -f /usr/local/bin/chromedriver
			sudo rm -f /usr/local/share/chromedriver
			
#### step_2.Run the python the file with required arguments:
	    
		(Note : Follow the step_3 to step_8 in section c)
	
		python3 /home/Automation/SOURCE/url_generator.py /home/Automation/INPUT/ /home/Automation/INPUT/parameter.json 3 10
		python3 /home/Automation/SOURCE/script_generator.py /home/Automation/INPUT/ORACLE_DMR_URLS.csv /home/Automation/INPUT/parameter.json

## Steps to run .exe file in windows.			

#### Step_1.we have below .exe files for the automation. Please follow the below steps in order to run Automation.		
			a.url_generator.exe	
			b.script_generator.exe
			c.script_run.exe (Not yet decided)
				
#### Step_2.Check the input files are placed in the INPUT folders	
			parameter.json
		
#### Step_3.Open the parameter file and update the parameters based on your requirement ans save.
			
#### Step_4.Open cmd and run the url_generator.exe file with 4 arguments			
	D:\Automation\url_generator.exe D:\Automation\INPUT\ D:\Python\INPUT\parameter.json 3 10
        argument1 : the path which the csv file to be placed.
        argument2 : parameter path
        argument3 : sub_modules_limit(Eg: If you give 10 , the program will take only first 8 sub-modules from the oracle documentation. so make it 100) 
        argument4 : Tables_limit (Eg : If you give 10 , it will take first 10 tables from each sub-modules in oracle documentation. So give max table limit like 1000)
        Note : argument3 and argument4 were optional if not provied, it will take default values (100,1000) respectively.Also close the previous csv file before running . It may cause permission issue.
    
#### Step_5.Check the ORACLE_DMR_URLS.csv file got generated in the input folder.		
			
 #### Step_6.Try to change the flag as Y in order to process the required table.		
			
#### Step_7.Run the script_generator.exe file with 2 arguments		
	D:\Automation\script_generator.exe D:\Automation\INPUT\ORACLE_DMR_URLS.csv D:\Automation\INPUT\parameter.json	
        argument1 : csv file
        argument2 : parameter path (json file path)

#### Step_8.Verify log and check status of tables processed.
	
#### Step_9. if you want to run only the script generator , keep the csv file and parameter file in the required format and run Step_7
