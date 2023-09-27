# BANDIT : OVER THE WIRE

### Level 0-1:

This is a begginner level which prompts us to login to the server with the ssh command
	Command:ssh bandit0@bandit.labs.overthewire.org -p 2220
	type in the password to enter the next lvl

### Level 1-2:

Simple usage of cat command
	Command:bandit0@bandit:~$ cat readme
	this gets the password to progress to the next level

### Level 2-3:

Spaces in file name
	Command:cat spaces\ in\ this\ filename 

### Level 3-4:

cd into the directory inhere
	Command: ls -a
	this reveals .hidden which on executed with cat gives the password

### Level 4-5:

Human readable file
	After Cd into the dir inhere we find a lot of files
	to find the human readable (ASCII) file we use the file command
	Command:file ./*
	This giives the file type of file 7 to be ASCII executing this gives the password

### Level 5-6:

Sort file on basis of size and Human readability
	On Cd ing into inhere directory we find a lot of files 
	We need to sort this using the du and grep command
	Command:du -b -a | grep 1033
	this sorts all the files on basis of the byte size and greps the size 1033
	thus providing the target file which when executed gives tghe password

### Level 6-7:

User and group owned file which can also be filtered by size
	Command:find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
	/var/lib/dpkg/info/bandit7.password
	the  2>/dev/null/var/lib/dpkg/info/bandit7.password  block helps to prevent the permission 
	denied error

### Level 7-8:

Easy use of grep and piping
	Command:cat data.txt | grep millionth

### Level 8-9:

Usage of the sort command to find a unique line
	Command:sort data.txt | uniq -u

### Level 9-10:

	easy use of grep command
	Command:strings data.txt | grep ===

### Level 10-11:

simple Cat command followed by decoding from base64 to ascii
	Command:cat data.txt
	Command:base64 -d data.txt

### Level 11-12:

Rot encryption whis can be decoded using tr command 
	Command:cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

### Level 12-13:

Hexdump of a file tht has been repeatedly compressed
	for this first create a tmp folder to save the files into
	then copy the data to the tmp folder
	on the folder use bzip2 , gzip and tar to decompress it multiple times and find the answer

### Level 13-14:

The ls revealed an ssh.privatekey
	this needs o be saved to the machine using cat and copy
	afterwards use the following command
	Command:ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

### Level 14-15:

Netcat introduction 
	Command:cat ./etc/bandit_pass/bandit14
		(Provides the password)
		nc localhost 30000
		(Enters provided pass)
	this provides the password

### Level 15-16:

Connection Using ssl client
	Command:openssl s_client -connect localhost:30001
		(Input the previous password)
	this gets the new password

### Level 16-17:

Introduced port scanning and Usage of Nmap
	use nmap to scan ports for the ones using ssl
	Command:nmap -sV localhost -p 31000-32000
	wich gives us a port tht uses ssl connect to tht port
	Command:openssl s_client -connect localhost:<input port>
		(input previous password)
	this provides a private key
	save it as 'sshkey17,private'

### Level 17-18:

login using the previously saved privatekey
	intro to diff commands
	Commands:diff passwords.old passwords.new 
	which gives the only line tht was changed which is the password

### Level 18-19:

ssh bandit18@bandit.labs.overthewire.org -p 2220 closes the connection as bash has been        			 	 	 	 	 
	modified to automatically log out while using ssh
	Using sh shell ssh bandit18@bandit.labs.overthewire.org -p 2220 -t "/bin/sh"
	Not logged out automatically ,Ls reveals readme file

### Level 19-20:
Need to use the setuid binary
execute the file bandit20-do with the password at the /etc/bandit_pass directory
Command:./bandit20-do cat /etc/bandit_pass/bandit20
this gives the password

### Level 20-21:
Complex question using setuid binary which makes a connection to localhost on the port you specify as a commandline argument.It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
To do this we need to start a server on a specific port with the following command
Command : echo < Previous password >| nc -l localhost -p 55555 &
then connect the file suconnect to the port
Command : ./suconnect 55555
which then asks for the previous password and when answered correctly gives the password for the next lvl

### Level 21-22
Introduction to cron(time-based job scheduler)
when we ls into /etc/cron.d , we see tht there are multiple files out of which one is named cronjob_bandit22
upon using cat on the file ith provided the code with 5 stars meaning that it is counting minutes
then we cd into the /usr/bin file to view the code
On using cat in the code tells us that the pasword is being assigned to a certain file 
once we execute the file we get the password 





	
