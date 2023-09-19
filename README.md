# host-static-website-on-aws-uisng-s3-bucket
![1](https://github.com/panwar100/host_static_website_on_aws/assets/134361823/f23d5b62-7b9c-4244-9412-7d74e3a264ca)

1.Create an S3 Bucket:

->Log in to your AWS Management Console.
->Go to the S3 service.
->Click the "Create bucket" button.
->Choose a unique and meaningful name for your bucket (e.g., "host-static-website-on-aws-uisng-s3-bucket").
->Select the AWS region you prefer.
->Keep the default settings for the rest of the options or configure them as needed.
->Click "Create bucket."
![2](https://github.com/panwar100/host_static_website_on_aws/assets/134361823/94ba5917-b147-4f69-b839-59281583434f)


2.Upload Your Website Files:
->In the bucket you just created, click on the "Upload" button.
->Select all the files and folders that make up your static website (HTML, CSS, JavaScript, images, etc.).
->Upload them to your S3 bucket.
![3](https://github.com/panwar100/host_static_website_on_aws/assets/134361823/a5f551b6-9dcb-41f3-81f6-5fae8cc48459)


3.Configure Bucket Properties:
->Select your bucket and click on the "Properties" tab.
->Enable static website hosting by clicking on "Static website hosting."
->In the "Static website hosting" panel, select the option for "Use this bucket to host a website."
->Enter the name of your main HTML file (e.g., "index.html") as the Index document.
->Optionally, you can also configure error documents for custom error pages.
->Click "Save changes."
![4](https://github.com/panwar100/host_static_website_on_aws/assets/134361823/7ac1263f-de01-4da8-b0a6-325dbe428a1a)


4.Set Bucket Permissions:
->Go to the "Permissions" tab.
->In the "Block public access" section, click "Edit" and ensure that public access settings allow your website to be publicly accessible. Typically, this means disabling "Block all public access."
->In the "Bucket policy" section, click "Edit" and add a bucket policy that allows public access to your objects. Here's an example bucket policy:
json
->Copy code
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::host-static-website-on-aws-uisng-s3-bucket/*"
        }
    ]
}
->Replace "my-static-website" with your bucket name.
->Click "Save changes."
![5](https://github.com/panwar100/host_static_website_on_aws/assets/134361823/6bed7190-9f93-40d0-98a7-86127b8c3f7a)

5.Testing:
->After configuring everything, you should be able to access your static website using the S3 bucket's endpoint (e.g.,http://host-static-website-on-aws-uisng-s3-bucket.s3-website-us-east-1.amazonaws.com/) or your custom domain if you set it up.
![6](https://github.com/panwar100/host_static_website_on_aws/assets/134361823/fd84fb7e-b6eb-49d5-82de-7ba11fd5216d)

6.Configure DNS (Optional):
->If you want to use a custom domain for your website, configure the DNS settings to point to your S3 bucket. This typically involves creating a CNAME or alias record that points to the S3 bucket endpoint.
![7](https://github.com/panwar100/host_static_website_on_aws/assets/134361823/4683ae81-6ca5-47db-b5cf-b4cb9004bc15)


