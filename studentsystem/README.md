Here's what worked for me:
First:
```
export WSL_HOST_IP=$(awk '/nameserver/ { print $2 }' /etc/resolv.conf)
```
Not sure what the above command does, but works.

Now, allow all connections from MySQL Workbench
- Open MySQL Workbench --> Server --> Users and Privileges
- Select the user
- Change the Limit to Hosts Matching to "%" for accessing from any host.
- Apply changes.
- Restart MySQL Service if required. It worked for me with out restarting.

Remember to put nameserver from the following command to access db from windows:
```
cat /etc/resolv.conf
```