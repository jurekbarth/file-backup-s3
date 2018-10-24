# file-backup-s3
An easy way to backup files to s3

## Usage
Docker:
`docker run -e SCHEDULE="@daily" -e S3_ACCESS_KEY_ID=key -e S3_SECRET_ACCESS_KEY=secret -e S3_PREFIX=backup -e S3_BUCKET=my-bucket -v your-local-file-path:/backup jurekbarth/file-backup-s3`

Docker Compose:
```
backups3:
  image: jurekbarth/file-backup-s3
  restart: always
  environment:
    SCHEDULE: '@daily'
    S3_REGION: region
    S3_ACCESS_KEY_ID: key
    S3_SECRET_ACCESS_KEY: secret
    S3_BUCKET: my-bucket
    S3_PREFIX: backup
  volumes:
    - 'your-local-file-path:/backup'
```

## Build container
`docker build -t jurekbarth/file-backup-s3 .`

