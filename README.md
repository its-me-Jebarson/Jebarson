# Jebarson
import requests

def get_repo_info(owner, repo):
    url = f'https://api.github.com/repos/{owner}/{repo}'
    response = requests.get(url)
    
    if response.status_code == 200:
        repo_info = response.json()
        print(f"Repository: {repo_info['name']}")
        print(f"Description: {repo_info['description']}")
        print(f"Owner: {repo_info['owner']['login']}")
        print(f"Stars: {repo_info['stargazers_count']}")
        print(f"Forks: {repo_info['forks_count']}")
        print(f"Open Issues: {repo_info['open_issues_count']}")
    else:
        print(f"Failed to fetch repository information. Status code: {response.status_code}")

if __name__ == "__main__":
    owner = "its-me-Jebarson"
    repo = "Jebarson"
    get_repo_info(owner, repo)
