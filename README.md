# Assigned-TUE-10-20-26---Due-MON-10-26-26

# WEEK 2 ASSIGNMENTS

# Group 
## Wolfpak
### Members
#### T.I.Q.S. 3rd3y3 Michael Maximus Uriah_Victorious


**AWS Study Notes: EC2 Instance Types**

Based on your Cloud Vikings transcript, organized in your preferred format.

**1. Main concepts**

| Topic | Short definition | Certification key words |
|---|---|---|
| Amazon EC2 | Provides servers in the AWS cloud to run applications. | Compute, instances, servers |
| Instance type | Defines the instance’s combination of processing power, memory, storage, and networking. | CPU, RAM, storage, network |
| Instance family | Groups instances designed for similar workloads. | General purpose, compute, memory, storage, accelerated |
| Instance generation | Identifies the hardware generation within a family. | Newer hardware, performance |
| Instance size | Determines the amount of resources within an instance family. | large, xlarge, 2xlarge |
| Right sizing | Selecting resources that meet your workload’s needs without excessive unused capacity. | Performance, cost optimization |
| Workload bottleneck | The resource that limits application performance. | CPU-bound, memory-bound, I/O-bound |

**2. EC2 instance families**

| Topic | Short definition | Certification key words |
|---|---|---|
| General purpose — **M** | Balances CPU, memory, and networking for everyday applications. | Balanced resources, application servers, web servers |
| Burstable general purpose — **T** | Provides baseline CPU performance with the ability to handle occasional bursts. | CPU credits, intermittent demand |
| Compute optimized — **C** | Emphasizes CPU resources for heavy processing. | Batch processing, scientific computing, CPU-intensive |
| Memory optimized — **R** | Provides substantial RAM for applications that process large datasets in memory. | In-memory databases, caching, real-time analytics |
| High-memory families — **X, U** | Support workloads requiring exceptionally large amounts of memory. | SAP HANA, large in-memory databases |
| Storage optimized — **I** | Provides fast local SSD storage for frequent reads and writes. | NVMe SSD, high IOPS, low latency |
| Dense storage — **D** | Emphasizes large local HDD capacity and sequential data throughput. | HDD, large datasets, data warehouses |
| GPU accelerated — **P** | Uses GPUs for demanding computational workloads. | Machine learning training, parallel computing |
| Graphics accelerated — **G** | Uses GPUs for graphics workloads and other supported accelerated tasks. | Rendering, virtual workstations, graphics |
| Inference — **Inf** | Uses AWS Inferentia accelerators to run trained machine learning models. | Predictions, inference, Inferentia |
| Training — **Trn** | Uses AWS Trainium accelerators for machine learning training workloads. | Model training, Trainium |
| FPGA — **F** | Provides programmable hardware for specialized processing. | Field-programmable gate array, custom acceleration |

**3. Reading an instance name**

Example: **`m8g.2xlarge`**

| Part | Meaning |
|---|---|
| `m` | General purpose family |
| `8` | Eighth generation of that family |
| `g` | AWS Graviton processor |
| `.2xlarge` | Instance size |

Common suffixes:

| Suffix | Meaning | Study cue |
|---|---|---|
| `g` | AWS Graviton, based on Arm architecture | Check software compatibility |
| `a` | AMD processor | Processor option |
| `i` | Intel processor | Processor option |
| `d` | Local instance store storage | Local disks |
| `n` | Enhanced networking capabilities | Network performance |
| `.metal` | Bare metal size providing direct access to physical server resources | Physical hardware access |

**Remember:** A **G-family** instance and a lowercase **`g` suffix** mean different things. The family identifies the workload category; the suffix identifies Graviton.

**4. Storage and performance**

| Topic | Short definition | Certification key words |
|---|---|---|
| Instance store | Temporary storage physically attached to the instance’s host. | Local storage, temporary data |
| Amazon EBS | Network-attached block storage whose lifecycle can be managed separately from the instance. | Persistent block storage |
| IOPS | Number of storage input/output operations performed per second. | Frequent small reads/writes |
| Throughput | Amount of data transferred over a period of time. | Large transfers, sequential access |
| Latency | Time required to complete an operation. | Response time, delay |
| Replication | Maintaining additional copies of data. | Availability, resilience |
| Backup | Keeping recoverable copies of data. | Recovery, durability |

**Key storage rule:** Instance store data is lost when an instance is stopped or terminated. Keep recoverable copies of important data elsewhere.

**5. Choosing the right instance**

1. Identify what the application needs most: CPU, memory, storage, networking, or specialized hardware.
2. Select the family that matches that need.
3. Check processor and software compatibility.
4. Choose a size based on measured or estimated demand.
5. Test the workload and compare performance.
6. Adjust resources as usage changes.

| Topic | Short definition | Certification key words |
|---|---|---|
| AWS Compute Optimizer | Analyzes usage and recommends resource configurations. | Recommendations, right sizing |
| Benchmarking | Running tests to compare workload performance. | Measurement, performance testing |
| Vertical scaling | Increasing or decreasing the resources of an individual instance. | Scale up/down |
| Horizontal scaling | Increasing or decreasing the number of instances. | Scale out/in |

**6. Practice questions — correct answers only**

| Question | Correct answer |
|---|---|
| Which family provides balanced resources? | **M — General purpose** |
| Which family suits occasional CPU bursts? | **T — Burstable general purpose** |
| Which family suits CPU-intensive batch processing? | **C — Compute optimized** |
| Which family suits large in-memory datasets? | **R — Memory optimized** |
| Which families support exceptionally large memory requirements? | **X and U** |
| Which family emphasizes fast local SSD reads and writes? | **I — Storage optimized** |
| Which family emphasizes dense HDD storage? | **D — Dense storage** |
| Which family is associated with GPU-based model training? | **P** |
| Which family suits graphics rendering and virtual workstations? | **G** |
| Which instances use AWS Inferentia? | **Inf** |
| Which instances use AWS Trainium? | **Trn** |
| Which family provides programmable hardware acceleration? | **F — FPGA** |
| What does the `g` suffix indicate? | **AWS Graviton processor** |
| Which tool recommends instance configurations based on usage? | **AWS Compute Optimizer** |
| What happens to instance store data when the instance is stopped? | **The data is lost** |

**Quick review cues**

- **M = Mixed, balanced resources**
- **T = Temporary CPU bursts**
- **C = CPU**
- **R = RAM**
- **I = I/O performance**
- **D = Dense storage**
- **G = Graphics**
- **Inf = Inference**
- **Trn = Training**
- **F = FPGA**

*The transcript was published in April 2025. Its references to “latest” generations and best price-performance reflect that recording date.*

**Git Notes — Beginner Fundamentals**

Based on *Git Tutorial for Beginners: Learn Git in 1 Hour* by Programming with Mosh.

**1. What Git does**

| Topic | Short definition | Key words |
|---|---|---|
| Git | A version control system that records project history. | Track changes, recover versions, collaborate |
| Repository | The project’s stored Git history and supporting data. | Repo, history, `.git` |
| Distributed version control | Developers can keep repository history locally and make commits offline. | Local history, distributed |
| Working directory | The project files you currently view and edit. | Current files |
| Staging area | The proposed snapshot for your next commit. | Index, prepare changes |
| Commit | A recorded snapshot of tracked project content with a message and metadata. | Checkpoint, snapshot |
| Branch | A separate line of development. | Parallel work |
| `HEAD` | Usually points to the branch you currently have checked out. | Current position |

**Git records versions you commit. It does not automatically save every edit.**

**2. Check and configure Git**

Check whether Git is installed:

```bash
git --version
```

Set your commit author information:

```bash
git config --global user.name "Cassiem Davids"
git config --global user.email "your-email@example.com"
```

Replace the example email with the address you want associated with your commits.

| Command / Setting | Purpose |
|---|---|
| `--global` | Applies the setting to your user account across repositories. |
| `--local` | Applies the setting to the current repository. |
| `--system` | Applies the setting at the system level. |
| `git config --global -e` | Opens your global configuration for editing. |
| `git config --list` | Displays configuration settings. |

Use VS Code as your Git editor, if the `code` command is available:

```bash
git config --global core.editor "code --wait"
```

The `--wait` option makes Git wait until you close the file being edited.

The tutorial’s line-ending settings are:

```bash
# Windows
git config --global core.autocrlf true
```

```bash
# macOS or Linux
git config --global core.autocrlf input
```

**Line-ending cue:** Windows commonly uses **CRLF**; macOS and Linux commonly use **LF**. Follow your project’s line-ending policy when one exists.

**3. Get help**

| Command | Purpose |
|---|---|
| `git config -h` | Shows a short command reference. |
| `git config --help` | Opens detailed documentation. |
| `git add -h` | Shows help for staging files. |
| `git restore -h` | Shows help for restoring files. |

When output opens in a terminal pager:

- **Space** moves forward a page.
- **Q** exits.

**4. Create a repository**

```bash
mkdir git-practice
cd git-practice
git init
git status
```

| Command | Purpose |
|---|---|
| `mkdir git-practice` | Creates a practice folder. |
| `cd git-practice` | Enters the folder. |
| `git init` | Initializes a repository in that folder. |
| `git status` | Shows staged, unstaged, and untracked changes. |
| `ls -a` | Lists entries including the hidden `.git` directory. |

**Keep the `.git` directory:** It contains the local repository’s history and supporting information.

**5. Understand the daily workflow**

**Edit files → Stage selected changes → Review → Commit**

```bash
git status
git add notes.txt
git diff --staged
git commit -m "Add Git study notes"
git status
```

The three areas have different roles:

| Area | What it contains |
|---|---|
| Working directory | Your current edits |
| Staging area | Content selected for the next commit |
| Repository | Previously committed snapshots |

**Important:** If you stage a file and then edit it again, the new edits are unstaged. Run `git add` again to include them.

After a normal commit, the staging area matches the new commit. A clean status means there are no differences to commit.

**6. Create files and stage changes**

These are **Bash commands**:

```bash
echo "Hello" > file1.txt
echo "World" >> file1.txt
```

| Symbol | Meaning |
|---|---|
| `>` | Writes output to a file, replacing existing content. |
| `>>` | Appends output to the end of a file. |

These are **Git commands**:

| Command | Purpose |
|---|---|
| `git add file1.txt` | Stages one file’s current changes. |
| `git add file1.txt file2.txt` | Stages changes in specified files. |
| `git add .` | Stages changes under the current directory, including deletions. |
| `git ls-files` | Lists tracked paths in the index. |

**`git add` stages changes, including modifications and deletions.**

**7. Commit changes**

```bash
git commit -m "Add initial project files"
```

For a longer message, open your configured editor:

```bash
git commit
```

Use a short summary, a blank line, and any useful explanation.

Good commit habits:

- Record meaningful checkpoints.
- Keep each commit focused on one logical task.
- Review staged changes before committing.
- Use specific messages, such as `Fix broken image link`.

Shortcut:

```bash
git commit -am "Fix spelling in study notes"
```

**`-am` automatically stages modifications and deletions of tracked files. It does not add new untracked files.**

**8. Remove, rename, and move files**

| Command | Purpose |
|---|---|
| `rm file2.txt` | Deletes the working file; deletion still needs staging. |
| `git rm file2.txt` | Deletes a tracked working file and stages its removal. |
| `mv file1.txt main.txt` | Renames the working file; changes still need staging. |
| `git mv file1.txt main.txt` | Renames a tracked file and updates the index. |

Example:

```bash
git mv file1.txt main.txt
git commit -m "Rename file1 to main"
```

**Command order:** Source first, destination second.

**9. Ignore files with `.gitignore`**

Create a file named **`.gitignore`** and enter patterns such as:

```gitignore
logs/
bin/
*.log
```

| Pattern | Meaning |
|---|---|
| `logs/` | Ignores matching directories named `logs`. |
| `bin/` | Ignores matching directories named `bin`. |
| `*.log` | Ignores matching filenames ending in `.log`. |
| `# Comment` | Adds an explanatory comment. |

Commit the ignore rules:

```bash
git add .gitignore
git commit -m "Ignore logs and generated files"
```

**Adding a tracked file to `.gitignore` does not stop Git from tracking it.**

To stop tracking a directory while keeping your local copy:

```bash
git rm -r --cached bin/
git add .gitignore
git commit -m "Stop tracking generated bin files"
```

This removes the directory from future snapshots; earlier commits still contain it.

**10. Read short status**

```bash
git status -s
```

For ordinary tracked files, the **first column** describes staged changes; the **second column** describes unstaged changes.

| Output | Meaning |
|---|---|
| ` M notes.txt` | Modified, unstaged |
| `M  notes.txt` | Modification staged |
| `MM notes.txt` | Staged, then modified again |
| `A  notes.txt` | New file staged |
| ` D notes.txt` | Deleted locally, unstaged |
| `D  notes.txt` | Deletion staged |
| `?? notes.txt` | Untracked file |

**11. Review changes**

| Command | Comparison |
|---|---|
| `git diff` | Working directory versus staging area: unstaged edits |
| `git diff --staged` | Staging area versus latest commit: staged changes |
| `git diff --cached` | Same as `git diff --staged` |
| `git difftool` | Opens a configured visual comparison tool. |
| `git difftool --staged` | Opens a visual comparison of staged changes. |

In a text diff:

- **`+`** indicates added lines.
- **`-`** indicates removed lines.

**12. View project history**

| Command | Purpose |
|---|---|
| `git log` | Shows commit history, newest first. |
| `git log --oneline` | Shows a compact history. |
| `git log --oneline --reverse` | Shows compact history, oldest first. |
| `git show HEAD` | Shows the latest commit and its changes. |
| `git show HEAD~1` | Shows the previous commit along the first-parent history. |
| `git show HEAD:notes.txt` | Shows the committed version of a file. |
| `git ls-tree HEAD` | Lists the top-level entries in a commit. |

A commit contains an identifier, author information, a message, and a reference to its project snapshot.

**Branch-name cue:** The tutorial uses `master`; your repository may use `main`.

**13. Unstage changes while keeping your edits**

```bash
git restore --staged notes.txt
```

Unstage changes under the current directory:

```bash
git restore --staged .
```

**Unstaging changes what will enter the next commit. Your working files remain unchanged.** These examples assume the repository already has a commit.

**14. Discard edits or remove untracked files**

Discard unstaged edits in one tracked file:

```bash
git restore notes.txt
```

This replaces the working file with the staged version. **Unstaged edits are lost.**

Preview untracked files and directories that would be removed:

```bash
git clean -nd
```

Remove them only after checking the preview:

```bash
git clean -fd
```

**Git cannot restore untracked content it never recorded.**

**15. Restore a file from an earlier commit**

```bash
git restore --source=HEAD~1 -- notes.txt
```

This copies the file from the previous commit into your working directory. It does not undo the entire commit or automatically commit the restored file.

To record the restoration:

```bash
git add notes.txt
git commit -m "Restore earlier version of notes"
```

**Quick review cues**

| Task | Command |
|---|---|
| Start tracking a project | `git init` |
| Check your work | `git status` |
| Select changes | `git add` |
| Review unstaged edits | `git diff` |
| Review staged changes | `git diff --staged` |
| Save a local checkpoint | `git commit` |
| Browse checkpoints | `git log --oneline` |
| Inspect a checkpoint | `git show` |
| Unstage, keep edits | `git restore --staged` |
| Discard unstaged edits | `git restore` |
| Preview untracked removal | `git clean -nd` |

**Remember: A commit saves work in your local repository. Uploading commits to GitHub is a separate step.**

