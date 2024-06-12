# MY CLOUD RESUME CHALLENGE

## Introduction

This project integrates a number of AWS services and other resources to deliver contents of a static webpage (Resume) over the internet. The challenge is considered an entry into the cloud world and provides an exposure into cloud and DevOps practices. 

![My Cloud Resume Challenge Architecture Diagram](Org_charts.png)

The project is divided into parts:

* ### Frontend

This part of the project consists of a resume webpage built using HTML and styled with CSS. It aso has some Javascript for interactivity. These web files are living in an S3 bucket that's configured to host a static website. The bucket is sitting behind a CloudFront Distribution (Content Delivery Network CDN). It is hosted on Route 53 with a custom domain name (blessingogbeh.com) over a secure HTTPS connection using an SSL Certificate set up Certificate Manager.

* ### Backend

This portion of the Challenge utilizes Lambda, DynamoDB and some Javascript to retrieve and update a website visitor counter for the webpage. The Lambda function is written in Python using the amazon SDK boto3 library and servs as a bridge of communication between the Javascript and a NoSql database -  DynamoDB table that stores the visitor count in a key-value pair. A counter Script is embeded in the root file of the webpage content and calls the Lambda function through its function URL to retrieve and display the visiotor count on the resume webpage.

* ### Continuous Integration Continuous Deployment (CI/CD)

With the use of Github and Github Actions, one is able to push changes in code to the S3 bucket while keeping the entire architecture intact. I've utilized a yaml workflow in Github Actions and with my s3 bucket name and AWS account secrets, I'm able to seamlessly push changes into the S3 bucket.

***
You can find details of this project including step by step approach I took in completing challenge, the chalenges I faced and how I overcame them in my blog here.