                              How To Encrypt Your Creadention IN Ansible
-------------------------------------------------------------------------------------------------------------------------
How to Encrypt Passwords in Ansible Using Ansible Vault

Step 1: Create a secrets.yml file
First, store your sensitive credentials, such as passwords and API keys, in a file named secrets.yml.
Example:
password: MySecretPassword123
api_key: MySecretAPIKey456


Step 2: Create a Vault Password File, This password is used to Encrypt.
Create a file named vault_password.txt. This file will contain your own secret password (encryption key), which Ansible Vault will use to encrypt and decrypt secrets.yml.
vim vault_password.txt
Write a unique password inside it.

Step 3: Set File Permissions
Run the following command: chmod 600 vault_password.txt
This ensures that only the file owner has read and write permissions.

Step 4: Encrypt secrets.yml
Use the following command to encrypt your credentials file:
ansible-vault encrypt secrets.yml --vault-password-file vault_password.txt


ansible-vault encrypt → Encrypts the specified file.
secrets.yml → The file containing your sensitive credentials.
--vault-password-file vault_password.txt → Tells Ansible where to find the password required for encryption.
Now, your secrets.yml file is encrypted using Ansible Vault.

Step 5: Run the Playbook Without Providing the Vault Password
ansible-playbook -i hosts.ini show_secrets.yml
Important
 If you already encrypted secrets.yml file, Ansible will ask for the Vault password or fail if no password is provided. It cannot automatically decrypt the file without the password.

Step 6: Run the Playbook by Providing the Vault Password File
ansible-playbook -i hosts.ini show_secrets.yml --vault-password-file vault_password.txt

step 7: add all these files in .gitignore

echo "show_secrets.yml" >> .gitignore
echo "secrets.yml" >> .gitignore
echo "vault_password.txt" >> .gitignore


Now Ansible will:
1. Read the password from vault_password.txt.
2. Use it to decrypt secrets.yml.
3. Load the credentials into your playbook.
4. Execute the tasks.

Remember:
- ansible-vault encrypt is used to encrypt your secrets file.
- --vault-password-file specifies the file containing your Vault password.
- chmod 600 restricts access to the password file to its owner.
- Keep vault_password.txt secure. Do not upload it to GitHub or commit it to your Git repository.
- You can safely commit the encrypted secrets.yml file to GitHub, provided you protect your Vault password separately.