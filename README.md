# 🔐 IPFS Privacy and Encryption – Command Line Assignment

This project demonstrates how to securely upload, encrypt, decrypt, and manage file privacy using **IPFS (InterPlanetary File System)** and **OpenSSL** through the command line.

---

## 📌 Objective

To understand how to:
- Add files to IPFS
- Perform AES-256 encryption using OpenSSL
- Decrypt encrypted files
- Maintain privacy while storing data on a decentralized file system

---

## 🧪 Steps Performed

### ✅ Step 1: Create a file with sample text
```bash
echo "Hello, IPFS!" > myfile.txt
```
📸  
![Step 1](images/Step1_Create_File.png)

---

### ✅ Step 2: Add original file to IPFS
```bash
ipfs add myfile.txt
```
📸  
![Step 2](images/Step2_Add_Original_File_to_IPFS.png)

---

### ✅ Step 3: Encrypt the file using AES-256-CBC (OpenSSL)
```bash
openssl enc -aes-256-cbc -pbkdf2 -iter 100000 -salt -in myfile.txt -out myfile_encrypted.txt -pass pass:Lucky@123
```
📸  
![Step 3](images/Step3_Encrypt_File.png)

---

### ✅ Step 4: Add the encrypted file to IPFS
```bash
ipfs add myfile_encrypted.txt
```
📸  
![Step 4](images/Step4_Add_Encrypted_File_to_IPFS.png)

---

### ✅ Step 5: View encrypted file contents
```bash
cat myfile_encrypted.txt
```
📸  
![Step 5](images/Step5_View_Encrypted_Content.png)

---

### ✅ Step 6: Decrypt the file using the same password
```bash
openssl enc -d -aes-256-cbc -pbkdf2 -iter 100000 -in myfile_encrypted.txt -out decrypted_file.txt -pass pass:Lucky@123
```
📸  
![Step 6](images/Step6_Decrypt_File_Success.png)

---

### ✅ Step 7: Verify the decrypted content
```bash
cat decrypted_file.txt
```
📸  
![Step 7](images/Step7_Verify_Decrypted_Content.png)

---

### ✅ Step 8: Add decrypted file back to IPFS
```bash
ipfs add decrypted_file.txt
```
📸  
![Step 8](images/Step8_Add_Decrypted_File_to_IPFS.png)

---

## 📄 Conclusion

This assignment successfully demonstrates how to:
- Secure sensitive data before uploading to IPFS
- Protect access using AES encryption
- Verify data integrity by decrypting it again
- Understand how IPFS uses content-based addressing (same file = same CID)

> 🔐 **Security Tip:** Always keep your encryption password secret to maintain privacy on decentralized platforms.

---

