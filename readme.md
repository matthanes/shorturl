# S3 URL shortener
## Introduction
This small Astro project will create directories and files for an S3 bucket to shorten URLs. The directories contain an index.html file that redirects to the URL. The project will require a rewrite function on the CloudFront distribution to redirect to the index.html file. You can find an example of this in [this document from Amazon](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/example-function-add-index.html).

With the rewrite function, items in directories will redirect to the index.html file. For example, if you have a directory called `test` and a file called `index.html` in that directory, the URL `https://XXXXXXXX.cloudfront.net/test` will default to `https://XXXXXXXX.cloudfront.net/test/index.html`. That index.html will contain a meta redirect to the URL you want to shorten.

## Output
The files will output to a dist directory. The contents of the dist directory can be uploaded to an S3 bucket. The folders/files should be uploaded to the root of the bucket. 