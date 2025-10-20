# Migration Guide: Moving unit8_part1.ipynb

## Problem
The file `unit8_part1.ipynb` is currently located in the wrong repository:
- **Current (Wrong) Location**: `Camel-light/Assignments/notebooks/unit8/unit8_part1.ipynb`
- **Target (Correct) Location**: `Camel-light/HuggingFace_RL_Course/notebooks/unit8/unit8_part1.ipynb`

## Steps to Move the File

### Step 1: Download the file from the Assignments repository
1. Navigate to: https://github.com/Camel-light/Assignments/blob/main/notebooks/unit8/unit8_part1.ipynb
2. Click the "Raw" button or download the file
3. Save it locally

### Step 2: Add the file to this repository
1. Clone this repository (HuggingFace_RL_Course) if you haven't already:
   ```bash
   git clone https://github.com/Camel-light/HuggingFace_RL_Course.git
   cd HuggingFace_RL_Course
   ```

2. Place the downloaded `unit8_part1.ipynb` file in the correct location:
   ```bash
   # Make sure you're in the repository root
   # Copy the file to: notebooks/unit8/unit8_part1.ipynb
   ```

3. Commit and push the file:
   ```bash
   git add notebooks/unit8/unit8_part1.ipynb
   git commit -m "Add unit8_part1.ipynb to correct repository"
   git push
   ```

### Step 3: Remove the file from the Assignments repository
1. Navigate to the Assignments repository:
   ```bash
   cd /path/to/Assignments
   ```

2. Remove the file:
   ```bash
   git rm notebooks/unit8/unit8_part1.ipynb
   git commit -m "Remove unit8_part1.ipynb (moved to HuggingFace_RL_Course repo)"
   git push
   ```

### Step 4: Verify the README.md links
The README.md in this repository has been updated to point to the correct location. Verify that the link works after adding the file.

## Alternative: Using Git to Preserve History

If you want to preserve the git history of the file, you can use `git format-patch` or `git cherry-pick`:

```bash
# In the Assignments repository, find the commits related to unit8_part1.ipynb
cd /path/to/Assignments
git log --all --full-history -- notebooks/unit8/unit8_part1.ipynb

# Create a patch file
git format-patch -1 <commit-hash> -- notebooks/unit8/unit8_part1.ipynb

# In the HuggingFace_RL_Course repository, apply the patch
cd /path/to/HuggingFace_RL_Course
git am < /path/to/patch-file.patch
```

## After Migration
Once the file is successfully moved:
1. The file will be accessible at: `notebooks/unit8/unit8_part1.ipynb`
2. The README.md will correctly link to this repository
3. The file should be removed from the Assignments repository to avoid confusion
