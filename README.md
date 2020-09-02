# Automate patching of EC2 instances

The patching process consists of 2 processes.
1. A lambda function that tags instances based on which AZ they are in.
2. A maintenance window, that patches instances that are tagged by that lambda
e.g. Tag = {'Key': 'Patch Group', 'Value': 'PatchMntWindow-AZ-eu-west-1a'}


To skip patching for an EC2 instance the following tag overrides the schedule.
{'Key': 'ssm:patchcycle:enabled', 'Value': 'false'}

