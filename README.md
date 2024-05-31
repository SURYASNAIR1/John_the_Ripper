# JOHN_THE_RIPPER

•	Powerful and popular open-source password cracking tool.

•	Known for its versatility and capability to crack various types of password hashes through different attack methods.

•	Johny is a user-friendly graphical interface that makes john the ripper more accessible to non-technical users.

•	Testing the security of your own passwords or recovering the lost credentials

•	Crack password hashes.

•	Can handle various password hash formats.

•	Offers multiple attack modes including brute-force, dictionary, and hybrid attacks.

•	Is optimized for speed, utilizing multiple CPU cores and GPUs to accelerate the password cracking process.

•	Users can easily use their own wordlists and apply custom rules to generate password variations efficiently. 

•	Is supported in windows, Linux, macOS, openbsd, android, freebsd.

•	Is preinstalled in kali Linux.

•	Open kali and then type john --help

•	Usage:  <font color="red"> john [OPTIONS] [PASSWORD-FILES] </font>

•	Johny features a wizard mode that guides users through the necessary steps to start password cracking without requiring in depth technical knowledge.

•	To install johny in kali: sudo apt install johny

•	Then search for johny in the tool section of kali and click on it.

•	Inside johny we can be able to see open password file. Under that two sections will be there. one for hash file and other for password protected file like zip, pdf.

•	Under options tab we can be able to see section details and attack mode

•	Under the session details we can be able to see the current hash format

•	From the attack mode we can select the attack types.

•	Attack types are single crack, wordlists, incremental, external, mask, Markov, and prince.

•	Console log: displays logs for each attack attempt providing insights into the cracking process.

•	Start new attack, resume attack, and pause attack are there.

•	Progress bar: provide a visual representation of the cracking process making it easy to track.

# Example1: How to crack any type of Hash?

•	Open web browser and search for online hash generator. Let’s generate a MD5 hash.

•	In the input field give your desired string for example: TechnoScience@123

•	After clicking the generate button we will be able to see the hash

•	Now we copied the MD5 hash.

•	Open kali and copy the hash value to there and save it as hashmd.txt

•	Then open the terminal and type the command sudo john - -format=RAW-MD5 hashmd.txt

•	Wordlist attack using cup

Commands: open terminal and type

cupp -i

•	Now the word lists will be created with a name that we can see in the terminal itself.

•	Now return to the previous terminal and type sudo john - -format=RAW-MD5 hashmd.txt - -  wordlist=techno.txt

•	Thus, we can crack the hash.

Crack the hash using a GUI

•	Open johny in kali

•	Open password file

•	Load the password file hashmd.txt.

•	Click on open.

•	Click on options.

•	Click on wordlist.

•	Click on browse and choose hashmd.txt

•	Choose the current hash format as Raw-MD5

•	Then go to password.

•	Click on start new attack.

•	Thus, we will get the password.


# Example 2: How to crack a password protected encrypted file like .zip, .rar?

•	I have test.zip in my kali. 

•	Open the terminal and type zip2john test.zip > test.txt

•	This command will generate a text file which contain the password hash.

•	sudo john test.txt - - wordlist=/usr/share/wordlists/rockyou.txt

•	Thus, we will be able to get the password use the password after extracting the zip file and to open it.

•	Similar way for .rar also.

# Example 3: How to crack a password protected PDF File?

•	I have a pdf with name test.pdf.

•	Open terminal in kali and type pdf2john test.pdf > test.txt

•	sudo john test.txt - - wordlist=/usr/share/wordlists/rockyou.txt

•	Thus, we will be able to get the password use the password to open pdf file.


# Example 4: How to crack a Linux Passwords?

•	Set up 3 users in the Linux system in ubuntu.

•	Boot your system using a kali Linux USB drive.

•	Inside kali select live system with USB persistence 

•	Here inside kali, we will have ubuntu kali hard disk (here with name 33GB volume in the desktop of kali)

•	Open it and open etc directory.

•	The open the terminal.

•	Sudo unshadow passwd shadow > /home/kali/Desktop/linuxpass.txt

•	cd/home/kali/Desktop

•	ls

•	sudo john linuxpass.txt

•	Using the above command, we will not get succeed so use below command.

•	sudo john - -format=crypt linuxpass.txt

•	open new terminal and type 

locate rockyou.txt

•	The file is in .gz format so we will extract it.

•	sudo gunzip /usr/share/wordlists/rockyou.txt.gz

•	Then on another terminal we will type

sudo john - -format=crypt linuxpass.txt - -wordlist=/usr/share/wordlists/rockyou.txt

•	Thus, we can be able to see the passwords

# Example 5: How to crack windows password?

•	Created two users in windows.

•	Usually in windows the user passwords are stored inside security account manager file.

•	Boot the system with kali Linux USB drive.

•	Then choose the hard drive as done in above example.

•	Then go to windows directory.

•	Choose system32.

•	config directory choose.

•	Open the terminal from there.

•	sudo samdump2 SYSTEM SAM > /home/kali/hashes.txt

•	cd

•	ls

•	Open another terminal and type

•	locate rockyou.txt

•	sudo gunzip /usr/share/wordlists/rockyou.txt.gz

•	sudo john - -format=NT hashes.txt - -wordlist=/usr/share/wordlists/rockyou.txt

•	Thus, we can be able to see the passwords




