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
![exp5_1](https://github.com/user-attachments/assets/ab0dabac-39fd-441a-b13c-a77dd81649d7)

Invoke msfconsole:
![exp5_2](https://github.com/user-attachments/assets/668c2db5-4274-4aea-823d-1526b1345aed)


Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![exp5_3](https://github.com/user-attachments/assets/9cc8f586-af3b-4759-807d-86f00fbcfdcf)


Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
![exp5_4](https://github.com/user-attachments/assets/66c32fff-08b5-4cb4-b082-10458231d7c7)

msf-nmap step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
![exp5_14](https://github.com/user-attachments/assets/ff4364de-a9e7-4bc6-ad8a-e20c7feb9019)



### OUTPUT:
db_nmap
![exp5_8](https://github.com/user-attachments/assets/2554a32b-77fe-4362-8e18-66d8c226771d)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
![image](https://github.com/user-attachments/assets/b9e72261-856d-4567-8ae6-f4c791afe915)

### OUTPUT:
auxiliary-ls-l

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit
![exp5_7](https://github.com/user-attachments/assets/5481cccd-4159-4b26-a31a-b00ee34f8c59)

The info command provides information regarding a module or platform,
![exp5_10](https://github.com/user-attachments/assets/0315b93b-0a3b-4958-aee1-3566e0eb8aa5)

### OUTPUT
msfsearch

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init

MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

db_nmap

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![exp5_5](https://github.com/user-attachments/assets/3d146ef5-1dfb-4b81-8a58-ba782dd64474)

searchtypeauxiliarymysql
![exp5_9](https://github.com/user-attachments/assets/30f34a72-a7a6-4dee-a51a-542479f1d5e3)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

use11

Use the set rhosts command to set the parameter and run the module, as follows:

setrhost
![exp5_11](https://github.com/user-attachments/assets/6acd8b92-46a6-4030-b98c-b82b820a8125)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

mysql_login
![exp5_12](https://github.com/user-attachments/assets/e0b33061-5753-432c-909d-034800495150)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

pass_file_parameter
![exp5_13](https://github.com/user-attachments/assets/4672beac-c90c-4a04-b38b-9549045f4752)

## RESULT:
The Metasploit framework for reconnaissance is examined successfully.




## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
