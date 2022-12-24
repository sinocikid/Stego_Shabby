[TryHackMe | Stego_Shabby](https://tryhackme.com/room/stegoshabby)

# Download Task File
![Pasted image 20221223211714](https://user-images.githubusercontent.com/91645007/209423234-24e7efaf-99d7-45ee-81fc-8c4a1c415aad.png)
It's an image file, maybe there is something hide it, let's check it out.

# Binwalk
syntax:
```
binwalk -M
```

![Pasted image 20221223211714](https://user-images.githubusercontent.com/91645007/209423208-4a397733-085e-42a5-a7e5-89fae5936d47.png)

We can see there is Zip file here and a file.txt, maybe it's the key.
```
binwalk -e
```
Extract the file
![Pasted image 20221223212343](https://user-images.githubusercontent.com/91645007/209423211-2ab5af46-0041-47c3-8244-a6e5ecebfa6a.png)
Let's check the file.txt, but it's nothing in it.
Then let's check the zip file, it needs password, obviously.
# John the Ripper 
syntax:
```
zip2john 1C5f17.zip > output
john --wordlist=/usr/share/wordlists/rockyou.txt output
john --show output
```
![Pasted image 20221223213204](https://user-images.githubusercontent.com/91645007/209423214-d731557d-3c37-4102-8669-e24f0e9091af.png)

# Unzip
syntax:
```
unzip 1C5F17.zip
```
![Pasted image 20221223223518](https://user-images.githubusercontent.com/91645007/209423216-51115b9a-1caa-45f4-b789-7ae95ea905d1.png)

![Pasted image 20221223223731](https://user-images.githubusercontent.com/91645007/209423218-b28167d5-7d51-4759-befd-39f6d56f2666.png)

# Base64
we can decode this base64 online or in Kali
![Pasted image 20221223223949](https://user-images.githubusercontent.com/91645007/209423219-3305716e-5e25-42c6-9848-e099a7bf80fd.png)
And we find the flag!
