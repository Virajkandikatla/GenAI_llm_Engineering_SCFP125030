# Upload all notebooks and code to your existing GitHub repository

**GitHub owner:** `Virajkandikatla`  
**Existing repository:** `GenAI_llm_Engineering_SCFP125030`

Your repository can stay named as it is. You do not have to delete or recreate it.

## Option A — upload using the GitHub website (easiest for an empty repository)

1. **Extract** the downloaded `GenAI_LLM_Engineering_SCFP125030_Ready.zip` file.
2. Open the extracted `GenAI_LLM_Engineering_SCFP125030` folder. It should contain `README.md`, `.gitignore`, `Lab3`, `Lab5`, `Lab6`, `Activity_01`, `Activity_02`, and so on.
3. Open [your GitHub repository](https://github.com/Virajkandikatla/GenAI_llm_Engineering_SCFP125030).
4. Click **Add file > Upload files**. If it is completely blank, click **uploading an existing file**.
5. Drag the **contents** of the extracted project folder (the files **and subfolders**) onto the upload screen. Do **not** upload the ZIP itself and do **not** create an extra nested `GenAI_LLM_Engineering_SCFP125030/` folder in the repository.
6. Wait for the upload to populate, check folder paths, enter commit message `Add GenAI and LLM engineering project`, then click **Commit changes** or **Propose changes** (wording may vary by GitHub UI/branch settings).
7. Check that `README.md` and the project folders are visible at the root of your GitHub repository. GitHub's browser uploader supports up to 100 files per upload and 25 MiB per file; this package is below those limits.

**The requested two Activity notebooks are already present:**
- `Activity_01/rnn_text_classification.ipynb`
- `Activity_02/Text Classification with LSTM.ipynb`

## Option B — VS Code PowerShell terminal (recommended)

1. Download `GenAI_LLM_Engineering_SCFP125030_With_2_Notebooks.zip` into your **Downloads** folder.
2. Open your existing cloned repository folder (for example `github-recovery`) in VS Code.
3. Open **Terminal > New Terminal**, choose PowerShell.
4. Check `git status` shows branch `main`. Run these commands:

```powershell
$zip = "$env:USERPROFILE\Downloads\GenAI_LLM_Engineering_SCFP125030_With_2_Notebooks.zip"
$tmp = Join-Path $env:TEMP "genai_upload_scfp125030"
Expand-Archive -LiteralPath $zip -DestinationPath $tmp -Force
Get-ChildItem "$tmp\GenAI_LLM_Engineering_SCFP125030" -Force | Copy-Item -Destination . -Recurse -Force
git status
git add .
git commit -m "Add GenAI LLM exercises and both tutorial notebooks"
git push origin main
```

These commands **add or update** files; they do **not** delete your existing Lab5 and Lab6 files. They replace any repository files with the same paths (for example `README.md` and `.gitignore`), so save local changes first. `git status` lets you review what will be committed. Never commit `.env` or private API keys.

If your VS Code folder is not yet cloned, use:

```powershell
git clone https://github.com/Virajkandikatla/GenAI_llm_Engineering_SCFP125030.git
cd GenAI_llm_Engineering_SCFP125030
```

Then run the extraction-and-commit commands above.

Both separately supplied tutorial files are now included at the repository root: `langchain.ipynb` and `groq_tutorial.ipynb`.

## Optional repository rename

If you want the repository name to be exactly `GenAI_LLM_Engineering_SCFP125030`, open **Settings > General > Repository name > Rename**. Renaming the remote repository is separate from uploading these files.

## Run locally

See the root `README.md`. Install the dependencies, add API keys to a local `.env` (never commit it), and use JupyterLab for `.ipynb` files. The code was statically checked; live Groq/WeatherAPI services and network-dependent training/model downloads cannot be verified without your keys and machine.
