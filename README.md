# host_static_website_on_aws_uisng_s3_bucket
1.Create an S3 Bucket:
-Log in to your AWS Management Console.
-Go to the S3 service.
-Click the "Create bucket" button.
-Choose a unique and meaningful name for your bucket (e.g., "my-static-website").
-Select the AWS region you prefer.
-Keep the default settings for the rest of the options or configure them as needed.
-Click "Create bucket."

2.Upload Your Website Files:
-In the bucket you just created, click on the "Upload" button.
-Select all the files and folders that make up your static website (HTML, CSS, JavaScript, images, etc.).
-Upload them to your S3 bucket.

3.Configure Bucket Properties:
-Select your bucket and click on the "Properties" tab.
-Enable static website hosting by clicking on "Static website hosting."
-In the "Static website hosting" panel, select the option for "Use this bucket to host a website."
-Enter the name of your main HTML file (e.g., "index.html") as the Index document.
-Optionally, you can also configure error documents for custom error pages.
-Click "Save changes."

4.Set Bucket Permissions:
-Go to the "Permissions" tab.
-In the "Block public access" section, click "Edit" and ensure that public access settings allow your website to be publicly accessible. Typically, this means disabling "Block all public access."
-In the "Bucket policy" section, click "Edit" and add a bucket policy that allows public access to your objects. Here's an example bucket policy:
json
-Copy code
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::my-static-website/*"
        }
    ]
}
-Replace "my-static-website" with your bucket name.
-Click "Save changes."

5.Configure DNS (Optional):
-If you want to use a custom domain for your website, configure the DNS settings to point to your S3 bucket. This typically involves creating a CNAME or alias record that points to the S3 bucket endpoint.

6.Testing:
-After configuring everything, you should be able to access your static website using the S3 bucket's endpoint (e.g., http://my-static-website.s3-website-us-east-1.amazonaws.com) or your custom domain if you set it up.
