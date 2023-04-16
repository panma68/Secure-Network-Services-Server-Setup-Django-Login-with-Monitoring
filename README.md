# Network_Security_Projects
This repository contains projects from the Network Security courses of the AUEB university.

For the first implementation there is only a report as it is a server setup. For the second one there is code.

## The first project has a result to have created a VM with OS CentOS 7.
The connection to the server is done only with SSH using any client (eg PuTTY).

1) SSH connection requires using AUEB VPN.

2) Set the authentication to be done only with SSH keys.

### Requirements included:

  A. Create a "teacher" user. The teacher user should connect with ssh key.
(Note: to check connectivity you can add to the file with public
keys (authorized_keys) past the teacher's public key on a new line and yours. This was done. 
My private key was created using PuTTYgen.)

  B. Give the user "teacher" read permissions everywhere on /home and /root (on folders, subfolders and files) and not have any write rights to /home (the folder, subfolders and archives)

  C. Installation and configuration of all necessary services for the server to function as a web-server with Apache.

  D. Adding the necessary inbound rules to the FirewallD service of CentOS, so that http and https to be accessible from everywhere. Restrict ssh access via AUEB only VPN.
  E. Using OpenSSL create a Certificate Authority (CA), CSR and an SSL certificate. In Organizational Unit Name (OU) define your AM (eg: 3180000 and not p3180000).

  F. Configure Apache to serve your certificate over https and to redirects http to https. Make sure the entire SSL certificate chain is displayed correctly.

  G. Create a simple website with only one text field with name=”username” and a submit button. If your AM is submitted (eg: 3180000) it should display a success message, while in any other case a failure message (containing the words "success" and "fail" respectively) You can use any technology. Use as DocumentRoot: /var/www/html

## The second project is a secure login page.

1. Create a system in Python Django.

2. Build activity monitoring mechanisms in the login endpoint that you created.

### The basic control that of the login page is analyzed in the following two steps:

A. Checking the database of the web information system if there is a user with this username

B. Calculation of the summary (hash) of the code given by the user in the web-form and retrieving the record with the user's details from the database check if the stored hash of the registered user's password is the same as the hash that was calculated from the password provided in the corresponding field of the web-form. If the hashes match, the user is entered into the private environment of the web application which provides features that are not public on the world wide web but are available only to its legitimate users.
