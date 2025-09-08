# test-repository
Test repository for DVC-GD and Github integration

# Steps

1. Clone the repo with Git

2. Create and activate conda image:

```
conda create -n test python=3.10 -y
conda activate test
```

3. Install and init DVC. File .dvcignore and directory .dvc will be automatically created.

```
pip install "dvc[gdrive]"
dvc init
```

4. Track data/ with DVC (and keep it out of Git)

```
git rm -r --cached data
dvc add data
git add data.dvc .gitignore .dvc .dvcignore
git commit -m "Track data with DVC; keep data/ out of Git"

```

5. Create a folder in Google Drive to store data

6. Point DVC to the Google Drive folder

```
dvc remote add -d gdrive gdrive://<FOLDER_ID>  # e.g. FOLDER_ID: 1yyf6Gxgu0YrxNvf_WHoExBZ87MO-T1ct
git add .dvc/config
git commit -m "Configure DVC remote: Google Drive"

```
