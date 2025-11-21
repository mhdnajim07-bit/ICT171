# ICT171
1.Installed the Web Server (Apache) on Azure

Connected to the VM using SSH:
ssh azureuser@4.247.132.31
Installed Apache:

sudo apt update
sudo apt install apache2


Enabled and started the web server:

sudo systemctl enable apache2
sudo systemctl start apache2

2. Uploaded My Website Files to Azure

On my Windows laptop, used Git Bash + SCP to upload the website file:

scp /c/Users/.../index.html azureuser@4.247.132.31:~/index.html


Then moved it into the Apache folder on the VM:

sudo mv ~/index.html /var/www/html/index.html
sudo chown www-data:www-data /var/www/html/index.html
sudo chmod 644 /var/www/html/index.html
sudo systemctl restart apache2

3. Purchased a Domain from Clearname

Bought a custom domain from Clearname.

Logged in to Clearname DNS settings.

4. Connected My Domain to My Azure VM

In Clearname DNS:

Added an A Record
Host: @
Points to: 4.247.132.31
TTL: Default

Waited 5–20 minutes for DNS propagation.

Now the domain shows my website.

5. Final Testing

Opened the domain in a browser.

Ensured UI, functionality, cart system, and filters work correctly.

Confirmed that the site loads securely and consistently.
