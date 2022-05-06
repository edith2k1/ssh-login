# How to Setup Passwordless SSH Login

Step 1.  Generate public/private rsa key pair

    ssh-keygen -t rsa -b 4096
    
Step 2. Copy our public key to remote machine `Run on Git Bash`

    ssh-copy-id vex@192.168.217.100

Step 3. Login to your server using SSH keys

After completing these steps above you should be able log in to the remote server without providing password.
To test it just try to login to your server via SSH:

    ssh vex@192.168.217.100
    
If everything went well, you will be logged in immediately. 

**Advanced**: To add an extra layer of security to your server you can disable the password authentication for SSH.

Open the SSH configuration file /etc/ssh/sshd_config, search for the following directives and modify as it follows:

    PasswordAuthentication no
    
Once you are done save the file and restart the SSH service.

    sudo systemctl restart ssh
