# SCAP
Create architecture to run SCAP scan on EC2 and results of scan go into a bucket. A lambda parses through bucket to find vulnerabilities and will trigger Security Hub for remediation, counts of findings in CloudWatch, and saves detailed information onto a Dynamo DB table.
