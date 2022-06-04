# SPA in s3 with CloudFront

Creates the infrastructure to host and expose a Single Page Application:
  - An Amazon S3 bucket for hosting the application
  - An S3 bucket policy to allow CloudFront acces to the files
  - An Amazon CloudFront distribution to expose the application
  - An Amazon S3 bucket for hosting bucket and cloudfront access logs
  - An SSL/TLS certificate hosted in ACM for the custom domain name
  - DNS records for the custom domain name
  - CloudFront function to redirect to index.html because react router need this behaviour

## Deploy the solution
This template has been tested in us-east-1 region only, you can change the resources names to match your own deployment

  1. Deploy the template in CloudFormation.
  2. On the Specify stack details page, enter values for the following fields:
      - SubDomain: The subdomain for your registered domain name, for example: www.example.com
      - DomainName: Your registered domain name, as example.com. This domain must be pointed to a Route 53 hosted zone.
      - HostedZoneId The Route 53 Hosted Zone Id containing the domain being used.
      - CreateApex: Create an Alias to the domain apex (example.com)
  3. Wait for the CloudFormation stack to launch.
  4. Choose the bucket for the files whose name is protunnus-web or the name you have chosen
  5. In this bucket upload your own SPA build.
