# BorgBase Sync Backup All

This is a simple Ansible project to automate the configuration and syncing of backups from multiple BorgBase repositories using rclone.

## Usage

1. Copy the `group_vars/all.yml.tpl` to `group_vars/all.yml`:
```bash
cp group_vars/all.yml.tpl group_vars/all.yml
```
2. Insert your variables into `group_vars/all.yml`, such as your SSH key file path and BorgBase repository details.

3. Run the playbook:
```bash
ansible-playbook main.yml
```

4. Prepare the disk: Simply mount it once manual and format as ext4 and chown it to be usable by user.

The playbook will:
- Create the rclone configuration directory and generate the `rclone.conf` file based on your repositories.
- Install a script (`my-borgbase-sync.sh`) in your `~/.local/bin` directory for performing the sync operations.
