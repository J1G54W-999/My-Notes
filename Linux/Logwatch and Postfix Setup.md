- # Logwatch:
- Logwatch → Keeps an eye on your logs for you, flags items that may be of interest, and reports them via email
- NOTE: Setup Postfix (Mail server) locally as a mail transfer agent (mentioned during logwatch download)
- ### Installation:
-  ```
   # Install Logwatch
     sudo apt install logwatch
   
   # Manually add in a temporary directory for logwatch to work
     sudo mkir /var/cache/logwatch
    ```
- ### Configuration:
- ```
  # Copy logwatch.conf file 
    sudo cp /usr/share/logwatch/default.conf/logwatch.conf /etc/logwatch/conf 
  
  # Modify configurations
    sudo vim /etc/logwatch/conf/logwatch.conf
  
  # Change the following items
    Output    = mail
    MailTo    = voldemort@localhost
    MailFrom  = logwatch@localhost
    Detail    = Low
    Service   = All
    ```
- NOTE: Similarly to fail2ban, we need to copy the config file and make changes or else everything will be overwritten during updates
- # Postfix: Mail server
- Postfix → Postfix is a mail transfer agent (MTA) used for sending and receiving emails
- ### Installation:
- ```
  # Install postfix
    sudo apt install postfix
    ```
- ### Configurations: Local Setup
    ```
  # Edit configurations
      sudo vim /etc/postfix/main.cf 
  
  # Change myorigin
      myorigin = voldemort-VirtualBox
  
  # Change myhostname
      myhostname = localhost
  
  # Change  mydestination
      mydestination = $myhostname, voldemort-VirtualBox, localhost.localdomain, , localhost 
  
  # Change inet_interfaces
      inet_interfaces = localhost 
  
  # Restart the service
      sudo systemctl restart postfix 
    ```
- NOTE: To check configurations use `postconf -n` 
- # Mail: Ubuntu
- ```  
  # If mail command is not installed
    sudo apt install mailutils 
  
  # Send test email
    sudo logwatch --detail low --mailto voldemort@localhost --range today
  
  # Check mailbox mail is working
  sudo mail -u voldemort
