# Spigot-deploy-playbook
Ansible playbook that automates deploying a Spigot Minecraft server to an Ubuntu minimized server with Ansible installed.

Much of this code was created with the help of ChatGPT.  I fully expect errors or some possible edge cases where this will not work.  I did my best to make this an easy deploy to a local host.  If you are deploying to a remote server, please update localhost in the playbook to reflect the server hostname.

Assumptions: Ubuntu minimized server with Ansible installed

Instructions - sudo ansible-playbook deploy-spigot.yaml

----------------------------
Minecraft Server Documentation
----------------------------

Deployment Method: Ansible

Automations:
- Daily server update cron job (4 AM).

Available functions:
- Start the server: sudo systemctl start spigot
- Stop the server: sudo systemctl stop spigot
- Restart the server: sudo systemctl restart spigot

Update Scripts:
- Server Update: /home/minecraft/server/update_server.sh
- Spigot Update: /home/minecraft/server/update_spigot.sh

World Backup:
- Usage: /path/to/world_backup_script.sh "world_name" "destination_folder"
