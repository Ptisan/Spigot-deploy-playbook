# Spigot-deploy-playbook
Ansible playbook that automates deploying a Spigot Minecraft server to an Ubuntu minimized server with Ansible installed.

Much of this code was created with the help of ChatGPT.  I fully expect errors or some possible edge cases where this will not work.  I did my best to make this an easy deploy to a local host.  If you are deploying to a remote server, please update localhost in the playbook to reflect the server hostname.

NOTE: This playbook allocates 6GB RAM to the Spigot service.  Please make sure that you have at least 6GB free to run the server and enough RAM to still run the OS.  I would recommend at least 8GB in all.  If you want to modify the amount of RAM allocated to the server, find the task titled "Create start script for Spigot server" and replace the number 6 in "-Xms6G -Xmx6G" with the amount of RAM you wish to allocate.  These are the first two options after the word "java" in the shell script.

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
- Usage: /home/minecraft/server/world_backup_script.sh "world_name" "destination_folder"
