# The Windows Registry:

- Windows Registry → A hierarchical database that stores configuration settings and options for the Microsoft Windows operating system
- HKEY = Hive to registry key

- ### The 5 Hives:     
- HKEY_CLASSES_ROOT → File associations and COM objects i.e. tells windows which program to use to open different file types like .jpg or .txt 
- HKEY_CURRENT_USER → Setting for the currently logged in user i.e. Desktop settings, start menu settings and user profiles (points to a sub-key of the HKU hive)  
- HKEY_LOCAL_MACHINE → Setting for the entire computer, including hardware and software setting and system-wide configurations
- HKEY_USERS → Settings for all user profiles on the computer. Each user has their own sub-key 
- HKEY_CURRENT_CONFIG → Current hardware config settings by pointing to a sub-key of the  HKLM hive
- 
- NOTE: Any changes to the registry can crash the computer if not done correctly
![](https://remnote-user-data.s3.amazonaws.com/qmyG-CRwn9JmnraSVBkaZGrlJWsucmLhOQoJXZgLk0qsCUCfoZCrjiuu6F4CD9UjPXTM_ZtjJf5SkveoURIA9PQn_BJ2W7W_YQRSrPiKNg3cYXcsgK7VFVipsnk3qYvl.png)
- 
- ### The Registry System:
| Old System: | New System: |
|--|--|
|Storage was in TXT files  |Storage is in a database  |
|Easy to delete sub-keys/files by accident  | Can't accidentally delete sub-keys |
| No standard structure (Made to fit task) | Centralised + standardised storage (Hierarchy Structure) |
|If keys got deleted they are unrecoverable  | Database can be backed-up |
