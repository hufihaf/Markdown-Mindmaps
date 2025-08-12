# Git
## Table of Contents
>[History and Significance](#history-and-significance)  
>  
>[Under the Hood](#under-the-hood)  
>  
>[Capabilities](#capabilities)  
>  
>[Uses](#uses)

## History and Significance
- Created by Linus Torvalds in 2005

- Designed for Linux kernel development
- Response to issues with proprietary source control tools
- Needed to be distributed, fast, and secure

## Under the Hood
- Distributed version control system  
    - Every developer has the full history locally  
- Built on snapshots, not file differences  
    - More efficient than traditional patch-based systems  
- Uses SHA-1 (or SHA-256 in newer versions) for content integrity

## Capabilities
- `git init` — Create a new Git repository from a directory  

- `git clone` — Copy an existing remote repository to your local machine  

- `git add` — Stage file changes to be included in the next commit  

- `git commit` — Save a snapshot of the staged changes to the repository  

- `git status` — Check which files are staged, modified, or untracked  

- `git push` / `git pull` — Sync local changes with a remote repository and vice versa

## Uses
- Version control for software projects  

- Collaboration via platforms like GitHub, GitLab, Bitbucket  
- Backup and restore of code history  
- Track changes to configuration files or documents  
- Manage open source and enterprise-level codebases
