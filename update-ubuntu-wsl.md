1. Update all packages for current version `sudo apt update && sudo apt dist-upgrade -y`
2. Install the release upgrade tool `sudo apt install update-manager-core`
3. Do the release upgrade `sudo do-release-upgrade -d`
4. Answer yes to any questions about disabling services
5. Keep your version for any of the SSH upgrades.
6. You will lose the connection to the server at the after the reboot at the end; simply reopen the terminal for the newest version.
