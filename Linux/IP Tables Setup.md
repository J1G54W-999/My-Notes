- # IP Tables: 
- `sudo iptables -L` → Shows the current iptables rules.
- `netfilter-persistent` → A tool that saves and restores netfilter rules across reboots.
- `nftables` → The newer version of iptables
- `iptables-persistent` → Saves the iptables across reboots `sudo apt install iptables-persistent` 
- ### Commands to view and save iptables:
- ```
    # View the iptable rules 
	  sudo iptables -L
     
    # Save changes to the iptables (If iptables-persistent is installed) 
	  sudo iptables-save > /etc/iptables/rules.v4 
    
    # Save to persistent storage to keep after reboot sudo netfilter-persistent save
  
    ```
- NOTE: Save iptables to the `/etc/iptables/rules.v4` (for IPv6 use .v6)
- NOTE: The iptables directory is not pre-made, so you have to make it. If you have permission issues, you can create the rules.v4 file in your own directory and then move it to the `/etc/iptables` 
- 
- ### How to change to permissions to root for save after reboot:
- ```
    #  Change permissions to Owner: read, write | Group: read | Others: read
	   chown 644 filename
	   
	# Change owner and group to root
	  chown new_owner:new_group file/directory 
    ```
- ### Examples of iptables firewall setup:
- ```
    # Drop ALL incoming traffic (Unless specified like the fields below)
    sudo iptables -P INPUT DROP
    
    # Keep existing connections like loopback
    sudo iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
    
    # Allow incoming traffic on port 22
    sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
    
    # Block incoming traffic on port 22
    sudo iptables -A INPUT -p tcp --dport 22 -j DROP
    
    # Allow outgoing traffic on port 22
    sudo iptables -A OUTPUT -p tcp --dport 22 -j ACCEPT
    
    # Block outgoing traffic on port 22
    sudo iptables -A OUTPUT -p tcp --dport 22 -j DROP 
    
    # Drop all other connections
    sudo iptables -A INPUT -p tcp -j DROP 
    ```
- NOTE: Be sure to check the DNS. Sometimes the rule is correct, but you still can't resolve hosts because the 'address book' is blank 
