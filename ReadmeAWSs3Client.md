# AWS S3 Client - Readme

## Overview
This service handles interactions with AWS S3 bucket, specifically for:
- Generating pre-signed URLs for file uploads
- Uploading images to the specified S3 bucket path
- Returning the URL of the uploaded image

## Usage
```typescript
const fileURLAWS = await new AWS3Client().uploadFile(file, ticket.ossFilePath);
```
# AWS S3 Client - Readme

## Overview
Handles connections to AWS S3 bucket for secure file uploads via pre-signed URLs.

## Parameters
| Parameter          | Type     | Description |
|--------------------|----------|-------------|
| `file`            | File     | The image file to be uploaded from the whiteboard |
| `ticket.ossFilePath` | String | Destination path in S3 bucket for storage |

## Returns
`String` - URL of the uploaded image

## Implementation Details
```typescript
class AWS3Client {
  /**
   * Uploads file to S3 and returns URL
   * @param file - The file to upload
   * @param path - S3 destination path
   * @returns Promise<string> - File URL
   */
  async uploadFile(file: File, path: string): Promise<string> {
    // 1. Generate pre-signed URL
    // 2. Upload file to S3
    // 3. Return accessible URL
  }
}
```

Important Note

⚠️ Move to backend/server for:

    Enhanced security (AWS credential protection)

    Better upload process control

    Reduced client complexity

    Centralized file management

Dependencies
json

"dependencies": {
  "aws-sdk": "^2.x.x"
}

    AWS SDK for JavaScript

    Proper IAM permissions

    Valid S3 access credentials

Usage Example
typescript

// Client-side usage (temporary)
const awsClient = new AWS3Client();
const imageUrl = await awsClient.uploadFile(
  whiteboardImage, 
  `uploads/${ticketId}/whiteboard.png`
);
