# AWS VPC with Public Subnet and Internet Gateway

This repository contains AWS Cloudformation template to create an AWS VPC with a single public subnet and an Internet Gateway. The infrastructure is deployed using GitHub Actions.

## Infrastructure Overview

- VPC with a single CIDR block
- One public subnet in a single Availability Zone
- Internet Gateway attached to the VPC
- Route table for the public subnet with a route to the Internet Gateway

## Cost Optimization

This setup deliberately avoids creating private subnets and NAT Gateways to minimize costs. Using only public subnets eliminates the need for Elastic IPs associated with NAT Gateways, which can incur additional charges.

## Deployment

The infrastructure is automatically deployed using GitHub Actions when changes are pushed to the main branch.

### Prerequisites

1. AWS Account
2. GitHub Account
3. AWS Cli install locally (for development and testing)

### Repository Secrets

The following secrets must be set in the GitHub repository settings:

- `AWS_ACCESS_KEY_ID`: Your AWS access key
- `AWS_SECRET_ACCESS_KEY`: Your AWS secret access key

The following environment variable must be set in the GitHub repository settings:
- `AWS_REGION`: ap-southeast-2 for Sydney region.

## Usage

1. Clone this repository
2. Modify the main.yaml file to customize your VPC and subnet CIDR blocks in the parameter override.
3. Commit and push your changes to the main branch
4. The GitHub Action will automatically deploy the infrastructure to AWS

## Security Considerations

- Ensure that your AWS access keys have the minimum required permissions
- Regularly rotate your AWS access keys
- Consider using AWS IAM roles for enhanced security

## Contributing

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

## License

This project is licensed under the MIT License.
