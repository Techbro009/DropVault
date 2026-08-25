DropVault — 10 GB file transfer starter

A production-oriented starter for a WeTransfer-style transfer flow: upload up to 10 GB, generate a private link, expire after 12 hours, and optionally email the recipient.

## Run
1. Install Node.js 20+.
2. `npm install`
3. Copy `.env.example` to `.env` and configure an S3-compatible bucket plus SMTP.
4. `npm start`
5. Open `http://localhost:3000`.

## Important production upgrades
- Store transfer metadata in PostgreSQL/Redis instead of the in-memory Map.
- Use S3 lifecycle rules to delete objects after 12 hours.
- Add authentication, rate limiting, virus scanning, abuse controls, encryption, and audit logs.
- For folders, package the folder selection as multiple files in the browser; browsers do not upload a folder as one file.
- Configure CORS on the bucket for browser multipart uploads and expose the `ETag` header.
