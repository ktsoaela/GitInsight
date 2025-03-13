
# GitInsight

GitInsight is a CLI tool to analyze Git repositories and provide insights like commit frequency, contributor stats, and more.

## Features
- Commit frequency over time.
- Contributor statistics.
- Commit activity by hour of the day.

## Installation
```bash
pip install -r requirements.txt
```

## Usage
```bash
gitinsight /path/to/repo --commit-frequency --contributor-stats --active-hours
```

## Example Output
### Commit Frequency Over Time
![Commit Frequency](https://via.placeholder.com/600x300.png?text=Commit+Frequency+Graph)

### Contributor Statistics
```
Contributor  Commits
John Doe     10
Jane Smith   5
```

### Commit Activity by Hour of the Day
![Active Hours](https://via.placeholder.com/600x300.png?text=Active+Hours+Graph)

## License
MIT

### Step 8: Test the CLI
Run the CLI tool to analyze a Git repository:

```bash
gitinsight /path/to/repo --commit-frequency --contributor-stats --active-hours
```


# installing Localy

---

### Step 1: Install the Package Locally
Since you’re developing the package locally, you need to install it in "editable" mode. This allows you to make changes to the code without reinstalling it.

1. Navigate to the root of your `GitInsight` project (where `setup.py` is located).
2. Run the following command to install the package in editable mode:
   ```bash
   pip install -e .
   ```

   This will install `GitInsight` and make the `gitinsight` command available in your terminal.

---

### Step 2: Verify Installation
After installing, verify that the `gitinsight` command is available:
```bash
which gitinsight
```
This should output the path to the `gitinsight` executable, e.g., `/path/to/venv/bin/gitinsight`.

---

### Step 3: Run the Command
Now you can run the `gitinsight` command:
```bash
gitinsight . --commit-frequency --contributor-stats --active-hours
```

---

### Step 4: Debugging (If the Issue Persists)
If the command is still not found, follow these steps:

1. **Check `setup.py`**:
   Ensure that the `entry_points` section in `setup.py` is correctly defined:
   ```python
   entry_points={
       'console_scripts': [
           'gitinsight=gitinsight.cli:analyze',
       ],
   },
   ```

2. **Reinstall the Package**:
   Uninstall and reinstall the package:
   ```bash
   pip uninstall GitInsight
   pip install -e .
   ```

3. **Check Your Virtual Environment**:
   Ensure that your virtual environment is activated:
   ```bash
   source venv/bin/activate  # On macOS/Linux
   venv\Scripts\activate      # On Windows
   ```

4. **Check `PATH`**:
   Ensure that your virtual environment’s `bin` (or `Scripts` on Windows) directory is in your `PATH`. You can check this by running:
   ```bash
   echo $PATH
   ```
   If the path to your virtual environment is missing, activate it again.

---

### Step 5: Test with a Sample Repository
If everything is set up correctly, you can now test `GitInsight` on a Git repository. For example:
```bash
gitinsight /path/to/your/repo --commit-frequency --contributor-stats --active-hours
```

---

### Example Output
If you run the command on a repository, you should see:
1. A plot for commit frequency over time.
2. A table of contributor statistics.
3. A bar chart for commit activity by hour of the day.

