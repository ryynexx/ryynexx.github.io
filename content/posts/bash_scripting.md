
+++
date = '2025-06-28T17:00:00+05:00'
title = 'From Command Line to Automation: Your Bash Journey Begins'
tags = ['bash', 'scripting', 'linux', 'automation', 'productivity']
+++

---


Being on your terminal, you must have faced doing a single task repetitively. For that, we have **Bash scripting** — it lets you automate repetitive tasks using a single command.

---

## What is Bash Scripting

**Bash** (Bourne Again Shell) is the default command-line shell on most Linux distributions and macOS.

A **Bash script** is a file that contains commands written line by line, which the shell can execute.

It’s like writing a to-do list for your computer — and by running the script, all your commands in it will run on their own.

---

## How to Create a Bash Script

A Bash script typically:

* Has an extension of `.sh`
* Starts with a **shebang** line to specify the interpreter

### Example:

```bash
nano greeting.sh
```

Inside the file:

```bash
#!/bin/bash
echo "Hello, $USER!"
date
```

### Make the script executable:

```bash
chmod +x script_path.sh
```

### Run the script:

```bash
./script_path.sh
```

---

## Work on Bash Script

### Display Output

Use `echo` to print text to the console:

```bash
echo "Hello, world!"
```

---

### Reading User Input

Use the `read` command to get input from the user:

```bash
echo "Enter your name:"
read name
echo "Hello, $name!"
```

---

### Conditional Statements

Bash supports `if`, `elif`, `else`, and `case` for decision-making.

#### Example using `if`, `elif`, and `else`:

```bash
read -p "Enter a number: " num

if [ "$num" -gt 0 ]; then
  echo "Positive number"
elif [ "$num" -lt 0 ]; then
  echo "Negative number"
else
  echo "Zero"
fi
```

> `fi` ends the `if` block (it’s `if` spelled backward).

---

#### Example using `case`:

```bash
read -p "Enter a day: " day

case "$day" in
  "Monday") echo "Start of the work week." ;;
  "Friday") echo "Almost the weekend!" ;;
  "Sunday") echo "Relax, it's Sunday." ;;
  *) echo "Just another day." ;;
esac
```

> `esac` ends the `case` block (again, it's `case` spelled backward).

---

### Loops in Bash

You can use both `for` and `while` loops.

#### `for` loop example:

```bash
for i in 1 2 3 4 5; do
  echo "Count: $i"
done
```

#### `while` loop example:

```bash
count=1
while [ $count -le 3 ]; do
  echo "This is loop #$count"
  ((count++))
done
```

> `done` is used to close both `for` and `while` loops.

---

### Variable Usage

In Bash, you assign variables like this:

```bash
name="Alice"
```

To access a variable, use the dollar sign:

```bash
echo "Welcome, $name"
```

---

### Adding Comments in Bash Scripts

In Bash, you can add comments using the `#` symbol. Anything following `#` on a line is ignored by the interpreter and is just for human readers.

This helps explain what each part of the script does, making it easier to maintain.

#### Example:

```bash
#!/bin/bash

# This script greets the current user
echo "Hello, $USER!"

# Show the current date and time
date
```

Use comments generously in longer scripts to make your code more understandable.

---

## Automating with Terminal Commands

To automate a function, include terminal commands in scripts.

### Example 1: Update and Upgrade

```bash
#!/bin/bash
sudo apt update && sudo apt upgrade -y 
echo "System updated on $(date)"
```

---

### Example 2: Clean System

```bash
#!/bin/bash
sudo apt autoremove -y && sudo apt autoclean -y
echo "System cleaned successfully"
```

---

### Example 3: Backup a Folder

```bash
#!/bin/bash
src="$HOME/"
dest="/mnt/backup/"
rsync -av --delete "$src" "$dest"
```

---

## Scheduling Scripts

You can schedule your script to run using the tool **cron**, which helps automate or schedule tasks to run on a daily, weekly, monthly basis — or even at a specific time.

Use this syntax for a cron job:

```bash
* * * * * sh /path/to/script.sh
```

The `*` symbols represent:

```
| Minute | Hour | Day of Month | Month | Day of Week |
```

### Commands to work with cron:

* `crontab -e` → Add or edit scheduled jobs
* `crontab -l` → List all the scheduled scripts

---

## Conclusion

It can be concluded that **Bash scripting turns the command line into your personal assistant**. It saves time, avoids errors, and gives you full control over your Linux system.

Start simple, script often — and let your terminal do the work for you.

---

