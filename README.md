<h1>The Power of SUID</h1>

<h2>Description</h2>
Project consists of configuring a Set-User Identification (SUID) on one of the system's binaries to copy classified data with a regular user.
<br />


<h2>Utilities Used</h2>

- <b>VirtualBox</b>
- <b>Debian Environment</b>
- <b>Terminal</b>

<h2>Setting a Binary with SUID:</h2>
A binary is set with SUID to allow a regular user to access classified data. To do this, terminal is first logged in under our regular user:<br/>
<img src="https://imagizer.imageshack.com/img924/6914/TBdIPc.png" alt="Disk Sanitization Steps"/>
<br />
<br />
A file named secret.txt is created on the desktop. To verify, the Desktop directory is listed:<br/>
<img src="https://imagizer.imageshack.com/img922/7305/apx6k0.png" alt="Disk Sanitization Steps"/>
<br />
<br />
Attempting to copy the contents of the shadow file to secret.txt will prompt a command due to insufficient permissions:<br/>
<img src="https://imagizer.imageshack.com/img923/7898/UjnCT9.png" alt="Disk Sanitization Steps"/>
<br />
<br />
Attempting to print the contents of secret.txt will note that it is still an empty file:<br/>
<img src="https://imagizer.imageshack.com/img923/5659/5fmMJ9.png" alt="Disk Sanitization Steps"/>
<br />
<br />
The permissions of the shadow file are then printed using the ls -l command. This shows that only the root user has access to this file:<br/>
<img src="https://imagizer.imageshack.com/img924/3926/Rvuna4.png" alt="Disk Sanitization Steps"/>
<br />
<br />
The root user is switched to using su -:<br/>
<img src="https://imagizer.imageshack.com/img924/8104/W0tzKS.png" alt="Disk Sanitization Steps"/>
<br />
<br />
The permissions are then printed again, noting that it does not use SUID:<br/>
<img src="https://imagizer.imageshack.com/img924/1083/DKXBJH.png" alt="Disk Sanitization Steps"/>
<br />
<br />
A SUID is set on the cp binary to allow its execution with root permissions:<br/>
<img src="https://imagizer.imageshack.com/img924/1921/XPuLUD.png" alt="Disk Sanitization Steps"/>
<br />
<br />
The user is returned to using the exit command:<br/>
<img src="https://imagizer.imageshack.com/img922/63/R9Uqb7.png" alt="Disk Sanitization Steps"/>
<br />
<br />
Attempting to print the contents of the secret.txt file this time around will prove that the previous command was successful:<br/>
<img src="https://imagizer.imageshack.com/img923/2284/y6q7VF.png" alt="Disk Sanitization Steps"/>
<br />
<br />
The binary permissions are then returned to their former state:<br/>
<img src="https://imagizer.imageshack.com/img924/392/POdLjj.png" alt="Disk Sanitization Steps"/>
<br />
<br />
In terms of Linux Security, SUID plays a major role. It can grant or deny access to certain files within the sytstem by providing permissions to run the file as its owner. This is key, due to some files being only accesible through the root user. Using the root user is bad practice, due to it having complete control over the system with no restrictions. This can cause detrimental security incidents if handled incorrectly.
<br />
<br />

<h2>SUDO:</h2>
A binary is set with SUID to allow a regular user to access classified data. To do this, terminal is first logged in under our regular user:<br/>
<img src="https://imagizer.imageshack.com/img924/6914/TBdIPc.png" alt="Disk Sanitization Steps"/>
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
