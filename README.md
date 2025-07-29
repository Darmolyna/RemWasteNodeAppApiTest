# BuildasPostman
## API Test Automation Using Postman & Newman

This repository contains a set of automated API tests written using **Postman**. These tests can be executed either via the **Postman** application or from the command line using **Newman**.

---

## Prerequisites

Ensure the following tools are installed on your system:

- **Node.js** v18 or above  
- **Postman** (Latest version)

---

## Getting Started

### 1. Create and Navigate to a Project Folder

Open your terminal and run:

```bash
mkdir my-postman-project
cd my-postman-project
```

### 2. Clone the Repository

Clone this GitHub repository into the folder and navigate into the cloned directory:

```bash
git clone https://github.com/Darmolyna/RemWasteNodeAppApiTest.git
cd RemWasteNodeAppApiTest
```

---

## Run API Tests

### Option 1: Run Tests from the CLI (Using Newman)

Use the following command to run the tests and generate an HTML report:

```bash
npx newman run "path/to/your/postman_collection.json"   --reporters cli,html   --reporter-html-export newman-reports/report.html
```

> Replace `path/to/your/postman_collection.json` with the actual path to your Postman collection file.

**Example for macOS:**

```bash
npx newman run "/Users/Blessing/Downloads/RemWasteNodeAppApiTest.postman_collection.json"   --reporters cli,html   --reporter-html-export /Users/Blessing/Downloads/newman-reports/report.html
```

### Option 2: Run Tests in the Postman App

1. Open the **Postman** application.
2. Click **Import** (top left).
3. Select the `RemWasteNodeAppApiTest.postman_collection.json` file you cloned from GitHub.
4. Go to the **Collections** tab.
5. Right-click the imported collection and select **Run**.
6. Configure the run settings (e.g., iteration count, environment) and click **Run**.

---

##  Option 3: Run Postman Tests in GitHub Actions CI

### Step 1: Remove Existing Git History

To remove the link to the original GitHub repo:

```bash
rm -rf .git
```

### Step 2: Create a New GitHub Repository

- Go to [GitHub](https://github.com)
- Click the `+` icon (top right) → **New repository**
- Name it (e.g., `my-postman-tests`)
- Click **Create repository**
- **DO NOT** initialize with a README or `.gitignore`

### Step 3: Push Project to New Repo

```bash
git init
git add .
git commit -m "Initial project commit"
```

### Step 4: Add Remote and Push

```bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
git branch -M main
git push -u origin main
```

> Replace `YOUR_USERNAME` and `YOUR_REPO_NAME` with your actual GitHub username and new repository name.

### Step 5: Verify GitHub Actions CI is Working

- Go to your new GitHub repository in the browser.
- Click the **Actions** tab at the top.
- You should see a workflow run triggered by your recent push.

Click on the workflow name to:

- View job steps  
- Check if Postman tests passed or failed  
- Locate the **Upload HTML Report as Artifact** section and click the provided link to download the test report.

---
