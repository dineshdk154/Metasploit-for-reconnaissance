
# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## OUTPUT:

![Screenshot 2024-04-24 081006](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/b4627ea6-1903-495a-bdc8-d58526806196)


Invoke msfconsole:

## OUTPUT:

![Screenshot 2024-04-24 081018](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/13b813ee-c881-40de-abd9-3b2a652f809e)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:

![Screenshot 2024-04-24 081033](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/413c90fd-ec68-4fce-9756-ed46c2efe1ba)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![Screenshot 2024-04-24 081045](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/f18d0fad-47cc-4b77-b431-94b12031546e)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![Screenshot 2024-04-24 081054](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/ffdf3b34-6ec2-4f6f-bb4e-c1cf8dc94d3a)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![Screenshot 2024-04-24 081106](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/827ef15e-b8ba-46f4-ace0-04e09579b979)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:

![Screenshot 2024-04-24 081121](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/d2854529-5baa-4f21-84a0-1d84c9257e83)

The info command provides information regarding a module or platform,


## OUTPUT:

![Screenshot 2024-04-24 081132](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/8bb2ecf6-bec6-48fc-85ad-ad7907f1f409)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:

![Screenshot 2024-04-24 081144](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/853d795c-3054-422e-842a-0f9e5ee56baa)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:

![Screenshot 2024-04-24 081155](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/807fd0a5-64d4-40f8-94be-ff15cbbdab4d)

use 11 Or: use auxiliary/scanner/mysql/mysql_version

## OUTPUT:

![Screenshot 2024-04-24 081212](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/d597c747-f674-4c3d-b61f-d2842ef02b14)

Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:

![Screenshot 2024-04-24 081221](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/2bacf86c-0fc7-4ea3-b6b9-befba69de8d0)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:

![Screenshot 2024-04-24 081231](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/dbbcc38e-9a33-48dd-8898-c65226ffc980)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

## OUTPUT:

![Screenshot 2024-04-24 081241](https://github.com/RahulKrishna05/Metasploit-for-reconnaissance/assets/162027231/43c07561-5882-4bba-916c-f0037eeff783)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
