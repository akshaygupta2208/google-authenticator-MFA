# google-authenticator-MFA


This ansible role will enable google authenticator MFA on linux machines.

### Steps to run this ansible role.
- Create an intevtory file with the list of servers on which you want to enable MFA.
- apply the ansible playbook by running the below mentioned command.
```
ansible-playbook -i YOUR_INVENTORY_FILE playbook.yml
```

# After running this script what will happen?
- whenever anyone tries to ssh login on the server then for the fresh users it will display the QR code and disconnect the ssh session.
- now user has to scan the QR code and now when the user tries to login again he will be asked to put google-authenticator verification code.

# Assumptions
- This script will not enable MFA for root user and ec2-user. If you want to enable for these users also then you need to edit [sshrc file](roles/google-authenticator/files/sshrc) and remove the entry for root user or ec2-user.
- I have tested this script only on Amazon linux.
