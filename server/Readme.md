# Server Configuration Guide

## Base Configuration

```yaml
server:
  port: 80
  env: dev
  region: SG
```

## Database Setup

```yaml
mysql:
  host: localhost
  port: 3306
  username: [YOUR_MYSQL_USER]
  password: [YOUR_MYSQL_PASSWORD]
  db: [YOUR_DATABASE_NAME]
```

## Redis Configuration

```yaml
redis:
  host: [YOUR_REDIS_HOST]
  port: [YOUR_REDIS_PORT]
  username: "default"
  password: [YOUR_REDIS_PASSWORD]
  db: 0
  queueDB: 1
```

> Note: Requires Redis v7.2.7

## Security Configuration

### JWT Settings

```yaml
jwt:
  secret: "3f7b2e9c1a5d8f4b6e0c2a9d7b1e5f8c3d6a0e9b4c7f2d5a8e1b3c6f9d2e7a4"
  algorithms: 'HS256'
```

> Supported algorithms: HS256 (others available in netless-io/flat-server)

### Login Security

```yaml
login:
  salt: "3f7b2e9c1a5d8f4b6e0c2a9d7b1e5f8c3d6a0e9b4c7f2d5a8e1b3c6f9d2e7a4"
```

## Domain Configuration

```yaml
# For development:
website: https://localhost:3000

# For production:
# website: https://flat-web-dev.whiteboard.agora.io
```

## Storage Configuration

### Cloud Storage Limits

```yaml
cloud_storage:
  concurrent: 3
  single_file_size: 524288000  # 500MB
  total_size: 2147483648      # 2GB
  prefix_path: cloud-storage
  allow_file_suffix: [ppt, pptx, doc, docx, pdf, png, jpg, jpeg, gif, mp3, mp4]
```

### User Avatar Settings

```yaml
user:
  avatar:
    size: 5242880  # 5MB
    allow_suffix: [png, jpg, jpeg]
```

## Email Configuration (SMTP)

```yaml
email:
  enable: true
  type: smtp
  smtp:
    host: [YOUR_SMTP_HOST]
    port: [YOUR_SMTP_PORT]
    from: [YOUR_SENDER_EMAIL]
    secure: [true/false]
    auth:
      user: [YOUR_SMTP_USER]
      pass: [YOUR_SMTP_PASSWORD]
```

## Whiteboard Configuration

```yaml
whiteboard:
  app_id: [YOUR_APP_ID]
  access_key: [YOUR_ACCESS_KEY]
  secret_access_key: [YOUR_SECRET_KEY]
  region: "sg"
  convert_region: "sg"
```

---

## Setup Instructions

### Database Setup:

* Create MySQL database and configure credentials in `development.local.yaml`
* Install and configure Redis v7.2.7

### Security Setup:

* Change JWT secret to your own secure value
* Keep login salt for password hashing

### Environment Configuration:

* For development, keep web domain as `localhost:3000`
* Update to production domain when deploying

### Email Service:

* Configure SMTP settings for email login functionality

### Storage Services:

* Configure OSS/cloud storage credentials as needed
* Set appropriate file size limits and allowed types

---

## Important Notes
* Development and production configurations should be separate
* Refer to [netless-io/flat-server](https://github.com/netless-io/flat-server) for advanced configurations
