# JKS app

The research desk for *JK, We're Serious*, served at https://jks.exlorem.com.

This repo holds **code only**. Topics and episodes live as JSON in the private `exlorem/JKS` repo. The page loads them at runtime with each person's own GitHub token, so nothing in this public repo exposes show data.

## Signing in

Each person makes a fine-grained personal access token:

- Resource owner: `exlorem`
- Repository access: only `JKS`
- Permissions: **Contents: Read and write** (nothing else)

The token is kept in the browser (this session, or remembered if you tick the box) and is only sent to `api.github.com`. The page's Content Security Policy blocks connections anywhere else.

## Data

- `data/topics/NNN.json`: one topic per file.
- `data/episodes/NNN.json`: one episode per file. Slots reference topics by id only.
- Episode history and "aired" status are derived from episodes, never stored on topics.
- Every save is a commit by the person who made it. If someone else saved first, the page refuses to overwrite and offers to load their version.
