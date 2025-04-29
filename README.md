# SCAP Scan Testing in AWS
Create architecture to run SCAP scan on EC2 and send results of scan go into a bucket via POST API.
POST API on S3 bucket triggers Lamabda to run function or it's block of code to SCAP tool.

You can get the scan onto an EC2 instance by running a `git clone https://<repo>` and repo is where you the repo that has the scan is located.
You might need certain dependencies to grab the script based on the operating system you are running.

## What is SCAP?

You run a SCAP scan against a system that you want to see what vulnerabilities it has so you can either manually or automatically remediate them.
It uses NIST (National Institute of Standards and Technology) guidelines
Although geared towards government machines, it is a great baseline to do in combination with other scans for any industry's compute resources to avoid exploitation.

It has CAT 1, CAT 2, and CAT 3 vulnerabilities (also CAT I, CAT II, CAT III)
CAT 1 is for critical vulnerabilities and you have to fix those or provide a mission or business essential reason to why this can't be remedied or why the risk will be taken
CAT 2 are also important and high visability vulnerabilies but can often have a tradeoff on operational need or to have a minumum viable product for testing


## What Resources does it require in AWS?

- EC2 instance (Virtual Machine in AWS) running RHEL (RedHat Enterprise Linux Operating System) with atleast 8 GB RAM (Instance type compatibility: ???)
- S3 Bucket is where you store files and in this case the SCAP results that we want automatically exported to.
- Lambda function is where you can run a little piece of code without having to provision an EC2 instance and patch it. It can be triggered based on time events (CRON) or regular events based on listeners. 
- Security Hub is where you have everything security like in AWS where you have other security services (Amazon GuardDuty, A)
