# jenkins terraform

## Overview

This repository will demonstrate an example workflow with Terraform and Jenkins.

## Requirements

* Terraform installed on Jenkins
* Correct plugins installed on Jenkins
* GitHub access token
* AWS credentials
* S3 bucket (for me "terraform-bucket-tarek")

## Setup Bucket

You will need to create a bucket and reference the bucket name in the following section of `main.tf`:

```
terraform {
  backend "s3" {
    bucket = "terraform-bucket-tarek"
    key    = "terraform.tfstate"
    region = "us-east-1"
  }
}
```

You can also update the key name to whatever you want your state file to be named.

## Plugins Required

* [Workspace Cleanup Plugin](https://wiki.jenkins.io/display/JENKINS/Workspace+Cleanup+Plugin)
* [Credentials Binding Plugin](https://wiki.jenkins.io/display/JENKINS/Credentials+Binding+Plugin)
* [AnsiColor Plugin](https://wiki.jenkins.io/display/JENKINS/AnsiColor+Plugin)
* [GitHub Plugin](https://wiki.jenkins.io/display/JENKINS/GitHub+Plugin)
* [Pipeline Plugin](https://wiki.jenkins.io/display/JENKINS/Pipeline+Plugin)
* [CloudBees AWS Credentials Plugin](https://wiki.jenkins.io/display/JENKINS/CloudBees+AWS+Credentials+Plugin)


