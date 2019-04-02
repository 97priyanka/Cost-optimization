# Cost-optimization

This python script gather the information from the AWS account and store the information into an excel file in a desired pattern for cost optimization.
This excel file will take you know how you can minimize the cost of your AWS account.

This is the code to be run in lambda function and generate excel file which contain:
  
  tab 1: Information of stopped EC2 instance - This will make you know about all the instances that are stopped, if they are of no use you can terminate them to reduce cost.
  
  tab 2: Information of available EBS volumes - It shows the available EBS volumes that are not attached to any instance, so if you don't need it. You can deregister it.
  
  tab 3: Information of un-associated elastic ip's - As the elastic ip charge when it is not in use, so this excel will show the elastic ip's that are not in use so you can release addresses to reduce cost

This python function can not run directly in lambda, as lambda do not support external dependencies like 'openpyxl'.
Thus, an environment variable is to be created that contain all the dependencies that the python function require, to create environment variable refer- "https://docs.aws.amazon.com/lambda/latest/dg/lambda-python-how-to-create-deployment-package.html".
It will contain a zipped file that contain your python code as well as all the dependencies which is then zipped in the lambda function.

NOTE : Make sure to change the lambda handler name to your python script's name.
