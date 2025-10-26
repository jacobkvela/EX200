# 🕒 AT Command Guide

The **`at`** command allows you to schedule *once-only* jobs that will be executed at a specified time.  
The **`atd`** service must be running to process these scheduled jobs.

---

## 📚 Table of Contents
1. [Install and Manage `atd`](#-install-and-manage-atd)
   - [Install `at`](#️-install-at)
   - [Enable and Start the `atd` Service](#️-enable-and-start-the-atd-service)
2. [Schedule a Job](#-schedule-a-job)
3. [List Scheduled Jobs](#-list-scheduled-jobs)
4. [Remove a Scheduled Job](#-remove-a-scheduled-job)
5. [Example Time Formats](#-example-time-formats)
6. [Tips and Notes](#-tips-and-notes)

---

# Enable and start the service
sudo systemctl enable atd
sudo systemctl start atd

# Check the status
systemctl status atd

# Schedule a job at a specific time
at <time>

# Inside the interactive at shell:
#   - Type your commands
#   - Press CTRL + D to save and exit

# Examples
echo "reboot" | at 2am
at now + 1 hour

# List all scheduled jobs
atq

# Remove a job by ID
atrm <job_id>

# Example
atrm 2

# Make sure the atd service is active before scheduling jobs
sudo systemctl status atd

# Check logs for atd
sudo journalctl -u atd

# Learn more
man at
