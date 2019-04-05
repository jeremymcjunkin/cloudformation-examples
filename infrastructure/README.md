Any time these files are changed, they should be synced to s3://cf.newscyclemobile.com/infrastructure versioned S3 bucket.

BEFORE running sync below make sure your CloudFormation `yaml` validates.  Ex: `aws cloudformation validate-template --template-body file://apig/single-lambda-proxy-with-CORS.yaml`.  If it passes the validator, but you get strange errors running CloudFormation, create the nested stack yaml directly in the cloudformation console. It does more checking.

FROM the `infrastructure` dir run:
`aws s3 sync . s3://cf.newscyclemobile.com/infrastructure`
