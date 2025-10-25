# 🛡️ TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux


## 🎯 Overview:
This project demonstrates how to configure and test firewall rules on **Kali Linux** using **UFW (Uncomplicated Firewall)**.

---

## 📝 Step-by-Step Procedure:

## Linux:

1. **Enable Firewall**  
   Activated UFW to start filtering network traffic:  
   ```bash
   sudo ufw enable
   ```
   
   📸 Screenshot:
   
   ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/linux(1).png)


2. **List Current Rules**  
   Displayed existing rules with:  
   ```bash
   sudo ufw status numbered
   ```
   Output showed SSH (22/tcp) allowed and Telnet (23/tcp) denied.
   
   📸 Screenshot:  

   ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/linux(2).png)

3. **Block Telnet (Port 23)**  
   Added a deny rule:  
   ```bash
   sudo ufw deny 23/tcp
   ```
   Confirmed with `sudo ufw status numbered`.
   
    📸 Screenshot:  

   ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/linux(3).png)


4. **Test the Rule**  
   Verified Telnet was blocked using Telnet and Netcat:  
   ```bash
   telnet localhost 23
   nc -vz localhost 23
   ```
   Both returned **Connection refused**.
   
   📸 Screenshot:  

   ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/linux(4).png)


5. **Allow SSH (Port 22)**  
   Ensured SSH remained accessible:  
   ```bash
   sudo ufw allow 22/tcp
   ```
   Verified in `ufw status`.
   
   📸 Screenshot:  

   ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/linux(5).png)


6. **Remove Test Rule (Telnet Block)**  
   Deleted the Telnet deny rule to restore the firewall state:  
   ```bash
   sudo ufw delete deny 23/tcp
   ```
   Final rules allowed only SSH (22/tcp).
    
   📸 Screenshot:
   
  ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/linux(6).png)

---

## ✅Commands Used
```bash
sudo ufw enable
sudo ufw status numbered
sudo ufw deny 23/tcp
telnet localhost 23
nc -vz localhost 23
sudo ufw allow 22/tcp
sudo ufw delete deny 23/tcp
```

---

## 🚨 Firewall Summary
A **firewall** acts as a security filter between a system and external traffic.  
- **Allow rules** permit safe traffic (e.g., SSH on port 22).  
- **Deny rules** block unsafe or unused services (e.g., Telnet on port 23).  
By configuring firewall rules, we minimize exposure to attacks and ensure only authorized connections are allowed.

---



## Windows 11:

 ## 🧰 Tool: Windows Defender Firewall (GUI-based interface)


1. **Open Windows Firewall Settings:**
  Navigated to:
     Control Panel → System and Security → Windows Defender Firewall
     Clicked on 'Advanced Settings' from the left panel to access advanced rule configuration.

2. **View Current Firewall Rules:**
     Selected 'Inbound Rules' to view existing traffic rules.
     Observed default rules for applications and system services.

3. **Create Rule to Block Inbound Traffic on Port 23 (Telnet):**
    • Clicked 'New Rule' in Inbound Rules.
    • Selected 'Port' as the rule type.
    • Chose 'TCP', specified port 23.
    • Action: Block the connection.
    • Applied rule to: Domain, Private, Public.
    • Gave it a name: Telnet.

4. **Test the Block Rule:**
     Opened Command Prompt and attempted to connect using:
     telnet localhost 23

    📸 Screenshot:
   
  ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/windows(1).png)

  ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/windows(2).png)

  ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/windows(3).png)

  ![image alt](https://github.com/Rushikesh38-bit/TASK-NO-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/windows(4).png)

## 📝 Purpose:
   Port 23 is used by the insecure Telnet protocol. Blocking it prevents potential unauthorized access.


