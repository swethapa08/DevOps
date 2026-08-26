# 🚀 GitHub Workflows

This directory contains the automated **CI/CD pipelines** and workflows for this project, powered by [GitHub Actions](https://github.com).

---

## 📋 Included Workflows

| Workflow Name | Trigger Event | Description |
| :--- | :--- | :--- |
| **CI Pipeline** | `push`, `pull_request` on `main` | Runs linters, tests, and build checks. |
| **CD Release** | `release` (published) | Packages the application and deploys to production. |
| **Nightly Security** | `schedule` (Cron daily) | Scans dependencies for known vulnerabilities. |

---

## 🛠️ How to Trigger Workflows

### 1. Automatic Triggers
Most workflows run automatically based on git events defined in the `on:` block of each YAML file:
* **Code Pushes:** Merging code to the `main` branch.
* **Pull Requests:** Opening or updating a PR against `main`.

### 2. Manual Triggers
Workflows configured with `workflow_dispatch` can be started manually:
1. Navigate to the **Actions** tab in this GitHub repository.
2. Select the desired workflow from the left sidebar.
3. Click the **Run workflow** dropdown menu.
4. Select the branch and click the green **Run workflow** button.

---

## 🪵 Local Debugging

You can test these GitHub workflows locally before pushing code by using [act](https://github.com).

```bash
# Run the default (push) event workflows locally
act

# Run a specific job
act -j build-and-test
```

---

## 🤝 Contributing
When adding or modifying workflows:
* Place all new `.yml` or `.yaml` files strictly in the `.github/workflows/` directory.
* Always pin third-party actions to a specific commit SHA or explicit version (e.g., `actions/checkout@v4`).
