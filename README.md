# Issue Templates & Project Integration

This repository contains centralized issue templates and workflows for our organization.

## 🎯 Issue Templates

Issue templates are automatically available in all repositories in our organization. No setup required!

Available templates:
- **Bug Report** - For reporting bugs and issues
- **Enhancement Request** - For requesting new features

## 🔄 Auto-Add to Project Workflow

To automatically add issues to your project board:

### Step 1: Copy the Workflow
1. Copy `.github/workflows/add-to-project.yml` to your repository's `.github/workflows/` folder. Do that to every repo that is connected to your project, so for most cases FE and BE

### Step 2: Update Project Number
Edit the workflow file and change the project number in this line:
```yaml
project-url: https://github.com/orgs/Software-by-Quokka-org/projects/9
```
Your project number is in the URL when viewing your project:
- `https://github.com/orgs/Software-by-Quokka-org/projects/5` → Project number is **5**
- `https://github.com/orgs/Software-by-Quokka-org/projects/12` → Project number is **12**

### Step 3: Add secrets to your repos secret settings
1. **Create the "general" environment**:
   - Settings → Environments → New environment
   - Name: `general`
2. **Add secrets to the environment**:
   - In the general environment, add:
   - `APP_ID`: [Contact admin for id of our Github App, installed on the Software by Quokka Repo]
   - `APP_PRIVATE_KEY`: [Contact admin for .pem file contents, downloaded from the Github App ]

## 📋 Project Numbers Quick Reference

| Repository | Number |
|------------|---------|
| Resume-builder | 9 |
| Feedback-tool | 11 |
| Flexible-model | 12 |

## 🎉 That's It!

Once set up:
1. ✅ Issue templates work automatically
2. ✅ New bug/enhancement issues auto-add to your project
3. ✅ Templates stay in sync when we update them here

## 🔧 Troubleshooting

**"Input required and not supplied: app-id"**
- Check that your environment is named exactly `general`
- Verify both secrets (`APP_ID` and `APP_PRIVATE_KEY`) are added to the environment
- Ensure the workflow includes `environment: general`

**"Could not resolve to a ProjectV2"**
- Double-check your project number in the workflow
- Ensure the GitHub App is installed on your repository

**Issues not being added**
- Verify the issue has either the `bug` or `enhancement` label
- Check the Actions tab in your repository to see if the workflow is running

**Need the App credentials?**
- Contact your team lead or organization admin
- They can provide the APP_ID and download the private key .pem if needed
