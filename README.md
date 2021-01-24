# ECS Secrets in AWS

Paraphrasing a question from a Solutions Architect Associate practice exam I took recently:

_You are designing application running on ECS and the database credentials must be passed as environment variables.  The credentials must not be visible in plain text on the ECS cluster.  How would you design the system to fulfill this requirement with minimal effort?_

The suggested answer is to store the credentials in the SSM Parameter Store, encrypt them using KMS and grant access to the relevant ECS tasks to access KMS and Parameter Store so the application can access and decrypt the secrets at runtime.

I got this wrong because I opted for AWS Secrets Manager instead of Parameter Store.  I'm not sure I understand why though.  My thinking is that AWS Secrets Manager is designed for secrets management and has strong support for RDS so it ought to be easier to implement.  However, I have to admit that RDS was not mentioned in the question so I can't assume it would be used.  

So in the interests of science I have decided to build a simple example so I can experiment with both options.




