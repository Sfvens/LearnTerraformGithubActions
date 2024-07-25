# Automate Terraform with GitHub Actions

This repo was built using the following repo as a base: [Automate Terraform with GitHub Actions tutorial](https://developer.hashicorp.com/terraform/tutorials/automation/github-actions).

I used reused the terraform configuration that sets up the EC2 instance and has it return a "Hello World" message when the endpoint is hit. I then reworked the project to accomplish the following:
- switch backend from Terraform Cloud to AWS S3
- use OpenID Connect (OIDC) to allow Github Actions to deploy and update AWS resources via Terraform
- set the workflows to run Terraform only if the configuration itself changes via the dorny/paths-filter@v3 extension
- make pushes to different branches deploy changes to different AWS accounts, thereby separating stage and production environments on AWS