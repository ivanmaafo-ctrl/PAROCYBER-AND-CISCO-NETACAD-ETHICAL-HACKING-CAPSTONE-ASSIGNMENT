# PAROCYBER-AND-CISCO-NETACAD-ETHICAL-HACKING-CAPSTONE-ASSIGNMENT
**Prepared and submitted by Ivan Maafo**

---

## Challenge 1: SQL Injection

### Step 1: Preliminary setup
1. Open a browser and go to **10.5.5.12**
2. Login with:
   - **Username:** admin
   - **Password:** password
3. Set DVWA security level to **Low** and click **Submit**

### Step 2: Retrieve Bob Smith’s credentials
1. Identify the table containing usernames and passwords  
   - Test SQL injection using: `' OR 1=1 #`  
   - Result: Application is vulnerable to SQL injection

2. Check number of fields in the query  
   - Use: `1' ORDER BY 1#`

3. Determine the database name  
   - Use: `1' OR 1=1 UNION SELECT 1, DATABASE()#`  
   - **Database name:** dvwa

4. Retrieve table names  
   - Use:  
     `1' OR 1=1 UNION SELECT 1, table_name FROM information_schema.tables WHERE table_type='base table' AND table_schema='dvwa'#`  
   - **Table found:** users

5. Retrieve Bob Smith’s credentials  
   - Use:  
     `1' OR 1=1 UNION SELECT user, password FROM users #`  
   - **Username:** smithy  
   - **Password hash:** [retrieved]

6. Crack password using CrackStation  
   - **Password:** password

### Step 3: Locate Challenge 1 code file
1. Log into **192.168.0.10** as Bob Smith  
2. Navigate to DVWA and login as **smithy** with password **password**

**File with code:** `my_passwords.txt`  
**Message/code inside the file:** [enter code]

### Step 4: Remediation methods for SQL Injection
- Use prepared statements  
- Validate and sanitize user input  
- Use secure stored procedures  
- Apply least privilege to database accounts  
- Use a web application firewall  

---

## Challenge 2: Web Server Vulnerabilities

### Step 1: Preliminary setup
1. Login to server at **10.5.5.12**  
   **admin / password**  
2. Set application security level to **Low**

### Step 2: Discover viewable directories
- Accessible directory:  
  **http://10.5.5.12/config/**

### Step 3: Find the Challenge 2 code file
- Search within accessible directories to find the file containing the code  
- Subdirectories to check:  
  - [list directories]

### Step 4: Remediation methods for Directory Listing
- Validate user-supplied input  
- Ensure canonicalized path starts with the expected base directory  

---

## Challenge 3: Exploit Open SMB Server Shares

### Step 1: Scan for SMB targets
- Scan network **10.5.5.0/24**  
- **Host with SMB services:** 10.5.5.14

### Step 2: Find SMB shares accessible anonymously
- Identify shares and which ones allow anonymous access

### Step 3: Locate the Challenge 3 file
- Access SMB shares using SMB client  
- **File found in:** [share name]  
- **File name:** `sxij42.txt`  
- **Code:** [enter code]

### Step 4: SMB remediation methods
- Ensure all SMB-enabled devices are patched and use SMBv2/v3  
- Implement strong passwords and MFA

---

## Challenge 4: Analyze a .pcap File

### Step 1: Analyze SA.pcap
- Determine target IP address  
- Identify directories revealed in the capture  

### Step 2: Access URL to find the file
- Find file containing Challenge 4 code  
- **URL:** [enter URL]  
- **Content/message:** [enter message]  
- **Code:** [enter code]

### Step 3: Remediation for cleartext file transmission
- Implement IPsec VPN tunnels to encrypt traffic  
- Use Data Loss Prevention (DLP) tools to block unencrypted file transfers  
