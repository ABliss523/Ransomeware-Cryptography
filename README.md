# Ransomeware-Cryptography
### Background

You will play the role of a cybersecurity analyst at Nakatomi Hospital.

- Unfortunately, one of the hospital's doctors opened up an email containing ransomware.

- This ransomware spread throughout the hospital and encrypted all of the Patient Records.

- The ransomware has given you two options to decrypt and retrieve the patient records: Either pay 100 bitcoins or solve six riddles.

- Since you refuse to pay off any ransom, you'll have to solve six cryptographic riddles. Act fast: the doctors need to access the patient records as lives are at stake!

### Riddle 1
![](https://github.com/ABliss523/Ransomeware-Cryptography/blob/main/Ransomeware%20Riddles/riddle1.jpg)

The first riddle uses the Caesar (ROT) cipher.
- The cipher appears to have used a rotation of 8. 
- The decryptions results in the word: `gruber`.
- After submitting the decrypted cipher, the following key was given: `6skd8s`.

### Riddle 2
![](https://github.com/ABliss523/Ransomeware-Cryptography/blob/main/Ransomeware%20Riddles/riddle2.jpg)

The second riddle is in binary, we will need to be convert it into a plaintext message.

- Once decryption of `01000111 01100101 01101110 01101110 01100101 01110010 01101111`  is the word: `Gennero`.

- After decrypting, the following key was given: `cy8snd2`.

### Riddle 3
![](https://github.com/ABliss523/Ransomeware-Cryptography/blob/main/Ransomeware%20Riddles/riddle3.jpg)
 
This third riddle will need to be done within the Ubuntu VM, we will use OpenSSL.
- First, add the ciphertext into a file with the command:
  - `echo "4qMOIvwEGXzvkMvRE2bNbg==" > cipher.txt`

- Then, the following openSSL command will then be ran against this file:
  - `openssl enc -pbkdf2 -nosalt -aes-256-cbc -d -in cipher.txt -base64 -K 5284A3B154D99487D9D8D8508461A478C7BEB67081A64AD9A15147906E8E8564 -iv 1907C5E255F7FC9A6B47B0E789847AED`

- This decrypts the ciphertext and displays the following message: `takagi`.
- After decrypting, the following key was given: `ud6s98n`. 


### Riddle 4
![](https://github.com/ABliss523/Ransomeware-Cryptography/blob/main/Ransomeware%20Riddles/riddle4.jpg)

The fourth riddle determines communication between public keys and determines the following:
1. Jack uses Jill's public key to encrypt a message that will be sent to Jill. 
2. Jill would then decrypt this message with her private key.
3. For Jack, Jill, Bob, and Tim to exchange messages, they would need the following asymmetric and symmetric encryptions:
    - **Asymmetric** = 6 * 2 = 12 Keys
    - **Symmetric** = (6 * (6 -1))/2 = (6 * 5)/2 =  30/2 = 15 Keys
4. If Tim sends an encrypted message to one of his friends, he would use someone else's public key to encrypt a message.
5. The only other person's public key is Alice. 
  
Once these questions are answered, the following key was given: **7gsn3nd2**

### Riddle 5
![](https://github.com/ABliss523/Ransomeware-Cryptography/blob/main/Ransomeware%20Riddles/riddle5.jpg)

  - **Hash:**  `3b75cdd826a16f5bba0076690f644dc7`
  
With the fifth riddle, we will use hashcat to crack the MD5 hash:

- First, add hash into a file with the command:
  - `echo "3b75cdd826a16f5bba0076690f644dc7"  > hash.txt`

- Next, run hashcat to crack it with the command:
  - `hashcat -m 0 -a 0 -o solved.txt hash.txt /usr/share/rockyou.txt --force`

- Inside the `solved.txt` file was: `3b75cdd826a16f5bba0076690f644dc7:argyle`

When `argyle` is submitted as the solution, you are provided the following key: `ajy39d2`. 
 

### Riddle 6
![](https://github.com/ABliss523/Ransomeware-Cryptography/blob/main/Ransomeware%20Riddles/riddle6.jpg)

The sixth riddle will require steghide to decrypt the hidden message inside an image.
- First, download the image into your Ubuntu VM and use the command:
  - `steghide extract -sf mary-lamb.jpg`
- This will prompt a requested passphrase, which is written on the book in the image:  `ABC`.
- After entering the passphrase, the following file will be extracted: `code_is_inside_this_file.txt`.
- Inside this file is the code: `mcclane`
- After submitted the code given, the following key was provided: `7skahd6`.


## Ransomware Decrypted:
After submitting all the keys, the following response was provided:

 ![](https://github.com/ABliss523/Ransomeware-Cryptography/blob/main/Ransomeware%20Riddles/Ransomeware%20Decrypter.PNG)

