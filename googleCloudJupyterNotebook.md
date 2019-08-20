# Now Google Cloud! (for linux practice)
Only God (and my friend xx) know how much time I spent on trying to set up an environment practicing Linux.
Long story short, I decided to try google cloud.
Excellent introduction here 
https://www.datacamp.com/community/tutorials/google-cloud-data-science.
Many thanks to datacamp's very much detailed article. Only a few notes here.
1. If you choose bootdisk as 'Ubuntu‘ instead of the default Debian GNU, then when activate anaconda,
instead of using 
```
source .bashrc
```
use 
```
source ~/.bashrc
```
(reference here https://www.digitalocean.com/community/tutorials/how-to-install-anaconda-on-ubuntu-18-04-quickstart,
step7)

2. when creating the instance, make sure you check the firewalls (i.e.,check the "Allow HTTP traffic" and
"Allow HTTPS traffic")

3. I figured it might be easier accessing the vm through ssh (just click on the ssh next to the name of the instance)

4. It took (very very) long time to install Debian packages, so make sure you have other things to do while waiting..

5. When creating your firewall rules, make sure you choose allow for the "action on match". I somehow created my
first firewall rule with that option set to be "deny" and never able to switch that back the the right way!

6. You don't need a static IP address to access from your local machine. 

7. I could not access the IP address (https://<your_VM_IP>:8888/>) after I set up everything. It magically worked
if I change it to http://<your_VM_IP>:8888/!. I found some online discussion here 
https://github.com/jupyter/notebook/issues/2265
that looks helpful.

8. Attention!!!!
According to the article, it is very important to have a strong Jupyter Password; also remember to stop the VM
when you are not running it. The reason is that Jupyter allows you lauch a terminal with sudo access within
the Jupyter Notebook which can then take control of your VM and steal your credit. So take a look here!
https://blog.jupyter.org/public-notebooks-and-security-3058c433c884
https://letsencrypt.org/zh-cn/getting-started/