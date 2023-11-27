## Deploy with Continuous Deployment Pipeline from GitHub to S3
## General Info
Code for this project is hosted on GitHub, we create S3 bucket for static website hosting then create a Continuous integration toolkit using CodePipeline.

## Create S3 Bucket
Create S3 bucket in your console and enable static site hosting.
- set default homepage to be `index.html`. 
- Enable public access of objects
- Add bucket policies to allow public read access to files
`{
    "Version": "2012-10-17",
    "Statement": [
    	{
        	"Sid": "PublicReadGetObject",
        	"Effect": "Allow",
        	"Principal": "*",
        	"Action": [
            	"s3:GetObject"
        	],
        	"Resource": [
                "arn:aws:s3:::Bucket-Name/*"
        	]
    	}
    ]
}
`

## Create a Pipeline that will orchestrate getting the code from your GitHub to the S3 bucket.
