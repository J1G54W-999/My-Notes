### Create a User Account: Linux
- `useradd` → Low-level user creation
- `adduser` → High-level user creation (Input prompts)
 
Syntax: `sudo useradd <account_name>` 
- `sudo useradd cyberninja` → Create a user account
- `sudo useradd -m cyberninja` → Create a user account + home directory `/home/cyberninja` 
 
### Set the password:
- Syntax: `sudo passwd <account_name>` 
- `sudo passwd cyberninja` → Set the password (If using the `useradd` command)
 
### Delete User:
- `deluser` → Deletes a user account and associated files.
 
Syntax: `deluser <account_name>` 
- `sudo deluser cyberninja` 
