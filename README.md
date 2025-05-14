# Apple Client Secret Generator

A Node.js utility for generating Apple client secrets used in Sign in with Apple authentication.

## Overview

This tool generates a JWT (JSON Web Token) that serves as a client secret for Apple's authentication system. The generated secret is used in conjunction with Sign in with Apple to authenticate your application with Apple's services.

## Prerequisites

- Node.js installed on your system
- Apple Developer account with the following credentials:
  - Team ID
  - Client ID (Bundle ID)
  - Private Key
  - Key ID

## Installation

1. Clone this repository
2. Install dependencies:

```bash
npm install
```

## Configuration

1. Copy the `.env-example` file to `.env`:

```bash
cp .env-example .env
```

2. Fill in your Apple credentials in the `.env` file:

```
APPLE_CLIENT_ID="your.bundle.id"
APPLE_TEAM_ID="your.team.id"
APPLE_PRIVATE_KEY="your.private.key"
APPLE_KEY_ID="your.key.id"
```

## Usage

Run the script using Node.js:

```bash
node apple-gen-secret.mjs
```

### Command Line Options

You can override the environment variables using command line arguments:

```bash
node apple-gen-secret.mjs --team_id "YOUR_TEAM_ID" --client_id "YOUR_CLIENT_ID" --key_id "YOUR_KEY_ID" --private_key "YOUR_PRIVATE_KEY"
```

### Output

The script will output:

- The generated client secret
- The expiration date of the secret (default: 180 days from generation)

## Environment Variables

| Variable            | Description                                                                       |
| ------------------- | --------------------------------------------------------------------------------- |
| `APPLE_CLIENT_ID`   | Secret ID in Apple's Certificates & Identifiers page (the com.example.app id)     |
| `APPLE_TEAM_ID`     | Your Apple Developer Team ID                                                      |
| `APPLE_PRIVATE_KEY` | Your private key generated in Keys tab in Apple's Certificates & Identifiers page |
| `APPLE_KEY_ID`      | Your key id generated in Keys tab in Apple's Certificates & Identifiers page      |

## Security Notes

- Keep your private key secure and never share it
- The generated client secret is valid for 180 days by default

## License

[Add your license here]
