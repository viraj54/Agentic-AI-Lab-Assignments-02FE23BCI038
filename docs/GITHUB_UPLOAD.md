# GitHub upload instructions

SRN: **02FE23BCI038**

Requested repository URL: **https://github.com/02FE23BCI038/Agentic-AI-Lab-Assignments**

This is the requested target URL, not evidence that the repository already exists. GitHub derives the first path segment from the account or organization that owns the repository. To obtain exactly this URL, that owner must be `02FE23BCI038`.

## Upload with GitHub in your browser

1. Extract the ZIP on your computer. Do not upload the ZIP itself as the submission; GitHub does not unpack ZIP files automatically.
2. Sign into the account that will own the repository. Create a repository named exactly `Agentic-AI-Lab-Assignments`.
3. Open **Add file → Upload files**. Upload the contents of the extracted `Agentic-AI-Lab-Assignments` folder so `README.md`, `labs`, `project`, `docs`, and `tests` appear at the repository root.
4. GitHub browser uploads have a 100-file limit per batch. Upload the root files and then each lab folder or several small batches. Keep folder paths intact. If your browser hides `.github` or `.gitignore`, upload those using Git or GitHub Desktop.
5. Commit the files and verify that all 14 lab folders and the project report appear. Check the Actions tab after `.github/workflows/verify.yml` is present.
6. Open the final repository URL and copy it to the course submission field.

## Upload all files using Git

Open a terminal inside the extracted `Agentic-AI-Lab-Assignments` folder after creating the empty GitHub repository, then run:

```bash
git init
git add .
git commit -m "Add 14 labs, 28 assignments, outputs and integrated course project"
git branch -M main
git remote add origin https://github.com/02FE23BCI038/Agentic-AI-Lab-Assignments.git
git push -u origin main
```

If the repository owner has a different username, replace only the owner segment in the remote URL and submit the actual URL. The SRN remains in the README and reports. Do not force-push into an existing repository with other work.

## Review before submission

Run `python run_all.py` and `python -m unittest discover -s tests -v`. The delivered capture contains 57 successful program runs, 25 independent requirement checks, and 19 passing integrated project evaluation cases. The deliberate mutant in Lab 11 prints expected failing feature tests; its surrounding demonstration passes because that bug correctly blocks release.

GitHub upload limits reference: [Adding a file to a repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository).
