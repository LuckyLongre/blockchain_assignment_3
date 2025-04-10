# IPFS Privacy and Encryption – Command Line Assignment

This project explains how to securely upload, encrypt, decrypt, and manage file privacy using **IPFS (InterPlanetary File System)** and **OpenSSL** via the command line.

---

## Objective

The aim is to learn how to:
- Add files to IPFS
- Encrypt files using AES-256 (OpenSSL)
- Decrypt encrypted files
- Store data privately on a decentralized file system

---

## Steps

### Step 1: Create a file with sample text
```bash
echo "Hello, IPFS!" > myfile.txt
```

![Step 1](images/Step1_Create_myfile.png)

---

### Step 2: Add the original file to IPFS
```bash
ipfs add myfile.txt
```

![Step 2](images/Step2_Add_myfile_to_IPFS.png)

---

### Step 3: Encrypt the file with AES-256-CBC using OpenSSL
```bash
openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -in myfile.txt -out myfile_encrypted.txt -pass pass:Lucky@123
```

![Step 3](images/Step3_Encrypt_myfile.png)

---

### Step 4: Upload the encrypted file to IPFS
```bash
ipfs add myfile_encrypted.txt
```

![Step 4](images/Step4_Add_Encrypted_File_to_IPFS.png)

---

### Step 5: View the encrypted file
```bash
cat myfile_encrypted.txt
```

![Step 5](images/Step5_View_Encrypted_Content.png)

---

### Step 6: Decrypt the file using the same password
```bash
openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -in myfile_encrypted.txt -out decrypted_file.txt -pass pass:Lucky@123
```

![Step 6](images/Step6_Decrypt_File_Success.png)

---

### Step 7: Check the decrypted content
```bash
cat decrypted_file.txt
```

![Step 7](images/Step7_Verify_Decrypted_Content.png)

---

### Step 8: Upload the decrypted file to IPFS again
```bash
ipfs add decrypted_file.txt
```

![Step 8](images/Step8_Add_Decrypted_File_to_IPFS.png)

---

## Conclusion

This task shows how to:
- Encrypt data before storing it on IPFS
- Use strong encryption to protect access
- Verify integrity by decrypting and comparing files
- Understand content-based addressing in IPFS

> **Note:** Always keep your encryption password secure to protect your data on decentralized platforms.

---

