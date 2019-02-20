# CloudFormation Templates

This repository is a place to store all the CloudFormation templates that I create during my exploration of the technology. 

## Manually Creating the Stack in the AWS Console

  - Go to the AWS Console and log in to your account. 
  - Go to the CloudFormation service. 
  - Choose `Create new stack`
  - Click `Upload a template to Amazon S3`
  - Then `Choose file` and select your YAML file.
  - Click `Next`
  - Type in a Stack Name, e.g. MyAwesomeAWSStack
  - Click `Next` twice.
  - Then `Create`

Your new stack will now be created based on the `Resources` specified in the YAML file.

## Syncing the CloudFormation scripts to AWS S3

So that the templates are easy to access via the console in AWS CloudFormation you can sync the contents of this repository up to the default S3 bucket that is created for CloudFormation templates by AWS by invoking this command from a terminal window from the root of the directory that this repository is cloned to:

`aws s3 sync . s3://cf-templates-<unique-id>-<AZ> --exclude "*.git/*" --exclude README.md`

You can then create this stack in the console by choosing the template source as `Amazon S3 URL` and specifying the URL of the object in the S3 bucket.
