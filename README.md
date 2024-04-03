# README.md for Service-Monitoring-and-Restart-Script

```markdown
# Service Monitoring and Restart Script

This script is designed to monitor specified critical services on a Linux system and restart them if they are found not to be running. It is particularly useful for ensuring essential services like SSH, Apache, and MySQL remain active, minimizing potential downtime.

## Features

- Monitors a customizable list of services.
- Automatically restarts any service that is not running.
- Can be scheduled to run at regular intervals using cron.

## Prerequisites

Before you run this script, ensure you have:

- A Linux system with `systemctl` command available.
- Sudo or root access to the system to restart services.

## Setup

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/MisterRedcliffe/Service-Monitoring-and-Restart-Script.git
   cd Service-Monitoring-and-Restart-Script
   ```

2. **Make the Script Executable:**

   Change the script's permissions to make it executable:

   ```bash
   chmod +x Service-Monitoring-and-Restart.sh
   ```

3. **Customize Services:**

   Open `service_monitor.sh` in your favorite editor and modify the `SERVICES` array to include the services you want to monitor:

   ```bash
   nano Service-Monitoring-and-Restart.sh
   ```

   Example:
   ```bash
   SERVICES=("ssh" "apache2" "mysql")
   ```

## Usage

Run the script manually to test its functionality:

```bash
./Service-Monitoring-and-Restart.sh
```

### Automating the Script

To ensure your services are monitored continuously, schedule the script to run periodically using `cron`:

1. Open your crontab:

   ```bash
   crontab -e
   ```

2. Add a line to run the script at your desired frequency. For example, to run it every hour:

   ```bash
   0 * * * * /path/to/Service-Monitoring-and-Restart.sh
   ```

3. Save and close the crontab editor.

## Contributing

Contributions to improve the script or add new features are welcome. Please feel free to submit a pull request or open an issue.
