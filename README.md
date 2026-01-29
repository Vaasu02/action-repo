# Action Repo

This repository is configured to send webhook events to the **webhook-repo** Flask application.

## 📋 Purpose

This repository triggers GitHub webhooks on the following actions:

- **Push**: When code is pushed to any branch
- **Pull Request**: When a PR is opened
- **Merge**: When a PR is merged

## 🔧 Webhook Configuration

The webhook is configured to send events to:
- **URL**: `https://your-webhook-repo-url.com/webhook/receiver`
- **Events**: Pushes, Pull Requests

## 🧪 Testing

### Test PUSH Event
```bash
# Make any change and push
echo "test" >> test.txt
git add .
git commit -m "Test push event"
git push
```

### Test PULL_REQUEST Event
```bash
# Create branch and open PR
git checkout -b feature/test-pr
echo "PR test" >> pr-test.txt
git add .
git commit -m "Test PR"
git push -u origin feature/test-pr
# Then open a PR via GitHub UI
```

### Test MERGE Event
- Open a PR as described above
- Merge the PR via GitHub UI

## 📁 Project Structure

```
action-repo/
├── README.md           # This file
└── .gitignore
```

## 🔗 Related Repository

- **webhook-repo**: Contains the Flask application that receives these webhook events

---

Made for the Developer Assessment Task
