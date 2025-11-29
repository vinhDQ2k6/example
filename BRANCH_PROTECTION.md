# Branch Protection Setup Guide

This document explains how to set up branch protection rules for this repository.

## Setting Up Branch Protection Rules in GitHub

### Step 1: Navigate to Repository Settings

1. Go to your repository on GitHub (e.g., `https://github.com/YOUR_USERNAME/YOUR_REPOSITORY`)
2. Click on **Settings** tab
3. In the left sidebar, click on **Branches** under "Code and automation"

### Step 2: Add Branch Protection Rule

1. Click **Add branch protection rule** or **Add rule**
2. In the "Branch name pattern" field, enter `main` (or any branch name you want to protect)

### Step 3: Configure Protection Settings

Enable the following recommended settings:

#### Required Pull Request Reviews
- ✅ **Require a pull request before merging**
  - ✅ Require approvals (set number of required approvals, e.g., 1 or 2)
  - ✅ Dismiss stale pull request approvals when new commits are pushed
  - ✅ Require review from Code Owners

#### Required Status Checks
- ✅ **Require status checks to pass before merging**
  - ✅ Require branches to be up to date before merging
  - Select the status checks that must pass

#### Additional Protection Rules
- ✅ **Require conversation resolution before merging**
- ✅ **Require signed commits** (optional, for extra security)
- ✅ **Require linear history** (optional, prevents merge commits)
- ✅ **Include administrators** (applies rules to admins too)
- ✅ **Restrict who can push to matching branches** (optional)
- ❌ **Allow force pushes** - Keep this **unchecked** for protection
- ❌ **Allow deletions** - Keep this **unchecked** for protection

### Step 4: Save Changes

Click **Create** or **Save changes** to apply the branch protection rule.

## Recommended Protection for `main` Branch

For the `main` branch, we recommend:

| Setting | Recommendation |
|---------|----------------|
| Require pull request | Yes |
| Required approvals | At least 1 |
| Dismiss stale reviews | Yes |
| Require code owner review | Yes |
| Require status checks | Yes (if you have CI/CD) |
| Require linear history | Optional |
| Include administrators | Yes |

## CODEOWNERS File

This repository includes a `.github/CODEOWNERS` file that defines code ownership. When branch protection requires "Code Owner" approval, GitHub will automatically request reviews from the designated owners.

## Additional Resources

- [GitHub Docs: About protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
- [GitHub Docs: Managing branch protection rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule)
- [GitHub Docs: About CODEOWNERS](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)
