# AWS - Boto3

## S3

- When uploading a file, folders are created automatically if they don't exist
- `boto3.resource` vs. `boto3.client`
    - `boto3.resource` provides a high-level, object-oriented interface
    - `boto3.client` is a low-level interface that gives you more control
    - `boto3.resource` does not cover all functionality provided by `boto3.client`