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
dvc add data
git add data.dvc .gitignore .dvc .dvcignore
git commit -m "Track data with DVC; keep data/ out of Git"

```

