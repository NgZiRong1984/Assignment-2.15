# Assignment-2.15

Answer the following:

What is needed to authorize your EC2 to retrieve secrets from the AWS Secret Manager?

- IAM Role for EC2: Create an IAM role with permissions to access Secrets Manager.
- IAM Policy: Define the necessary policy that grants the EC2 instance permissions to retrieve the secret.
- ARN for Secret: Use the secret's name to derive the ARN (Amazon Resource Name) that is referenced in the policy.

Derive the IAM policy (i.e. JSON)?

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "secretsmanager:GetSecretValue",
                "secretsmanager:DescribeSecret"
            ],
            "Resource": "arn:aws:secretsmanager:ap-southeast-1:your_account_id:secret:prod/cart-service/credentials-*"
        }
    ]
}



Using the secret name prod/cart-service/credentials, derive a sensible ARN as the specific resource for access

 "arn:aws:secretsmanager:ap-southeast-1:255945442255:secret:prod/cart-service/credentials-*"
