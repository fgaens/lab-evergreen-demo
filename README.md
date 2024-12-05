# Dependency Management Example

This repository demonstrates the setup of automated dependency management using GitHub's Dependabot and Evergreen tools.

## Features

- Automated dependency updates for both npm packages and GitHub Actions
- Weekly schedule for checking updates
- Custom labels and commit message formats
- Dependency grouping for development dependencies
- Organization-wide Dependabot setup using Evergreen

## Setup Requirements

1. GitHub repository with Actions enabled
2. Personal Access Token (PAT) with appropriate permissions
3. Repository secrets configured:
   - `EVERGREEN_TOKEN`: PAT for Evergreen to access repositories

## Configuration Details

### Dependabot Setup

The `.github/dependabot.yml` file configures:
- Weekly checks for both npm and GitHub Actions dependencies
- Custom labels for different types of dependencies
- Grouped updates for development dependencies
- Customized commit message formats

### Evergreen Setup

The `.github/workflows/evergreen.yml` workflow:
- Runs daily to check for repositories without Dependabot
- Creates pull requests to add Dependabot configuration
- Excludes specified repositories if needed
- Uses custom labels and base branch configurations

## Usage

1. Clone this repository
2. Update the organization name in `evergreen.yml`
3. Configure the required secrets
4. Push the changes to your repository

The setup will automatically begin monitoring dependencies and creating update pull requests as needed.