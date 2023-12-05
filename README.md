<h1>Password Checker</h1>



<h2>Description</h2>
The project consists of two Python files and text files. Generate_hashes.py is used to convert string values (user's passwords in this case) in variables that are assigned to their username. the list of user's passwords is saved in a common password text file and the usernames are saved in a username hashes  text file. The Password_Cracker.py converts the inputted string into SHA256 using UTF-8. This SHA256 value is compared to the SHA256 value of the commonly known passwords on the site. 
 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 
  

<h2>Environments Used </h2>

- <b>Pycharm</b> 

<h2>Program walk-through:</h2>

<p align="center">
Creating common passwords in a text file: <br/>
<img src="https://i.imgur.com/IXliyiu.png" height="80%" width="80%" alt="Password Cracker Steps"/>
<br />
<br />
Created hashing algorithm:  <br/>
<img src="https://imgur.com/HgdSbc6.png" height="80%" width="80%" alt="Password Cracker Steps"/>
<br /> haslib.sha256() creates a new SHA-256 hash object. SHA-256 (Secure Hash Algorithm 256-bit) is a cryptographic hash function that takes an input (in this case, the password) and produces a fixed-size (256-bit or 64-character) hexadecimal digest. 
  
<br /> password.encode('utf-8') This part of the code encodes the password string into bytes using the UTF-8 encoding. Hash functions work on bytes, so the password needs to be converted from a string to bytes before hashing.

<br />print(hash.hexdigest()) is used to output the hash values

<p align="center">
Assigned the password hash values to the username in a text file: <br/>
<img src="https://i.imgur.com/OgcbHcE.png" height="80%" width="80%" alt="Password Cracker Steps"/>
<br />
<br />
The first part of the password checker:  <br/>
<img src="https://i.imgur.com/jOucY6S.png" height="80%" width="80%" alt="Password Cracker Steps"/>
<br /> Import hashlib  imports the Python hashlib library, which provides hash functions like SHA-256 for secure hashing. 
  'user_hash_dict = {}' initializes an empty dictionary called user_hash_dict. 
  
  This dictionary will be used to store username-hash pair. 'with open('common_paswords.txt', 'r') as f:' This line opens the file 'common_paswords.txt' in 
   read ('r') mode using a context manager (with statement) and assigns it to the variable f.
  
  'common_passwords = f.read().splitlines():' this line reads the content of the 'common_paswords.txt' file using f.read() and then uses .splitlines() to 
   split the content into a list of strings. 
  Each string in the list represents a common password.
  
  'with open('Username_hashes.txt', 'r') as f:'this line opens the file 'Username_hashes.txt' in read ('r') mode using a context manager and assigns it to the variable f.
<br />

The second part of the password checker:  <br/>
<img src="https://imgur.com/2rVjuct.png" height="80%" width="80%" alt="Password Cracker Steps"/>
<br />hashed_password = hashlib.sha256(password.encode('utf-8')).hexdigest(): This line takes the password string and converts it into a SHA-256 hash.
<br />for username, hash in user_hash_dict.items(): This line initiates a loop that iterates through the items (key-value pairs) in the user_hash_dict.
<br />if hashed_password == hash:: Inside the loop, this line checks whether the hashed_password calculated in step 1 matches any of the stored hash values from the user_hash_dict. If a match is found, it indicates that the provided password is the same as the password previously associated with the username.

Hashes found:  <br/>
<img src="https://imgur.com/fpxYMmX.png" height="80%" width="80%" alt="Password Cracker Steps"/>
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
