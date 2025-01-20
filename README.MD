# Manage Google Big Query Resources with Terraform

## Prerequisites
*  A Google Cloud Platform (GCP) Account, with a project you have rights to make changes to.

## Steps to setup this Repo

1. Fork or clone this repository
2. When cloning: initiate git in this repo and push to GitHub remote.
  *  run 'git init' in the folder you are working in.
  *  add the files of the folder to git with 'git add *'
  *  commit with 'git commit -m "commit message"'
  *  go to GitHub and create a new, empty repository
  *  go back to your local folder and add the url of the new GitHub repo 'git remote add <url>'
  *  Push the local folder to GitHub with 'git push -u origin <branch-name>'
3. Make sure you have a GCP service account with proper access to the resources you will create
4. Take the key from this service account and save as a GitHub repo secret. Name it GCLOUD_SERVICE_ACCOUNT_KEY 
5. Create a bucket where the Terraform state file shall be stored. Refer to this bucket in the backend object in providers.tf
6. Set up an environment in the GitHub repo (Settings/Environments/New environment). Name it live. Make sure to tick Required reviewers and add people who need to be able to accept Terraform Apply.
7. Update the variable values in terraform.tfvars to match your GCP account.


## How to run

### For local Terraform use

1. When you change any of the resources managed by Terraform (mainly in main.tf and resources folder), and push to remote main, a Terraform workflow (terraform.yaml) is initiated. 
2. A Terraform plan will be created under GitHub Actions. You can approve the plan and apply the changes if you have the rights to do so. 
3. Your changes are now live in GCP.

