# setup 
- conda isntall dvc
- conda install -c conda-forge dvc-ssh
- dvc init (top-level fodler of the repo)
- dvc config core.analytics false
- dvc cache dir path/to/shared_cache 
- dvc remote add -d remote_storage path/to/your/dvc_remote

# Tracking files
- git checkout -b 'tracking_commit_name'
- dvc init
- dvc config core.analytics false
- dvc cache dir path/to/shared_cache 
- dvc remote add -d remote_storage path/to/your/dvc_remote
- dvc add data/raw/trin
- dvc add data/raw/val
- git add --all 
- git commit -m 'tracking files commit'
- dvc push
- git push --set-upstream origin tracking_commit_name


# structure
- -- data/
-   -- prepared/
-   -- raw/
- -- metrics/
- -- model/
- -- src/
-   -- evaluate.py
-   -- prepare.py
-   -- train.py

# remote storage setting
- dvc remote add --default aiforge-storage ssh://10.36.169.226/root/notebooks/groups/KR7150/dvc_repo/exer/dvc
- dvc remote modify aiforge-storage user root
- dvc remote modify aiforge-storage port 30172
- dvc remote modify --local aiforge-storage password aiforge
