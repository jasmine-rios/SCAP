# SCAP
Create architecture to run SCAP scan on EC2 and results of scan go into a bucket. A lambda parses through bucket to find vulnerabilities and will trigger Security Hub for remediation, counts of findings in CloudWatch, and saves detailed information onto a Dynamo DB table.

## What is SCAP?

SCAP stands for ???
It uses NIST (National Institute of Standards and Technology) guidelines found in (???Document number)
You run a SCAP scan against a system that you want to see what vulnerabilities it has so you can either manually or automatically remediate them.

Although geared towards government machines, it is a great baseline to do for any industry's compute resources to avoid exploitation.

## What Resources does it require?

- EC2 instance (Virtual Machine in AWS) running RHEL (RedHat Enterprise Linux Operating System) with atleast 8 GB RAM (Instance type compatibility: ???)
- S3 Bucket is where you store files and in this case the SCAP results that we want automatically exported to.
- Lambda function is where you can run a little piece of code without having to provision an EC2 instance and patch it. It can be triggered based on time events (CRON) or regular events based on listeners. 
- Security Hub is where you have everything security like in AWS where you have other security services (Amazon GuardDuty, A)