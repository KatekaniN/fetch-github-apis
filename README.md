# Fetch Github Pull Requests

## Description
This Node.js project fetches pull requests from a specified GitHub repository using the GitHub API. It allows filtering PRs by date range and formats the output for easy readability.

## Features
- Fetches pull requests for a given GitHub repository.
- Validates owner and repository before fetching data.
- Supports filtering PRs based on creation, update, close, or merge dates.
- Formats PR data for easier reading.

## Prerequisites
- Node.js installed on your system.
- A GitHub Personal Access Token with necessary repository permissions.

## Installation
1. Clone this repository:
   ```sh
   git clone https://github.com/KatekaniN/fetch-github-apis.git
   cd fetch-github-apis
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Create a `.env` file in the root directory and add your GitHub token:
   ```
   GITHUB_TOKEN=your_personal_access_token
   ```

## Usage
To fetch pull requests for a specific repository:
```javascript
const { getPullRequests } = require("./your-module-file");

const options = {
  owner: "owner_name",
  repo: "repo_name",
  startDate: "YYYY-MM-DD",
  endDate: "YYYY-MM-DD",
};

getPullRequests(options)
  .then((prs) => console.log(prs))
  .catch((error) => console.error(error));
```

## Functions
### `getPullRequests({ owner, repo, startDate, endDate })`
Fetches and filters pull requests based on the provided parameters.

### `validateOwner(owner)`
Checks if the given owner exists on GitHub.

### `validateRepo(owner, repo)`
Ensures the repository exists under the given owner.

### `fetchPullRequests(owner, repo)`
Retrieves all pull requests from the specified repository.

### `filterPullRequests(allPullRequests, startDate, endDate)`
Filters PRs based on creation, update, close, or merge date.

### `formatPullRequests(filteredPRs)`
Formats the pull request data into a readable structure.

## Error Handling
- If an invalid owner or repository is provided, an error message is returned.
- If the GitHub API request fails, an error is thrown with details.

## Testing

Run tests using 
```
npm run test
```