# S3UploaderCLI

## Description
`S3UploaderCLI` is a Bash script designed to upload multiple files from your home directory to a specified AWS S3 bucket. It uploads them to the specified bucket, and generates a temporary pre-signed URL for each uploaded file.

## Prerequisites
Before running this script, ensure the following prerequisites are met:
1. **AWS CLI**: The AWS Command Line Interface (CLI) must be installed and configured on your machine. For installation instructions, visit the [AWS CLI installation guide](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html).

2. **AWS Configuration**: You must have your AWS credentials configured. This can be done using `aws configure` command, which will prompt you to enter your AWS Access Key, Secret Key, region, and output format.

3. **Permissions**: Ensure your AWS IAM user has the necessary permissions to upload files to the S3 bucket and generate pre-signed URLs. The required permissions include:
    - `s3:PutObject`
    - `s3:GetObject`
    - `s3:ListBucket`

## How to Use

1. **Clone the Repository**:
   Clone the repository containing the `cloudUploader` script.
   ```bash
   git clone https://github.com/your-repo/cloudUploader.git
   cd cloudUploader
   ```

2. **Make the Script Executable**:
   ```bash
   chmod +x cloudUploader
   ```

3. **Run the Script**:
   Execute the script by passing the filenames you want to upload as arguments.
   ```bash
   ./cloudUploader.sh file1.txt file2.jpg file3.pdf
   ```

4. **Specify the S3 Bucket**:
   The script will prompt you to specify the S3 bucket where the files will be uploaded.
   ```
   Specify the bucket: your-s3-bucket-name
   ```

## Example

```bash
./cloudUploader.sh document.txt image.png
```
Output:
```
Specify the bucket: my-bucket
Successfully uploaded document.txt file
File link (valid for 10 seconds): https://my-bucket.s3.amazonaws.com/document.txt?AWSAccessKeyId=...
Successfully uploaded image.png file
File link (valid for 10 seconds): https://my-bucket.s3.amazonaws.com/image.png?AWSAccessKeyId=...
```

## Notes
- Ensure the filenames provided as arguments match the files in your home directory.
- The pre-signed URL's short validity is for quick verification; adjust the `--expires-in` parameter as needed for longer access.

By following these instructions, you can effectively use the `cloudUploader` script to manage your file uploads to AWS S3.
