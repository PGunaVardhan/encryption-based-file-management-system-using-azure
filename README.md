

# Encryption-Based File Management System

---

## 1. Abstract

The **encryption-based file management system** is a secure and efficient solution for storing, accessing, and managing files while ensuring data confidentiality and integrity. Designed with robust cryptographic techniques, the system encrypts files before storage, preventing unauthorized access and safeguarding sensitive information.  

A **command-line interface (CLI)** serves as the user interface, offering a lightweight and versatile environment for executing operations such as file upload, retrieval, deletion, and decryption. The system emphasizes usability alongside security, allowing users to interact seamlessly with encrypted data through straightforward commands while maintaining rigorous protection against data breaches.  

The system's modular design ensures adaptability, making it suitable for personal use or integration into larger workflows where data security is paramount. The CLI's simplicity ensures cross-platform compatibility and minimizes resource overhead. By prioritizing encryption and secure key management, the project addresses contemporary challenges in digital file handling, catering to the needs of privacy-conscious users and organizations.

---

## 2. Introduction

In an era where **data privacy** is paramount, this project aims to develop a robust encryption-based file management system to safeguard user data while ensuring seamless access and usability.  

The system operates through a **command-line interface (CLI)**, enabling users to:  
- Sign up for a secure account or sign in to an existing one.  
- Manage files and folders.  
- Store sensitive data like passwords.  

All operations are executed with encryption protocols in place, ensuring that data is protected during storage and transmission to the cloud.  

### Core Features:
1. **Encryption during Upload**: Files are encrypted before being securely stored in Azure Blob Storage.  
2. **Decryption during Download**: Encrypted files are decrypted during retrieval to maintain data confidentiality.  
3. **Additional Utilities**: Includes folder management and password storage for versatile use cases.  

The CLI ensures **lightweight operation and cross-platform compatibility**, making the system a versatile tool for privacy-conscious users seeking a reliable, secure, and user-friendly file management solution.

---

## 3. Methodology

The system is built using **Python**, integrating:  
- **CLI** for user interaction.  
- **Azure Blob Storage** for file storage.  
- **Azure SQL Database** for user management.  

### Workflow Overview

![image](https://github.com/user-attachments/assets/6206dd69-61e8-4490-8604-91717775dccc)

#### 1. User Authentication and Management
- **Signup**:  
  - Users register via `signup.py` by providing a username and a secure password (8–16 characters, at least one digit, uppercase letter, and special character).  
  - Credentials are stored securely in Azure SQL using **pyodbc**.  

- **Login**:  
  - Users authenticate via `login.py`. Credentials are fetched and validated against the Azure SQL database.  
  - Repeated attempts are permitted until the correct password is entered.  

#### 2. File Encryption and Upload
- **Encryption**:  
  - Files are selected using a GUI file dialog (`upload.py`, implemented with tkinter).  
  - Encrypted using **Fernet** (symmetric encryption), and an `.encrypted` extension is added.  

- **Upload**:  
  - Encrypted files are uploaded to Azure Blob Storage via the **BlobServiceClient**.  
  - Temporary encrypted files can be removed post-upload to save local storage.  

#### 3. File Decryption and Download
- **Download**:  
  - Encrypted files are retrieved from Azure Blob Storage using `download.py`.  

- **Decryption**:  
  - Files are decrypted locally using the Fernet key and saved with their original names.  

#### 4. Command-Line Interface (CLI)
- **CLITool.py** serves as the central CLI for all operations (signup, login, upload, download).  

#### 5. Database Connection Management
- **connection.py** manages interaction with Azure SQL for seamless database operations and robust exception handling.  

---

## 4. Results
![image](https://github.com/user-attachments/assets/0af0b84d-011d-4ed4-b785-268c04921d7c)
![image](https://github.com/user-attachments/assets/ccc46960-29bc-490a-aebe-3f33b9b7face)
![image](https://github.com/user-attachments/assets/682ffc96-1c2f-4bcd-8299-bd673f55621a)
![image](https://github.com/user-attachments/assets/21fdb388-80e5-4bb0-a016-dc877fc2a946)
![image](https://github.com/user-attachments/assets/4a77e586-b1d8-4306-abcd-1a53f3d86794)
![image](https://github.com/user-attachments/assets/46042bd9-9457-49fe-b848-7be0d0619cac)
![image](https://github.com/user-attachments/assets/4a19a736-3b87-466c-b117-d4f1fa02116f)



---

## 5. Results and Discussion

### Discussion Points:
1. **Security**:  
   - Enhance encryption using **AES-GCM** and secure key storage with **HSMs** or cloud-based key vaults.  

2. **Performance**:  
   - Optimize large file handling with **chunk-wise encryption and upload**.  

3. **User Experience**:  
   - Develop a GUI for broader accessibility while retaining CLI functionality for advanced users.  

4. **Error Handling**:  
   - Improve logging for detailed monitoring of file operations.  

5. **Future Scope**:  
   - Add multi-factor authentication.  
   - Introduce file-sharing features.  
   - Expand to mobile or web platforms.  

---

## 6. Conclusion

This **encryption-based file management system** successfully integrates encryption, cloud storage, and user authentication into a cohesive solution, ensuring data security throughout its lifecycle.  

The **modular design** allows for future enhancements, such as multi-factor authentication, improved encryption algorithms, and GUI integration. By prioritizing usability and security, this project demonstrates a practical implementation of secure file management tailored to modern needs.

--- 
