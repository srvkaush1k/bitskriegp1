# Autorev1
## Approach
I ran the netcat command and it only said that it will send 20 bytes and that i had to give the correct password within 1 second each
to automate this i had to first find where the password was and then store that and a variable and make a loop to send all passwords 
to the server to get the flag
## Solution
```
srv@srv-Yogapad:~/Downloads/red$ nc mysterious-sea.picoctf.net 57897
Welcome! I think I'm pretty good at reverse enginnering.
There's NO WAY anyone's better than me.
Wanna try? I have 20 binaries I'm going to send you
and you have 1 second EACH to get the secret in each one. Good luck >:)
2093224266
Here's the next binary in bytes:
```
This was for the first flag so i have to read until the angry face emoticon and the next line looks like the password 
the program is expecting
```
What's the secret?:
```
after a bunch of binaries the program asks for an input where i have to write a program to automatically send the stored password
If the correct password is sent, the program similarly sends the second password which is the next line after
```
Correct!
```
After reading the password in the next line again i had to receive a bunch of binaries until the program asked for the password input
Only the first password was to be recorded after the angry face emoticon rest all were to be recorded after **Correct!**
So i did a for loop for all the passwords from second to the twentieth

this is the code
```python
from pwn import *

url = "mysterious-sea.picoctf.net"
port = 57897
p = remote(url,port)
print("1/20")
p.recvuntil(b">:)\n")
code = p.recvline().strip()
p.recvuntil(b"What's the secret?:")
print(code)
p.sendline(code)
for i in range(2,21):
    print(f"{i}/20")
    p.recvuntil(b"Correct!\n")
    code = p.recvline().strip()
    print(code)
    p.recvuntil(b"What's the secret?:")
    p.sendline(code)

p.interactive()
```
## Takeaway
look for a pattern in which the server sends codes and automate the process


