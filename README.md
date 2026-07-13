# 📧 Email Inbox Manager with n8n

An automation workflow built with **n8n** that helps manage your Gmail inbox by automatically processing incoming emails.

## Features

- 📥 Monitors incoming Gmail emails
- 🏷️ Categorizes or labels emails
- 📂 Organizes your inbox automatically
- ⚡ Runs on a schedule or in real time
- 🔐 Uses Gmail OAuth2 authentication

---

## Prerequisites

Before running this project, ensure you have:

- Docker Desktop installed
- A Google account
- Google Cloud Project with Gmail API enabled
- Gmail OAuth2 credentials

---

## Run n8n with Docker

Pull the latest n8n image:

```bash
docker pull docker.n8n.io/n8nio/n8n
```

Create and start the container:

```bash
docker run -d \
  --name n8n \
  -p 5678:5678 \
  -v %USERPROFILE%\.n8n:/home/node/.n8n \
  docker.n8n.io/n8nio/n8n
```

Open n8n in your browser:

```
http://localhost:5678
```

---

## Import the Workflow

1. Download or clone this repository.
2. Open n8n.
3. Click **Import from File**.
4. Select the workflow JSON.
5. Save the workflow.

---

## Configure Gmail

Create a Gmail OAuth2 credential in n8n.

Requirements:

- Gmail API enabled
- OAuth Consent Screen configured
- OAuth Client ID and Client Secret
- Redirect URI:

```
http://localhost:5678/rest/oauth2-credential/callback
```

After creating the credential, connect your Gmail account.

---

## Start and Stop n8n

Start:

```bash
docker start n8n
```

Stop:

```bash
docker stop n8n
```

Restart:

```bash
docker restart n8n
```

View logs:

```bash
docker logs -f n8n
```

---

## Data Persistence

All workflows and credentials are stored locally in:

```
%USERPROFILE%\.n8n
```

Your data remains safe even if the container is stopped or restarted.

---

## Project Structure

```
email-inbox-manager/
│
├── README.md
├── workflow.json
└── docker-compose.yml (optional)
```

---

## Technologies Used

- n8n
- Docker
- Gmail API
- Google OAuth2

---

## Notes

- Gmail credentials are **not included** in this repository.
- After importing the workflow, reconnect your own Gmail OAuth2 credential.
- This project is intended for learning and automation purposes.

## License

MIT License
