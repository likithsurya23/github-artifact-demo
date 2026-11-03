# GitHub Actions Artifact Upload and Download Demo

This project demonstrates how to pass a text file between two GitHub Actions jobs using artifacts.

## Project structure

```text
github-artifact-demo/
├── .github/
│   └── workflows/
│       └── artifact-demo.yml
└── README.md
```

## Workflow

1. `upload-job` creates `output.txt`.
2. It prints the file and uploads it as `text-file-artifact`.
3. `download-job` waits for `upload-job` using `needs: upload-job`.
4. It downloads the artifact into `downloaded-file/`.
5. It prints the downloaded file using `cat`.

## Run it

1. Create a GitHub repository.
2. Extract this ZIP file.
3. Push the project contents to the repository's `main` branch:

```bash
git init
git add .
git commit -m "Add artifact upload and download workflow"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

4. Open the repository's **Actions** tab.
5. Select **Artifact Upload and Download** and inspect both jobs.

You can also run it manually using **Actions → Artifact Upload and Download → Run workflow**.

## Expected output in Job 2

```text
Artifact downloaded successfully!
Hello from Job 1
This file is uploaded as an artifact.
```
