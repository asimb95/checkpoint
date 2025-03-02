Here is the full `README.md` file in plain text:

---

# Checkpoint - Lightweight Local Code Snapshots

**Checkpoint** is a simple Bash script that allows developers to save and manage temporary snapshots of modified and untracked files in a Git repository **without committing them**. This is useful when you want to save a temporary version of your code and return to it later.

## 🚀 Features
- Create a checkpoint of modified and untracked files.
- List all saved checkpoints.
- Restore a checkpoint to recover previous changes.

## 📥 Installation

1. **Download the script:**
   ```
   curl -o ~/bin/checkpoint https://raw.githubusercontent.com/asimb95/checkpoint/main/checkpoint
   ```

2. **Make it executable:**
   ```
   chmod +x ~/bin/checkpoint
   ```

3. **Ensure it’s in your PATH:**
   ```
   echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc  # or ~/.zshrc for zsh users
   source ~/.bashrc  # or source ~/.zshrc
   ```

## 📌 Usage

### 1️⃣ Save a checkpoint
```
checkpoint commit -m "Refactored API calls"
```
This will:
- Archive all modified and untracked files into a `.zip` file inside `.checkpoints/`.
- Store metadata (message, timestamp, file list) in a `.json` file.

If no message is provided, it will prompt you to enter one.

### 2️⃣ List available checkpoints
```
checkpoint ls
```
Outputs a table with:
- Checkpoint filename
- Number of files
- Message provided

### 3️⃣ Restore a checkpoint
```
checkpoint restore checkpoint-YYYY-MM-DD_HH-MM-SS.zip
```
Extracts the files from the specified checkpoint.

## 🔧 Example Workflow

You're working on a feature branch and have uncommitted changes, but you're unsure if your approach will work. Instead of committing, you save a checkpoint:

```
checkpoint commit -m "New layout is working"
```

After testing, if the approach fails, restore the checkpoint:

```
checkpoint restore checkpoint-2025-03-01_14-30-00.zip
```

This brings back the saved state **without committing anything to Git**.

## 📜 License
This project is licensed under the MIT License.

## ✨ Contributions
Pull requests and improvements are welcome! Open an issue for feature requests or bug reports.

