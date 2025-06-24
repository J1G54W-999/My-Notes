- # Fail2Ban:
- Fail2ban → An intrusion prevention framework written in Python. It uses iptables to block brute-force attempts
- NOTE: Rather than modifying the actual `jail.conf` file, it is better to make a copy and and add the necessary configurations there or else updates can override the settings
- ### Configuration: `jail.local` 
- ```
    # Make a local copy of jail.conf and fail2ban.conf in /etc/fail2ban
	  cd /etc/fail2ban
      sudo cp fail2ban.conf fail2ban.local
      sudo cp jail.conf jail.local 
    
    # Edit the file
      sudo vim jail.local
    
    # Restart the service after making changes to enable them
      sudo systemctl restart fail2ban.service
    ```
- ### Jail Configuration: `jail.local` 
- 
    ```
    # Under the [sshd] section you can make a specific jail rule
    
    [sshd]
    
    enabled = true
    port = ssh
    filter = sshd
    logpath = /var/log/auth.log
    maxretry = 3
    findtime = 600  # 10 minutes
    bantime = 3600  # 1 hour
    ignoreip = 127.0.0.1 #localhost
    ```
- NOTE: The bantime, findtime and maxretry at the top of the jail.local file are GLOBAL SETTINGS
- ### Email Notification: `jail.local` 
-   ```
    # Email notifications
      destemail = your_email@domain.com
    
    # Choose an action for the email. There are 3 default actions
      action = %(action_mw)s
    ```
