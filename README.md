# runit-app
# RunIt app: shipped, measured and recovered (RunIt Weekend)

A small Python web app, containerised with Docker, deployed by a GitHub Actions pipeline, and run with the basics of reliability engineering.

## Live app
https://YOUR-APP-URL

## Architecture
GitHub push → GitHub Actions (build image, push to GitHub Container Registry, deploy) → Azure Container Apps (or Render) → users.

## SLO
**99.5% of requests to the home page succeed (HTTP 200), measured over 30 days.** That error budget is about 3.6 hours a month. `check.sh` is a quick spot check, not the SLO measurement itself: 20 requests are too few to measure 99.5%, so it raises the alarm when fewer than 19 of 20 succeed.

## Health check
`GET /health` returns `{"status": "ok"}` while the process is running. The Dockerfile's HEALTHCHECK uses it, so `docker ps` shows the container as healthy or unhealthy. It only proves the process answers: the incident drill shows it can stay green while every user gets an error.

## How to deploy
Push to `main`. The workflow in `.github/workflows/deploy.yml` builds, pushes and deploys. To roll back: `git revert <bad commit>` and push.

## Incident drill
I shipped a bad release on purpose, detected it with `check.sh` and the logs, rolled back, and wrote [postmortem.md](postmortem.md). Time to restore: __ minutes.
EOF

<img width="423" height="238" alt="image" src="https://github.com/user-attachments/assets/12915937-4abe-44c4-ac9d-09a1c8b0efbf" />  <img width="389" height="233" alt="image" src="https://github.com/user-attachments/assets/eaaf602c-0170-4af2-81a7-77868426a9a3" />


<img width="344" height="206" alt="image" src="https://github.com/user-attachments/assets/3a89f4a9-67cc-4bc5-8852-bfc5e46ce162" />
<img width="344" height="202" alt="image" src="https://github.com/user-attachments/assets/9dfe2192-5287-413e-b0f1-37fb60b31cb2" />

<img width="370" height="230" alt="image" src="https://github.com/user-attachments/assets/99090f65-8fb5-492d-b02e-d4c7c0534e66" />
<img width="449" height="185" alt="image" src="https://github.com/user-attachments/assets/bd17b5e1-c018-4e9f-b70a-c14793c32f4d" />

<img width="450" height="107" alt="image" src="https://github.com/user-attachments/assets/8020a0be-70d8-4393-81e1-1478427b435d" />
<img width="440" height="173" alt="image" src="https://github.com/user-attachments/assets/ac51a365-64db-4b07-8213-59c47b80df89" />

<img width="451" height="230" alt="image" src="https://github.com/user-attachments/assets/ba1d2fab-e12e-4637-92c1-76be547a2085" />  <img width="444" height="199" alt="image" src="https://github.com/user-attachments/assets/b0912243-f240-4ff3-bc20-2af18f5b76b6" />

<img width="376" height="240" alt="image" src="https://github.com/user-attachments/assets/8a4b91b2-63f9-47d9-8b50-00a97635d58c" /> <img width="383" height="251" alt="image" src="https://github.com/user-attachments/assets/babe5022-7a2f-4262-a753-a037059aaec9" />

<img width="383" height="197" alt="image" src="https://github.com/user-attachments/assets/f6fed980-28f8-4753-bccb-166ae8a0281b" />  <img width="356" height="244" alt="image" src="https://github.com/user-attachments/assets/2509a1ad-7767-4c2d-b39b-a040c38758be" />








