# Bash_Ultimate_Master_Guide.md

> 📘 **The most complete guide to Bash — from zero to expert.**
>
> 🎯 *Who is this for?* Absolute beginners to advanced power users, developers, AI engineers, and system automators.
> ⏱️ *Time to complete:* Self-paced (days to weeks depending on depth)
> 🛠️ *What you'll gain:* Full mastery of Bash scripting, Linux terminal power, and shell automation

---

## Table of Contents

1. [🧠 What is Bash?](#1-what-is-bash-super-simple)
2. [🌍 Why This Exists](#2-why-this-exists)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete System Breakdown](#4-complete-system-breakdown)
5. [🔄 Real-World Workflow](#5-real-world-workflow)
6. [🧪 Hands-on Practice](#6-hands-on-practice)
7. [⚠️ Common Mistakes](#7-common-mistakes)
8. [🔥 Pro Tips & Hidden Tricks](#8-pro-tips--hidden-tricks)
9. [🚀 Advanced Concepts](#9-advanced-concepts-expert-level)
10. [🗺️ Complete Roadmap](#10-complete-roadmap)
11. [🧩 Bonus Deep Insights](#11-bonus-deep-insights)
12. [📌 Summary](#12-summary-quick-revision)

---

## 🧠 1. What is Bash? (Super Simple)

### The 12-Year-Old Explanation

Imagine you have a robot assistant that can do anything on your computer — create files, search for text, download things, run programs, automate repetitive tasks — and all you have to do is **type instructions in plain-ish English**. That robot is called **Bash**.

Bash is a **shell** — a program that reads your text commands and tells the operating system (Linux/macOS) what to do. When you open a terminal and see that blinking cursor, you're talking to Bash. Instead of clicking buttons and menus, you *type* what you want, and Bash makes it happen — instantly.

The real superpower of Bash is **scripting**: you can write a file full of commands, and Bash will run them all automatically, one after another. That's how developers automate boring repetitive work, deploy AI models, manage servers, and process massive amounts of data — all with text.

### Real-Life Analogy

💡 **Think of it like this:**
Imagine giving a very smart intern a notepad full of step-by-step instructions:
1. Go to the folder called "Downloads"
2. Find all files that end in `.log`
3. Delete any file older than 7 days
4. Send me a message saying "Done!"

You wrote those instructions once. Now the intern can follow them every morning without you repeating yourself. That notepad is a **Bash script**. The intern is the **Bash shell**.

### One-Line Definition

> **Bash** is a command-line shell and scripting language for Linux/macOS that lets you control your computer, automate tasks, and build powerful workflows entirely through text commands.

---

## 🌍 2. Why This Exists

### The Problem It Solves

Before shells existed, interacting with a computer required physical switches, punch cards, or binary input. Even after graphical interfaces arrived, they were **too slow and too limited** for power users, developers, and system administrators. You can't click your way through 10,000 files. You can't schedule a task at 3am by dragging icons. You can't deploy a machine learning model with a GUI.

Bash (Born Again SHell) was created in 1989 by Brian Fox for the GNU Project to be a free, improved replacement for the original Bourne Shell (`sh`). It solved the need for a **powerful, programmable, scriptable interface** to the operating system — one that could automate anything a human could manually type.

### Where It's Used in the Real World

| Industry / Area       | How Bash Is Used |
|-----------------------|------------------|
| **AI / ML Engineering** | Automating training runs, managing datasets, deploying models to servers |
| **DevOps / Cloud** | CI/CD pipelines, server provisioning, Docker automation, AWS/GCP scripting |
| **Data Science** | Processing CSV files, running Python scripts in batch, ETL pipelines |
| **Cybersecurity / Kali** | Penetration testing scripts, log analysis, network scanning automation |
| **Web Development** | Build scripts, deployment automation, environment setup |
| **System Administration** | User management, cron jobs, backup automation, monitoring |
| **Bioinformatics** | Processing genome sequence files in bulk, running analysis pipelines |

### Why YOU Should Learn It

1. **Every Linux server runs Bash** — if you want to deploy AI models, use cloud GPUs, or manage a VPS, Bash is non-negotiable.
2. **Automate the boring stuff** — tasks that take you 30 minutes manually can be scripted to run in seconds, forever.
3. **It's the backbone of DevOps** — GitHub Actions, Docker, Kubernetes, and almost every CI/CD tool uses Bash scripts.
4. **Makes you 10x faster as a developer** — navigating, searching, processing files without clicking is dramatically quicker.
5. **AI/ML pipelines depend on it** — dataset preprocessing, model training automation, result collection — all scripted in Bash.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build a solid foundation before going deeper.*

---

### Concept 1: The Terminal and Shell

The **terminal** is the window/application you open to interact with Bash. It's just a visual frame. The **shell** (Bash) is the actual program running inside it that interprets your commands.

When you open a terminal, you see a **prompt** that looks something like:

```
deb@machine:~$
```

- `deb` = your username
- `machine` = your computer's hostname
- `~` = your current directory (tilde means home directory)
- `$` = you're a regular user (`#` means root/admin)

💡 **Example:**
```bash
# Just open a terminal. You'll see the prompt.
# Type this and press Enter:
echo "Hello, Bash!"
# Output: Hello, Bash!
```

---

### Concept 2: Commands and Arguments

Every Bash command follows a pattern:

```
command [options] [arguments]
```

- **command** — the program to run
- **options** — flags that modify behavior (usually start with `-` or `--`)
- **arguments** — the data to work on

💡 **Example:**
```bash
ls                   # List files in current directory
ls -l                # Long format (detailed)
ls -la               # Long format + hidden files
ls -la /home/deb     # Long format of a specific directory
```

---

### Concept 3: Navigating the Filesystem

The Linux filesystem is a tree starting from `/` (root). You move around using these core commands:

| Command | Meaning | Example |
|---------|---------|---------|
| `pwd` | Print Working Directory | `pwd` → `/home/deb` |
| `cd` | Change Directory | `cd Documents` |
| `ls` | List files | `ls -la` |
| `cd ..` | Go up one level | `cd ..` |
| `cd ~` | Go to home | `cd ~` |
| `cd /` | Go to root | `cd /` |
| `cd -` | Go to previous dir | `cd -` |

💡 **Example:**
```bash
pwd             # See where you are
cd /home        # Move to /home
ls              # See what's inside
cd deb          # Move into deb's home
cd ..           # Go back up to /home
```

---

### Concept 4: Working with Files and Directories

```bash
# Creating
touch myfile.txt          # Create empty file
mkdir myfolder            # Create directory
mkdir -p a/b/c            # Create nested directories

# Copying & Moving
cp file.txt backup.txt    # Copy file
cp -r folder/ backup/     # Copy directory recursively
mv file.txt newname.txt   # Move/rename file
mv file.txt ~/Documents/  # Move to different location

# Deleting
rm file.txt               # Delete file
rm -r folder/             # Delete directory recursively
rm -rf folder/            # Force delete (no confirmation — dangerous!)

# Viewing files
cat file.txt              # Print entire file
less file.txt             # Scroll through file (q to quit)
head -n 5 file.txt        # First 5 lines
tail -n 5 file.txt        # Last 5 lines
tail -f app.log           # Live-follow a log file
```

💡 **Example:**
```bash
mkdir my_project
cd my_project
touch README.md main.py
ls
# Output: README.md  main.py
cat README.md
# Output: (empty, since we just created it)
```

---

### Concept 5: Viewing System Information

```bash
whoami          # Print current username
hostname        # Print machine name
date            # Current date and time
uptime          # How long system has been running
uname -a        # Kernel and system info
df -h           # Disk usage (human-readable)
free -h         # RAM usage (human-readable)
top             # Live process viewer (q to quit)
htop            # Better process viewer (if installed)
```

---

### Concept 6: Getting Help

```bash
man ls          # Manual page for 'ls'
ls --help       # Quick help for 'ls'
help cd         # Help for built-in commands
whatis ls       # One-line description
which python3   # Find where a command lives
type ls         # Tell you what 'ls' is
```

---

🧪 **Mini Task 1:**
> Open your terminal. Navigate to your home directory, create a folder called `bash_practice`, go inside it, and create three files: `notes.txt`, `data.csv`, `script.sh`. List all files with detailed info.
> ✅ *Expected outcome:* You see all three files with their sizes and permissions.

🧪 **Mini Task 2:**
> Use `cat` to look inside `/etc/os-release` (it shows Linux version info). Then use `head -n 3` to see only the first 3 lines.

---

## ⚙️ 4. Complete System Breakdown

> 🎯 *Goal: Understand ALL parts of Bash — nothing hidden.*

---

### Part 1: Variables

**What it is:** Named containers that store values.
**Why it matters:** Variables let you write flexible, reusable scripts.
**How it works:** Assign with `=` (no spaces!), read with `$`.

```bash
# Assigning
name="Deb Barman"
age=17
pi=3.14159

# Reading
echo $name           # Deb Barman
echo "My age: $age"  # My age: 17
echo "${name}!"      # Deb Barman! (braces for clarity)

# Command output in a variable
current_dir=$(pwd)
echo "You are in: $current_dir"

# Readonly variable
readonly APP_VERSION="2.0.0"
```

---

### Part 2: Special Variables

Bash has many built-in variables with special meanings:

```bash
$0    # Name of the script itself
$1    # First argument passed to the script
$2    # Second argument
$@    # All arguments as separate words
$#    # Number of arguments
$?    # Exit code of the last command (0 = success)
$$    # PID of the current shell
$!    # PID of the last background process
$HOME # Home directory path
$PATH # Directories searched for commands
$USER # Current username
$SHELL # Path to current shell
```

💡 **Example:**
```bash
echo "Script name: $0"
echo "First arg: $1"
echo "All args: $@"
echo "Arg count: $#"
ls /nonexistent 2>/dev/null
echo "Exit code: $?"   # 2 (error)
ls /home
echo "Exit code: $?"   # 0 (success)
```

---

### Part 3: Input/Output and Redirection

Every process in Linux has three streams:
- **stdin** (0) — standard input
- **stdout** (1) — standard output
- **stderr** (2) — standard error

```bash
# Redirect stdout to file (overwrite)
echo "hello" > output.txt

# Redirect stdout to file (append)
echo "world" >> output.txt

# Redirect stderr to file
ls /bad 2> errors.txt

# Redirect both stdout and stderr
python3 train.py > log.txt 2>&1

# Redirect stderr to /dev/null (suppress errors)
ls /bad 2>/dev/null

# Input from file
sort < unsorted.txt

# Here document (multi-line input)
cat << EOF
Line 1
Line 2
Line 3
EOF
```

---

### Part 4: Pipes (`|`)

**What it is:** Connecting the output of one command to the input of another.
**Why it matters:** Pipes let you chain powerful commands to build complex data processing.

```bash
# Count lines in a file
cat file.txt | wc -l

# Find Python processes
ps aux | grep python

# Sort and remove duplicates
cat names.txt | sort | uniq

# Find 10 largest files
du -h . | sort -rh | head -10

# Real AI pipeline example:
cat dataset.csv | grep "error" | wc -l
```

---

### Part 5: Conditionals (`if` / `elif` / `else`)

```bash
if [ condition ]; then
    # commands
elif [ other_condition ]; then
    # commands
else
    # commands
fi
```

**Test operators:**

| Operator | Meaning |
|----------|---------|
| `-eq` | Equal (numbers) |
| `-ne` | Not equal |
| `-lt` | Less than |
| `-gt` | Greater than |
| `-le` | Less than or equal |
| `-ge` | Greater than or equal |
| `=` | Equal (strings) |
| `!=` | Not equal (strings) |
| `-z` | String is empty |
| `-n` | String is not empty |
| `-f` | File exists and is regular file |
| `-d` | Directory exists |
| `-e` | File/dir exists |
| `-r` | File is readable |
| `-w` | File is writable |
| `-x` | File is executable |

```bash
age=17

if [ $age -ge 18 ]; then
    echo "Adult"
elif [ $age -ge 13 ]; then
    echo "Teenager"
else
    echo "Child"
fi
# Output: Teenager

# File check
if [ -f "model.pkl" ]; then
    echo "Model exists, loading..."
else
    echo "Model not found, training..."
fi
```

---

### Part 6: Loops

**`for` loop:**
```bash
# Loop over a list
for item in apple banana cherry; do
    echo "Fruit: $item"
done

# Loop over files
for file in *.py; do
    echo "Found Python file: $file"
done

# C-style for loop
for ((i=0; i<5; i++)); do
    echo "Step $i"
done

# Loop over a range
for i in {1..10}; do
    echo "Number: $i"
done
```

**`while` loop:**
```bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    ((count++))
done

# Read file line by line
while IFS= read -r line; do
    echo "Line: $line"
done < myfile.txt
```

**`until` loop:**
```bash
x=0
until [ $x -ge 3 ]; do
    echo "x is $x"
    ((x++))
done
```

---

### Part 7: Functions

```bash
# Define a function
greet() {
    local name=$1   # local = variable only exists inside function
    echo "Hello, $name!"
}

# Call the function
greet "Deb"
greet "World"

# Function with return value
add() {
    local result=$(( $1 + $2 ))
    echo $result   # Use echo to "return" values
}

sum=$(add 10 20)
echo "Sum: $sum"   # Sum: 30
```

---

### Part 8: Arrays

```bash
# Declare array
fruits=("apple" "banana" "cherry")

# Access elements (zero-indexed)
echo ${fruits[0]}       # apple
echo ${fruits[2]}       # cherry

# All elements
echo ${fruits[@]}       # apple banana cherry

# Array length
echo ${#fruits[@]}      # 3

# Add element
fruits+=("mango")

# Loop through array
for fruit in "${fruits[@]}"; do
    echo $fruit
done

# Associative array (like Python dict)
declare -A person
person["name"]="Deb"
person["age"]=17
echo ${person["name"]}  # Deb
```

---

### Part 9: String Operations

```bash
str="Hello, World!"

# Length
echo ${#str}                    # 13

# Substring (position, length)
echo ${str:7:5}                 # World

# Replace first occurrence
echo ${str/World/Bash}          # Hello, Bash!

# Replace all occurrences
echo ${str//l/L}                # HeLLo, WorLd!

# Uppercase / Lowercase
echo ${str^^}                   # HELLO, WORLD!
echo ${str,,}                   # hello, world!

# Strip prefix
file="model_v2.pkl"
echo ${file#model_}             # v2.pkl

# Strip suffix
echo ${file%.pkl}               # model_v2

# Default value if unset
echo ${undefined_var:-"default value"}
```

---

### 📊 Full Overview Table

| Component | Purpose | Key Detail |
|-----------|---------|------------|
| Variables | Store data | No spaces around `=` |
| Redirection | Control I/O streams | `>` overwrite, `>>` append |
| Pipes | Chain commands | `cmd1 \| cmd2` |
| if/elif/else | Branching logic | Use `[ ]` or `[[ ]]` for tests |
| for loop | Iterate over items | `for x in list; do ... done` |
| while loop | Repeat while true | `while [ cond ]; do ... done` |
| Functions | Reusable code blocks | Use `local` for local variables |
| Arrays | Store lists | Zero-indexed, `${arr[@]}` for all |
| Strings | Text manipulation | Powerful `${}` expansion syntax |
| Exit codes | Command success/failure | `0` = success, non-zero = error |

---

## 🔄 5. Real-World Workflow

> 🎯 *Goal: See exactly how Bash is used step-by-step in practice.*

---

### 🟢 Beginner Workflow — Writing Your First Script

```
Step 1 → Create a .sh file
Step 2 → Add the shebang line
Step 3 → Write commands
Step 4 → Make it executable
Step 5 → Run it
```

**Explanation of each step:**

1. **Create the file** — `touch myscript.sh` or just open any text editor and save as `.sh`

2. **Shebang line** — The very first line tells Linux which shell to use:
```bash
#!/bin/bash
```

3. **Write your commands:**
```bash
#!/bin/bash
echo "Starting my script..."
name="Deb"
echo "Welcome, $name!"
date
echo "Done!"
```

4. **Make executable** — Without this, Linux won't run it:
```bash
chmod +x myscript.sh
```

5. **Run it:**
```bash
./myscript.sh
# or
bash myscript.sh
```

---

### 🔵 Professional Workflow — Automated ML Training Pipeline

This is how Bash is used in real AI/ML engineering:

```bash
#!/bin/bash
# train_pipeline.sh — Automated ML Training Script
# Author: Deb Barman

set -euo pipefail  # Exit on error, undefined vars, pipe failures

# ─── Configuration ────────────────────────────────────────────────
DATASET_DIR="./data/raw"
OUTPUT_DIR="./models/$(date +%Y%m%d_%H%M%S)"
LOG_FILE="./logs/train_$(date +%Y%m%d).log"
PYTHON="python3"

# ─── Logging function ─────────────────────────────────────────────
log() {
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] $1" | tee -a "$LOG_FILE"
}

# ─── Validation ───────────────────────────────────────────────────
log "Validating environment..."

if [ ! -d "$DATASET_DIR" ]; then
    log "ERROR: Dataset directory not found: $DATASET_DIR"
    exit 1
fi

mkdir -p "$OUTPUT_DIR" "./logs"

# ─── Preprocessing ─────────────────────────────────────────────────
log "Preprocessing dataset..."
$PYTHON preprocess.py --input "$DATASET_DIR" --output "./data/processed" \
    >> "$LOG_FILE" 2>&1

# ─── Training ──────────────────────────────────────────────────────
log "Starting model training..."
$PYTHON train.py \
    --data "./data/processed" \
    --output "$OUTPUT_DIR" \
    --epochs 100 \
    --lr 0.001 \
    >> "$LOG_FILE" 2>&1

# ─── Evaluation ────────────────────────────────────────────────────
log "Evaluating model..."
ACCURACY=$($PYTHON evaluate.py --model "$OUTPUT_DIR/model.pkl" 2>/dev/null)
log "Model accuracy: $ACCURACY"

# ─── Alert ─────────────────────────────────────────────────────────
log "Pipeline complete! Model saved to: $OUTPUT_DIR"
```

**What makes this professional:**
- `set -euo pipefail` for strict error handling
- Timestamped logging to file and console
- Environment validation before starting
- Variables for all configuration (easy to change)
- All output redirected to log files
- Clean exit with meaningful messages

---

## 🧪 6. Hands-on Practice

> 🎯 *Goal: Apply what you've learned through real projects.*

---

### 🟢 Beginner Project: File Organizer Script

**Goal:** Write a script that organizes files in a folder by their extension.
**Estimated Time:** 30–45 minutes
**Skills Used:** Variables, loops, conditionals, mkdir, mv

**Instructions:**

1. Create a folder called `test_org` and put random files in it (`.txt`, `.py`, `.jpg`, `.csv`)
2. Create `organizer.sh`
3. The script should automatically sort files into subfolders by type

```bash
#!/bin/bash
# File Organizer — Beginner Project
# Author: Deb Barman

TARGET_DIR="${1:-.}"  # Use argument or current directory

echo "Organizing files in: $TARGET_DIR"

for file in "$TARGET_DIR"/*; do
    # Skip if it's a directory
    [ -d "$file" ] && continue
    [ ! -f "$file" ] && continue

    # Get file extension (lowercase)
    ext="${file##*.}"
    ext="${ext,,}"

    # Create folder for this extension if it doesn't exist
    dest_dir="$TARGET_DIR/$ext"
    mkdir -p "$dest_dir"

    # Move the file
    filename=$(basename "$file")
    mv "$file" "$dest_dir/$filename"
    echo "  Moved: $filename → $ext/"
done

echo "Done! Your files are organized."
```

**Run it:**
```bash
chmod +x organizer.sh
./organizer.sh /path/to/messy/folder
```

✅ **You've succeeded when:** All files are sorted into subfolders named by their extension (txt/, py/, jpg/, etc.)

---

### 🔵 Intermediate Project: System Health Monitor

**Goal:** A script that checks system health and alerts you if something is wrong.
**Estimated Time:** 1–2 hours
**Skills Used:** Functions, variables, conditionals, command substitution, loops

```bash
#!/bin/bash
# System Health Monitor
# Author: Deb Barman

# ─── Config ──────────────────────────────────────────────────────
CPU_THRESHOLD=80
RAM_THRESHOLD=80
DISK_THRESHOLD=90
LOG_FILE="./health_$(date +%Y%m%d).log"

# ─── Color codes ─────────────────────────────────────────────────
RED='\033[0;31m'
GREEN='\033[0;32m'
YELLOW='\033[1;33m'
NC='\033[0m'  # No Color

# ─── Logging ─────────────────────────────────────────────────────
log() { echo "[$(date '+%H:%M:%S')] $1" | tee -a "$LOG_FILE"; }
alert() { echo -e "${RED}[ALERT] $1${NC}" | tee -a "$LOG_FILE"; }
ok() { echo -e "${GREEN}[OK] $1${NC}"; }

# ─── Check CPU ───────────────────────────────────────────────────
check_cpu() {
    local cpu_usage
    cpu_usage=$(top -bn1 | grep "Cpu(s)" | awk '{print $2}' | cut -d'%' -f1 | cut -d'.' -f1)
    
    log "CPU Usage: ${cpu_usage}%"
    if [ "$cpu_usage" -gt "$CPU_THRESHOLD" ]; then
        alert "CPU usage is HIGH: ${cpu_usage}%"
        return 1
    else
        ok "CPU: ${cpu_usage}%"
        return 0
    fi
}

# ─── Check RAM ───────────────────────────────────────────────────
check_ram() {
    local total used percent
    total=$(free -m | awk '/^Mem:/{print $2}')
    used=$(free -m | awk '/^Mem:/{print $3}')
    percent=$(( used * 100 / total ))
    
    log "RAM Usage: ${percent}% (${used}MB / ${total}MB)"
    if [ "$percent" -gt "$RAM_THRESHOLD" ]; then
        alert "RAM usage is HIGH: ${percent}%"
        return 1
    else
        ok "RAM: ${percent}% (${used}MB used)"
        return 0
    fi
}

# ─── Check Disk ──────────────────────────────────────────────────
check_disk() {
    while IFS= read -r line; do
        local usage mount
        usage=$(echo "$line" | awk '{print $5}' | tr -d '%')
        mount=$(echo "$line" | awk '{print $6}')
        
        if [ "$usage" -gt "$DISK_THRESHOLD" ]; then
            alert "Disk ${mount} is at ${usage}%!"
        else
            ok "Disk ${mount}: ${usage}%"
        fi
    done < <(df -h | tail -n +2 | grep -v "tmpfs")
}

# ─── Check Important Services ────────────────────────────────────
check_service() {
    local service=$1
    if systemctl is-active --quiet "$service" 2>/dev/null; then
        ok "Service $service is running"
    else
        alert "Service $service is NOT running!"
    fi
}

# ─── Main ────────────────────────────────────────────────────────
echo "═══════════════════════════════════"
echo "   System Health Monitor"
echo "   $(date)"
echo "═══════════════════════════════════"

check_cpu
check_ram
check_disk

echo ""
echo "Health check complete. Log: $LOG_FILE"
```

✅ **You've succeeded when:** The script runs, shows color-coded status for CPU, RAM, and disk usage, and logs everything to a file.

---

### 🔴 Advanced Project: Automated AI Dev Environment Setup

**Goal:** A script that sets up a complete Python AI/ML development environment from scratch.
**Estimated Time:** Half a day to refine

```bash
#!/bin/bash
# AI Dev Environment Setup Script
# Author: Deb Barman | Version: 1.0

set -euo pipefail

# ─── Colors & Styles ─────────────────────────────────────────────
CYAN='\033[0;36m'; GREEN='\033[0;32m'; RED='\033[0;31m'; YELLOW='\033[1;33m'; NC='\033[0m'
BOLD='\033[1m'

# ─── Banner ──────────────────────────────────────────────────────
print_banner() {
    echo -e "${CYAN}${BOLD}"
    echo "╔══════════════════════════════════════╗"
    echo "║   AI Dev Environment Installer       ║"
    echo "║   by Deb Barman                      ║"
    echo "╚══════════════════════════════════════╝"
    echo -e "${NC}"
}

# ─── Helpers ─────────────────────────────────────────────────────
step() { echo -e "${CYAN}▶ $1${NC}"; }
success() { echo -e "${GREEN}✓ $1${NC}"; }
warn() { echo -e "${YELLOW}⚠ $1${NC}"; }
error() { echo -e "${RED}✗ $1${NC}"; exit 1; }

check_command() {
    if command -v "$1" &>/dev/null; then
        success "$1 is available"
        return 0
    else
        return 1
    fi
}

# ─── System Update ───────────────────────────────────────────────
update_system() {
    step "Updating system packages..."
    sudo apt-get update -qq && sudo apt-get upgrade -y -qq
    success "System updated"
}

# ─── Python Setup ────────────────────────────────────────────────
setup_python() {
    step "Setting up Python environment..."
    
    check_command python3 || error "Python3 not found. Install it first."
    
    python3 -m pip install --upgrade pip -q
    
    local packages=(
        "numpy" "pandas" "matplotlib" "seaborn"
        "scikit-learn" "torch" "torchvision"
        "fastapi" "uvicorn" "pydantic"
        "langchain" "openai" "anthropic"
        "jupyter" "ipython"
        "black" "flake8" "mypy"
    )
    
    step "Installing Python packages..."
    for pkg in "${packages[@]}"; do
        echo -n "  Installing $pkg..."
        pip install "$pkg" -q && echo -e " ${GREEN}✓${NC}" || echo -e " ${YELLOW}SKIP${NC}"
    done
    
    success "Python AI/ML environment ready"
}

# ─── Create Project Structure ────────────────────────────────────
create_structure() {
    local project_name="${1:-ai_project}"
    step "Creating project structure: $project_name"
    
    mkdir -p "$project_name"/{data/{raw,processed},models,notebooks,src,tests,scripts,logs}
    
    # Create files
    touch "$project_name/README.md"
    touch "$project_name/requirements.txt"
    touch "$project_name/.gitignore"
    
    cat > "$project_name/.gitignore" << 'EOF'
__pycache__/
*.py[cod]
*.egg-info/
.env
venv/
.venv/
data/raw/
models/*.pkl
models/*.pt
logs/
.DS_Store
EOF

    cat > "$project_name/README.md" << EOF
# $project_name

AI/ML Project by Deb Barman

## Structure
\`\`\`
$project_name/
├── data/          # Datasets (raw and processed)
├── models/        # Saved model weights
├── notebooks/     # Jupyter notebooks
├── src/           # Source code
├── tests/         # Unit tests
├── scripts/       # Utility scripts (Bash, Python)
└── logs/          # Training logs
\`\`\`
EOF
    
    success "Project structure created: $project_name/"
}

# ─── Main ────────────────────────────────────────────────────────
main() {
    print_banner
    
    echo "What do you want to set up?"
    echo "1) Full system (update + Python + project)"
    echo "2) Python packages only"
    echo "3) New project structure only"
    read -r -p "Choice [1-3]: " choice
    
    case $choice in
        1)
            update_system
            setup_python
            read -r -p "Project name: " pname
            create_structure "$pname"
            ;;
        2) setup_python ;;
        3)
            read -r -p "Project name: " pname
            create_structure "$pname"
            ;;
        *) error "Invalid choice" ;;
    esac
    
    echo ""
    success "Setup complete! Happy coding, Deb! 🚀"
}

main "$@"
```

🔥 **Challenge:** Extend this script to also set up a virtual environment (`venv`), install packages inside it, and generate a `requirements.txt` automatically.

---

## ⚠️ 7. Common Mistakes

> 🎯 *Goal: Avoid the traps that catch 90% of beginners.*

---

### ❌ Mistake 1: Spaces Around `=` in Variable Assignment

**Why it happens:** Looks like math, where spaces are fine.
**What goes wrong:** Bash treats it as a command with arguments.

```bash
# ❌ Wrong way:
name = "Deb"
# Error: command not found: name

# ✅ Right way:
name="Deb"
```

**The Fix:** Never put spaces around `=` when assigning variables.

---

### ❌ Mistake 2: Forgetting to Quote Variables

**Why it happens:** Variables seem to work without quotes in simple cases.
**What goes wrong:** When the value contains spaces or special characters, it breaks.

```bash
# ❌ Wrong way:
filename="my file.txt"
cat $filename
# Error: No such file: my (Bash splits on spaces!)

# ✅ Right way:
cat "$filename"
```

**The Fix:** Always double-quote variables: `"$variable"`. Use `"${variable}"` when adjacent to other text.

---

### ❌ Mistake 3: Using `=` for Number Comparison

**Why it happens:** Works in other languages.
**What goes wrong:** `=` compares strings, not numbers.

```bash
# ❌ Wrong way:
num=10
if [ $num = 10 ]; then echo "ten"; fi  # Technically works but is misleading
if [ $num = 9+1 ]; then echo "ten"; fi  # WRONG, compares string "9+1"

# ✅ Right way:
if [ $num -eq 10 ]; then echo "ten"; fi
```

**The Fix:** Use `-eq`, `-ne`, `-lt`, `-gt`, `-le`, `-ge` for number comparisons. Use `=` and `!=` for strings.

---

### ❌ Mistake 4: Using `rm -rf` Carelessly

**Why it happens:** Beginners copy commands from the internet without understanding.
**What goes wrong:** You can delete your entire home directory or operating system. This cannot be undone.

```bash
# ❌ CATASTROPHICALLY WRONG:
rm -rf /          # Deletes everything on the system
rm -rf $MYDIR/    # If MYDIR is empty, this becomes rm -rf /

# ✅ Right way:
# 1. Always check what you're deleting first
ls "$target_dir"

# 2. Set nounset to catch empty variables
set -u

# 3. Verify the path before deleting
echo "About to delete: $target_dir"
read -p "Are you sure? (y/N) " -n 1 -r
if [[ $REPLY =~ ^[Yy]$ ]]; then rm -rf "$target_dir"; fi
```

---

### ❌ Mistake 5: Not Handling Errors

**Why it happens:** Scripts seem to work fine — until they don't.
**What goes wrong:** A failed command is silently ignored, and subsequent commands run on bad data.

```bash
# ❌ Wrong way:
cp config.txt /tmp/
process_config /tmp/config.txt   # Runs even if copy failed!

# ✅ Right way — Option 1: Check exit code
cp config.txt /tmp/
if [ $? -ne 0 ]; then
    echo "Copy failed!"
    exit 1
fi

# ✅ Right way — Option 2: Use set -e at top of script
set -e  # Exit immediately on error
```

---

### ❌ Mistake 6: Missing the Shebang Line

**Why it happens:** The file just has commands, which seems like enough.
**What goes wrong:** The system doesn't know which shell to use; behavior becomes undefined.

```bash
# ❌ Wrong way:
echo "Hello"   # (no shebang — might run with sh, dash, or something else)

# ✅ Right way:
#!/bin/bash
echo "Hello"
```

---

### ❌ Mistake 7: Using `[ ]` vs `[[ ]]` Incorrectly

**Why it happens:** They look the same.
**What goes wrong:** `[ ]` is POSIX `test` with limited functionality; `[[ ]]` is Bash-specific and much safer.

```bash
# ❌ Risky with [ ]:
if [ $string == "" ]; then ...   # Can fail if $string is unset

# ✅ Prefer [[ ]] in Bash scripts:
if [[ $string == "" ]]; then ...       # Safe
if [[ $string =~ ^[0-9]+$ ]]; then ... # Regex support!
if [[ -f file && -r file ]]; then ...  # Logical && inside
```

---

### ❌ Mistake 8: Forgetting `chmod +x`

```bash
# ❌ Wrong:
./myscript.sh
# Permission denied

# ✅ Right:
chmod +x myscript.sh
./myscript.sh
```

---

## 🔥 8. Pro Tips & Hidden Tricks

> 🎯 *Goal: Level up with knowledge most tutorials never share.*

---

### 💎 Tip 1: Use `set -euo pipefail` in Every Script

This single line at the top of your script makes it dramatically safer:

```bash
set -euo pipefail
```

- `e` — Exit immediately if any command fails (non-zero exit code)
- `u` — Treat unset variables as errors (catches typos like `$DIIR` instead of `$DIR`)
- `o pipefail` — If any command in a pipeline fails, the whole pipeline fails

Without this, a script can silently continue after errors, producing garbage results.

---

### 💎 Tip 2: Use `trap` to Clean Up on Exit

```bash
#!/bin/bash
set -euo pipefail

TEMP_DIR=$(mktemp -d)

# This runs no matter how the script exits (normal, error, or Ctrl+C)
trap "rm -rf '$TEMP_DIR'" EXIT

# Do work in temp dir
cp data.csv "$TEMP_DIR/"
process "$TEMP_DIR/data.csv"
```

`trap` ensures cleanup always happens — even if the script crashes.

---

### 💎 Tip 3: Process Substitution — Use Commands Anywhere a File is Expected

```bash
# Compare outputs of two commands without temp files
diff <(ls dir1/) <(ls dir2/)

# Read output of a command as if it were a file
while IFS= read -r line; do
    echo "Processing: $line"
done < <(find . -name "*.py")
```

---

### 💎 Tip 4: Background Jobs and Parallelism

```bash
# Run a command in background
python3 train.py &
python3 evaluate.py &

# Wait for ALL background jobs to finish
wait
echo "Both scripts done!"

# Run with limited parallelism using GNU parallel
ls *.wav | parallel -j4 ffmpeg -i {} {.}.mp3
```

---

### 💎 Tip 5: Powerful `find` Command

```bash
# Find files by extension
find . -name "*.py" -type f

# Find files modified in last 24 hours
find . -mtime -1

# Find files larger than 100MB
find . -size +100M

# Execute a command on each found file
find . -name "*.log" -exec rm {} \;

# Or with xargs (faster for many files)
find . -name "*.log" | xargs rm

# Find and grep in one line
find . -name "*.py" -exec grep -l "import torch" {} \;
```

---

### 💎 Tip 6: `awk` — The Data Processing Powerhouse

```bash
# Print specific column from CSV
awk -F',' '{print $2}' data.csv

# Sum a column
awk -F',' '{sum += $3} END {print "Total:", sum}' data.csv

# Filter rows where column 2 > 100
awk -F',' '$2 > 100' data.csv

# Print line count per file (like wc -l for multiple)
awk 'END {print FILENAME, NR}' *.txt
```

---

### 💎 Tip 7: `sed` — Stream Editor for Text Transformation

```bash
# Replace text in file (in-place with backup)
sed -i.bak 's/old_text/new_text/g' config.txt

# Delete lines matching pattern
sed -i '/^#/d' script.sh   # Remove comment lines

# Print specific lines (e.g., lines 10-20)
sed -n '10,20p' bigfile.txt

# Add text after matching line
sed '/model_path/a\    checkpoint_dir = "./checkpoints"' config.py
```

---

### 💎 Tip 8: Logging with Timestamps and Colors

```bash
#!/bin/bash
# Production-grade logging system

readonly LOG_FILE="./app.log"

log() {
    local level=$1; shift
    local msg="$@"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    
    case $level in
        INFO)  color='\033[0;32m' ;;  # Green
        WARN)  color='\033[1;33m' ;;  # Yellow
        ERROR) color='\033[0;31m' ;;  # Red
        DEBUG) color='\033[0;36m' ;;  # Cyan
        *)     color='\033[0m'    ;;
    esac
    
    # Print to terminal with color
    echo -e "${color}[${timestamp}] [${level}] ${msg}\033[0m"
    # Log to file without color codes
    echo "[${timestamp}] [${level}] ${msg}" >> "$LOG_FILE"
}

log INFO "Application started"
log WARN "Low disk space"
log ERROR "Database connection failed"
```

---

### 💎 Tip 9: Use `jq` for JSON Processing in Bash

```bash
# Install: sudo apt install jq

# Parse JSON from API
curl -s "https://api.github.com/users/deb-barman166" | jq '.name'
curl -s "https://api.github.com/users/deb-barman166" | jq '.public_repos'

# Extract from complex JSON
echo '{"models": [{"name": "gpt4", "score": 0.95}]}' | \
    jq '.models[0].name'

# Process JSON file
jq '.results[] | select(.accuracy > 0.9)' results.json
```

---

### 💎 Tip 10: Bash `history` Tricks

```bash
!!          # Repeat last command
!ls         # Repeat last command starting with 'ls'
!$          # Last argument of previous command
!*          # All arguments of previous command
Ctrl+R      # Reverse search through history
history | grep "docker"   # Search history
```

---

### 🛠️ Recommended Tools & Resources

| Tool / Resource | What It's For | Notes |
|----------------|---------------|-------|
| `shellcheck` | Lint and debug Bash scripts | `sudo apt install shellcheck` |
| `bat` | Better `cat` with syntax highlighting | `sudo apt install bat` |
| `fzf` | Fuzzy finder for history and files | Incredible for navigation |
| `tmux` | Terminal multiplexer (multiple panes) | Essential for remote servers |
| `ripgrep (rg)` | Blazing fast `grep` | `sudo apt install ripgrep` |
| `jq` | JSON processor for APIs | `sudo apt install jq` |
| GNU Parallel | Run commands in parallel | `sudo apt install parallel` |
| Bash Manual | Official documentation | `man bash` |
| ExplainShell.com | Explains any command | Website |
| BashGuide (mywiki.wooledge.org) | Best free Bash guide | Website |

---

## 🚀 9. Advanced Concepts (Expert Level)

> 🎯 *Goal: Go deep into the internals and advanced techniques.*

---

### Advanced Concept 1: Process Management and Signals

```bash
# List running processes
ps aux | grep python

# Kill a process by PID
kill 12345          # Send SIGTERM (polite)
kill -9 12345       # Send SIGKILL (force — no cleanup)
kill -SIGTERM 12345 # Same as kill 12345

# Kill by name
pkill -f "python train.py"
killall python3

# Background/foreground
python3 server.py &    # Run in background
jobs                   # List background jobs
fg %1                  # Bring job 1 to foreground
bg %1                  # Send paused job to background
Ctrl+Z                 # Pause current process
Ctrl+C                 # Interrupt (send SIGINT)

# Trap signals in scripts
trap 'echo "Caught SIGINT, cleaning up..."; cleanup; exit 1' INT TERM
```

---

### Advanced Concept 2: Here Documents and Here Strings

```bash
# Here Document — multi-line input to a command
cat << 'EOF'
This is line 1
This is line 2
Variables like $HOME are NOT expanded with quoted delimiter
EOF

cat << EOF
Variables ARE expanded here: $HOME
User: $USER
EOF

# Here Document to create files
cat > config.yaml << EOF
model:
  name: resnet50
  epochs: 100
  lr: 0.001
dataset:
  path: $DATASET_PATH
EOF

# Here String — pass a string as stdin
grep "error" <<< "$log_output"
```

---

### Advanced Concept 3: Coprocesses and Advanced Pipes

```bash
# Named pipes (FIFO) — communication between processes
mkfifo /tmp/mypipe
cat /tmp/mypipe &    # Reader in background
echo "data" > /tmp/mypipe  # Writer
rm /tmp/mypipe

# Coprocesses — bidirectional pipes (Bash 4+)
coproc DB { sqlite3 mydb.db; }
echo ".tables" >&${DB[1]}
read output <&${DB[0]}
echo "Tables: $output"

# Subshell — isolated environment
(
    cd /tmp
    export TEMP_VAR="only visible here"
    ls
)
# Back to original directory, TEMP_VAR is gone
```

---

### Advanced Concept 4: Advanced Parameter Expansion

```bash
# Conditional expansion
var="hello"
echo ${var:-"default"}    # Use default if var is unset or empty
echo ${var:="default"}    # Set and use default if unset
echo ${var:+"found"}      # Use "found" only if var is SET
echo ${var:?"Error: var must be set"}  # Error if unset

# Indirect expansion (variable variable)
user_type="admin"
admin_password="secret123"
echo ${!user_type}_password  # Prints value of $admin_password

# Array slicing
arr=(a b c d e f)
echo ${arr[@]:2:3}    # c d e (start at index 2, take 3 elements)

# Pattern-based removal
path="/home/deb/project/main.py"
echo ${path%/*}       # /home/deb/project (remove shortest suffix matching /*)
echo ${path%%/*}      # (empty — remove longest suffix matching /*)
echo ${path#*/}       # home/deb/project/main.py (remove shortest prefix)
echo ${path##*/}      # main.py (remove longest prefix — just filename)
```

---

### Advanced Concept 5: `eval` and Dynamic Command Construction

```bash
# eval — interpret a string as a command (use with extreme caution)
cmd="ls -la /home"
eval "$cmd"

# Dynamic variable names
for i in 1 2 3; do
    declare "model_$i=result_$i"
done
echo $model_1   # result_1
echo $model_2   # result_2

# Building commands dynamically (safely)
build_python_cmd() {
    local cmd="python3 train.py"
    [[ -n "$GPU" ]] && cmd+=" --gpu $GPU"
    [[ -n "$EPOCHS" ]] && cmd+=" --epochs $EPOCHS"
    cmd+=" --output $OUTPUT_DIR"
    echo "$cmd"
}

full_cmd=$(build_python_cmd)
echo "Running: $full_cmd"
eval "$full_cmd"
```

---

### Advanced Concept 6: `select` Menu and Interactive Scripts

```bash
#!/bin/bash
# Interactive menu with select

PS3="Enter your choice: "

options=("Train Model" "Evaluate Model" "Deploy Model" "View Logs" "Quit")

select opt in "${options[@]}"; do
    case $opt in
        "Train Model")   python3 train.py ;;
        "Evaluate Model") python3 evaluate.py ;;
        "Deploy Model")  bash deploy.sh ;;
        "View Logs")     tail -f app.log ;;
        "Quit")          echo "Goodbye!"; break ;;
        *) echo "Invalid option: $REPLY" ;;
    esac
done
```

---

### Advanced Concept 7: Script Modularity with `source`

```bash
# utils.sh — reusable functions library
log_info() { echo "[INFO] $1"; }
log_error() { echo "[ERROR] $1" >&2; exit 1; }
check_dependency() {
    command -v "$1" &>/dev/null || log_error "Required: $1 (not installed)"
}

# main.sh — uses the library
source ./utils.sh    # or: . ./utils.sh

check_dependency python3
check_dependency ffmpeg
log_info "All dependencies found"
```

---

### ⚡ Performance & Optimization

| Optimization Technique | Impact | When to Use |
|------------------------|--------|-------------|
| Use `[[ ]]` over `[ ]` | Medium | Always in Bash scripts |
| Avoid subshells in loops | High | When loops run thousands of times |
| Use `read` instead of `cat` | Medium | Reading files line by line |
| Use arrays instead of many variables | Medium | Handling collections |
| Prefer built-ins over external commands | High | `echo` > `/bin/echo`, string ops over `sed` |
| Use `mapfile`/`readarray` | High | Loading file into array |
| Pipe to `xargs -P` for parallelism | Very High | CPU-bound file processing |
| `time` to profile slow scripts | — | Debugging performance issues |

```bash
# Fast: use bash built-in
length=${#string}

# Slow: spawn external process
length=$(echo -n "$string" | wc -c)

# Fast: read file into array in one operation
mapfile -t lines < myfile.txt

# Slow: loop + read each line with subshell
lines=()
while IFS= read -r line; do lines+=("$line"); done < myfile.txt

# Parallel processing
find . -name "*.py" | xargs -P8 -I{} black {}
```

---

## 🗺️ 10. Complete Roadmap

> 🎯 *Goal: Know exactly what to learn and in what order.*

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1–2)
├── Day 1–2:   Terminal basics, navigation (cd, ls, pwd, mkdir, rm)
├── Day 3–4:   File operations (cat, less, cp, mv), viewing system info
├── Day 5:     Redirection (>, >>, 2>, /dev/null), pipes (|)
├── Day 6:     Your first script (shebang, chmod +x, variables, echo)
└── Day 7:     Mini project: File organizer script

PHASE 2 — CORE SCRIPTING (Week 3–4)
├── Day 8–9:   Conditionals (if/elif/else), test operators
├── Day 10–11: Loops (for, while, until), loop control (break, continue)
├── Day 12:    Functions, local variables, return values
├── Day 13:    Arrays, associative arrays, string operations
└── Day 14:    Intermediate project: System health monitor

PHASE 3 — POWER USER (Week 5–6)
├── Week 5:    Text processing: grep, sed, awk, sort, uniq, cut, tr
│              Process management: ps, kill, jobs, bg, fg, nohup
├── Week 6:    find command mastery, xargs, GNU parallel
│              Networking: curl, wget, ssh, scp, rsync
└── Project:   Full deployment automation script

PHASE 4 — ADVANCED MASTERY (Week 7–8)
├── Week 7:    Advanced parameter expansion, heredocs
│              Coprocesses, named pipes, signal handling
│              Debugging (bash -x, set -x, shellcheck)
├── Week 8:    Script libraries, modular design (source)
│              Environment management, PATH manipulation
│              Cron jobs, systemd timers
└── Project:   Complete AI pipeline automation framework

PHASE 5 — EXPERT & SPECIALIZATION (Month 3+)
├── Bash + Python integration patterns
├── Bash for Kubernetes, Docker, and cloud CLI
├── Writing portable scripts (POSIX compatibility)
├── Performance optimization for large-scale processing
└── Contributing to open source shell projects
```

---

### 🏁 Milestone Checklist

- [ ] I understand the core concepts of Bash (variables, loops, conditionals)
- [ ] I can explain what a pipe does and give an example
- [ ] I completed the beginner File Organizer project
- [ ] I completed the intermediate System Health Monitor project
- [ ] I can write a Bash function with local variables and return a value
- [ ] I understand how redirection works (stdout, stderr, stdin)
- [ ] I can use `grep`, `sed`, and `awk` for text processing
- [ ] I've applied `set -euo pipefail` and `trap` in a real script
- [ ] I understand and use `[[ ]]` instead of `[ ]`
- [ ] I've automated a real task in my development workflow with Bash

---

## 🧩 11. Bonus Deep Insights

> 🎯 *Things most people spend years figuring out — here upfront.*

---

### 🔮 Mental Model: Everything is a Stream

The most powerful mental model in Bash: **everything is just text flowing through pipes**. There are no "objects", no complex data structures (mostly), no type systems. Just bytes flowing from one place to another.

Once you internalize this, you can compose any command with any other. A web API output, a file, another program's terminal output — they're all just streams. You intercept them, transform them, and redirect them. This is why Bash scripts that combine `curl | jq | grep | awk | sort | head` can do incredibly sophisticated data processing in a single line.

---

### 🤫 Secret 1: `$()` Creates a Subshell — and That Has a Cost

Every time you write `$(command)`, Bash forks a child process, runs the command, captures its output, and returns it. This is cheap for occasional use, but in a tight loop running thousands of iterations, it becomes a performance bottleneck. The fix is to use Bash built-ins, parameter expansion, and `mapfile` wherever possible.

```bash
# Slow (spawns subshell each iteration):
for i in {1..10000}; do
    length=$(echo -n "$str" | wc -c)
done

# Fast (built-in, no subshell):
for i in {1..10000}; do
    length=${#str}
done
```

---

### 🤫 Secret 2: Exit Codes are the API of Bash Programs

In Bash, programs communicate success or failure through **exit codes** — not return values, not print statements. Exit code `0` means success. Anything else means failure. Every conditional in Bash (`if`, `while`, `&&`, `||`) is checking exit codes.

```bash
# These are equivalent:
if grep -q "error" log.txt; then echo "found"; fi
grep -q "error" log.txt && echo "found"

# You can build chains of dependent commands:
git pull && python3 train.py && python3 deploy.py && echo "All steps passed!"
# If ANY step fails, the chain stops
```

---

### 🤫 Secret 3: `shellcheck` Will Teach You More Than Tutorials

Install `shellcheck` right now:
```bash
sudo apt install shellcheck
```

Then run it on every script you write:
```bash
shellcheck myscript.sh
```

It catches quoting issues, undefined variables, bad comparisons, and dozens of other common bugs — with explanations. It's like having a senior developer review your code instantly.

---

### 🤫 Secret 4: Bash is Available Everywhere — That's Its Real Power

Python might not be installed. Node.js might not be installed. But `/bin/bash` exists on virtually every Linux system ever made, every macOS machine, and now even Windows (via WSL). Scripts you write today will run on cloud servers, containers, embedded devices, and CI/CD systems without any setup. That portability is the real reason Bash is worth mastering.

---

### 🧠 The Big Picture

Bash sits at the intersection of **every tool in the Linux ecosystem**. It doesn't compete with Python for complex logic — it orchestrates everything Python can't easily do: managing processes, connecting programs, handling the OS, automating the environment. When you train a deep learning model, Bash is setting up the environment, moving data, launching the Python process, capturing logs, and alerting you when done. When you deploy a web service, Bash scripts are starting containers, configuring nginx, setting environment variables, and running health checks.

**Bash is the glue of modern software engineering.** The more you master it, the more you can automate — and the more time you free up to focus on what actually matters: building intelligent systems.

---

## 📌 12. Summary (Quick Revision)

> 🎯 *Everything important — at a glance.*

---

### Core Concepts (1-line each)

| Concept | What It Means |
|---------|--------------|
| Shell | Program that interprets your text commands to the OS |
| Variable | `name="Deb"` — no spaces around `=`, read with `$name` |
| Redirection | `>` (overwrite), `>>` (append), `2>` (stderr), `<` (stdin) |
| Pipe | `\|` — send output of one command as input to another |
| if/else | `if [ condition ]; then ... elif ...; else ...; fi` |
| for loop | `for item in list; do ... done` |
| while loop | `while [ condition ]; do ... done` |
| Function | `myfunc() { local x=$1; echo $x; }` — call with `myfunc arg` |
| Exit code | `0` = success, non-zero = error, check with `$?` |
| Shebang | `#!/bin/bash` — first line of every script |
| chmod +x | Makes a script executable before running with `./script.sh` |
| `set -euo pipefail` | Safety triple: exit on error, catch undefined vars, pipe failures |

---

### The 5 Things to Remember

1. ✅ **Always quote your variables** — `"$var"` not `$var`, to handle spaces and special chars
2. ✅ **Check exit codes** — use `set -e` or explicit `if [ $? -ne 0 ]` checks
3. ✅ **Never use `rm -rf` without confirmation** — one typo can be catastrophic
4. ✅ **Pipes are your superpower** — chain small focused commands into powerful pipelines
5. ✅ **Use `shellcheck`** — it catches 80% of bugs before you run the script

---

### Quick Reference Cheat Sheet

```bash
# ─── NAVIGATION ───────────────────────────────────────────────────
pwd                    # Show current directory
cd ~/Documents         # Go to Documents
ls -la                 # List all files with details
cd -                   # Go to previous directory

# ─── FILE OPERATIONS ──────────────────────────────────────────────
touch file.txt         # Create empty file
mkdir -p a/b/c         # Create nested directories
cp -r src/ dst/        # Copy directory
mv old.txt new.txt     # Rename/move
rm -rf folder/         # Delete directory (careful!)

# ─── VARIABLES ────────────────────────────────────────────────────
name="Deb"             # Assign (no spaces!)
echo "$name"           # Read
result=$(cmd)          # Command output to variable
readonly PI=3.14       # Constant

# ─── CONDITIONS ───────────────────────────────────────────────────
if [[ $x -gt 5 ]]; then echo "big"; fi
[ -f file ] && echo "file exists"
[ -d dir ]  && echo "dir exists"
[[ $str =~ ^[0-9]+$ ]] && echo "number"

# ─── LOOPS ────────────────────────────────────────────────────────
for f in *.py; do echo "$f"; done
for i in {1..10}; do echo $i; done
while [[ $x -lt 5 ]]; do ((x++)); done

# ─── REDIRECTION ──────────────────────────────────────────────────
cmd > out.txt          # Stdout to file (overwrite)
cmd >> out.txt         # Stdout to file (append)
cmd 2> err.txt         # Stderr to file
cmd > out.txt 2>&1     # Both to same file
cmd 2>/dev/null        # Suppress errors

# ─── TEXT PROCESSING ──────────────────────────────────────────────
grep "pattern" file    # Search for pattern
grep -r "txt" ./       # Recursive search
sed 's/old/new/g' f    # Replace in file
awk '{print $2}' f     # Print column 2
sort file              # Sort lines
sort -u file           # Sort + remove duplicates
wc -l file             # Count lines
cut -d',' -f2 csv      # CSV column 2

# ─── PROCESS MANAGEMENT ───────────────────────────────────────────
cmd &                  # Run in background
wait                   # Wait for all background jobs
jobs                   # List background jobs
kill PID               # Terminate process
ps aux | grep python   # Find Python processes

# ─── USEFUL ONE-LINERS ────────────────────────────────────────────
# Find all Python files containing "import torch"
grep -rl "import torch" . --include="*.py"

# Count total lines in all Python files
find . -name "*.py" | xargs wc -l | tail -1

# Monitor GPU usage every 2 seconds
watch -n2 nvidia-smi

# Last 50 lines of log, live
tail -f -n50 app.log

# All IP addresses on the machine
hostname -I

# Free disk space
df -h | grep -v tmpfs
```

---

### What's Next?

After mastering Bash, consider exploring:
- 📘 **Python scripting** — for complex logic that's too hard in Bash (data structures, APIs, ML)
- 📘 **Docker & Kubernetes** — containerization uses Bash extensively for entrypoints and health checks
- 📘 **Ansible / Terraform** — infrastructure automation built on top of shell scripting concepts
- 📘 **awk & sed mastery** — take text processing to the next level
- 📘 **Zsh + Oh My Zsh** — a more feature-rich interactive shell for daily use

---

> 💬 *"The command line is the universal language of computing. Learn it deeply, and you'll find that the entire digital world becomes your playground."*

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Bash | Version: 1.0 | Author attribution: Deb Barman*
*Generated: 2026*
