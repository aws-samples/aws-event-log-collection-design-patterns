## Optimize AWS event and log collection using common design patterns  

If your organization operates within hundreds or thousands of AWS accounts, most likely you’ve been searching for better ways to optimize how you collect and process events and logs from your AWS services. Event and log information is a key component when gaining valuable business insights and providing capabilities like cloud security posture management (CSPM), cloud-native application protection platform (CNAPP), security Information and event management (SIEM), extended detection and response (XDR), and more. 

Many AWS customers follow a [multi-account strategy](https://docs.aws.amazon.com/whitepapers/latest/organizing-your-aws-environment/organizing-your-aws-environment.html#multi-account-strategy-best-practices-and-recommendations) to establish their cloud foundation, as described in the topic [Organizing Your AWS Environment Using Multiple Accounts](https://docs.aws.amazon.com/whitepapers/latest/organizing-your-aws-environment/organizing-your-aws-environment.html). Using this strategy, they can enable multiple AWS services at the [AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html) level and then transfer events and logs from these services to a dedicated AWS account. Oftentimes, they use open source, in-house, or AWS Partner tools to visualize the collected data for analysis. 

In our experience working with customers, we’ve learned that a top priority for organizations is to collect event and log data in the most efficient and cost-effective way. In this blog post, we discuss some common approaches for collecting data from multiple AWS services across your organization. We also present some common patterns that you can reuse to consume the data. Code snippets are available to help you build similar solutions in your own environment. 

About this blog post

* Time to read (in minutes): 7 minutes
* Time to complete (in minutes): 12 minutes
* Cost to complete: $0
* Learning level: 300 
* AWS services: 
    * [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)
    * [Amazon EventBridge](https://aws.amazon.com/eventbridge/)
    * [Amazon OpenSearch Service](https://aws.amazon.com/opensearch-service/)
    * [Amazon Simple Notification Service (Amazon SNS)](https://aws.amazon.com/sns/)
    * [Amazon Simple Queue Service (Amazon SQS)](https://aws.amazon.com/sqs/)
    * [Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/)
    * [AWS CloudFormation](https://aws.amazon.com/cloudformation/)

## Overview

This repository, describes the following approaches and patterns for collecting and consuming event and log data. 

* Approach 1: Collecting logs in a centralized Amazon CloudWatch monitoring account
* Approach 2: Collecting logs in an Amazon S3 bucket in a centralized log archive account
    * Pattern A: Sending Amazon S3 event notifications through Amazon SQS
    * Pattern B: Sending Amazon S3 event notifications through Amazon SNS
    * Pattern C: Fanning out Amazon S3 event notifications using a combination of Amazon SNS and Amazon SQS
    * Pattern D: Performing centralized logging with Amazon OpenSearch

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

