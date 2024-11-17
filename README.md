# Static Website Hosting on AWS
This project demonstrates the steps to deploy a static website on AWS using S3 and CloudFront.

## The files included are: 

- index.html - The Index document for the website.
- /img - The background image file for the website.
- /vendor - Bootssrap CSS framework, Font, and JavaScript libraries needed for the website to function.
- /css - CSS files for the website.

## Steps to Deploy

1. Create an S3 Bucket:
- Configured the bucket for static website hosting.
- Secured the bucket using IAM policies.
2. Upload Website Files:
- Uploaded the website files (HTML, CSS, JS) to the S3 bucket.
3. Set Up CloudFront:
- Configured AWS CloudFront as the Content Delivery Network (CDN) to speed up content delivery.
4. Access the Website:
- Accessed the website using the CloudFront distribution URL.

## Website URL
- CloudFront URL: https://d2ffhzntz1zn29.cloudfront.net
- S3 Endpoint URL: http://my-713427788215-bucket.s3-website-us-east-1.amazonaws.com
- S3 Index.html file URL: https://my-713427788215-bucket.s3.us-east-1.amazonaws.com/index.html

## Submission Notes
- The project includes screenshots of the following steps:
1. S3 bucket creation and configuration.
2. Upload of website files to the S3 bucket.
3. CloudFront distribution setup.
4. Successful website access via CloudFront.

- Screenshots folder is zipped into a file named my-static-s3-website.zip and included alongside this README.

## Additional Information
IAM Policy details: 
- The bucket is secured with read-only permissions for public access.
Cloudfront download file instead of hosting: 
- Reason: Incorrect metadata of index.html, 
- Update using:
```bash
aws s3 cp s3://my-713427788215-bucket/index.html s3://<bucket-name>/index.html --content-type "text/html" --metadata-directive REPLACE
copy: s3://<bucket-name>/index.html to s3://my-713427788215-bucket/index.html
```
