# Opensearch Cluster in VPC and authenticated access to dashboard outside VPC using Nginx Proxy server
<!--BEGIN STABILITY BANNER-->
---

![Stability: Stable](https://img.shields.io/badge/stability-Stable-success.svg?style=for-the-badge)

> **This is a stable example. It should successfully build out of the box**
>
> This example is built on Construct Libraries marked "Stable" and does not have any infrastructure prerequisites to build.

---
<!--END STABILITY BANNER-->

## Overview

This project demonstrates how to set up Amazon OpenSearch Service domain in a VPC. Along with OpenSearch Service domain it also launches an EC2 instance to run nginx proxy for accessing OpenSearch Dashboards.
This example also deploys Cognito resources to provide authenticated access to Amazon Opensearch Dashboard.


This [AWS repost](https://repost.aws/knowledge-center/opensearch-outside-vpc-nginx) was used in part to identify required steps.

## Synthesize Cloudformation Template

To see the Cloudformation template generated by the CDK, run `cdk synth`, then check the output file in the "cdk.out" directory.

## Deploy

Run `cdk deploy`. This will deploy your Stack to your AWS Account.

After the deployment,
1. Go to the Cloudformation stack outputs and check the `CognitoUserPoolId`.
2. Go to Cognito Service on AWS Console and create a Cognito User. You can set the password or choose to receive the password in an email.
3. From the Cloudformation outputs, click on the `NginxOpensearchDashboardUrl`
4. Use Cognito credentials to login. You shoud be re-directed to your Opensearch Cluster's Dashboard


## CDK Destroy

If no longer want the stack to be running, you can destroy the stack by running `cdk destroy`

