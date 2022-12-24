[TryHackMe | Stego_Shabby](https://tryhackme.com/room/stegoshabby)

# Download Task File
![[Pasted image 20221223211714.png]]
It's an image file, maybe there is something hide it, let's check it out.

# Binwalk
syntax:
> binwalk -M

![[Pasted image 20221223211906.png]]
We can see there is Zip file here and a file.txt, maybe it's the key.
> binwalk -e

Extract the file
![[Pasted image 20221223212343.png]]
Let's check the file.txt, but it's nothing in it.
Then let's check the zip file, it needs password, obviously.
# John the Ripper 
syntax:
> zip2john 1C5f17.zip > output
>john --wordlist=/usr/share/wordlists/rockyou.txt output
> john --show output

![[Pasted image 20221223213204.png]]
# Unzip
syntax:
> unzip 1C5F17.zip

![[Pasted image 20221223223518.png]]

![[Pasted image 20221223223731.png]]
# Base64
we can decode this base64 online or in Kali
![[Pasted image 20221223223949.png]]
And we find the flag!