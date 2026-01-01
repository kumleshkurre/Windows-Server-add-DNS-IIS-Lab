# 🖥️ Host Server Configuration – IIS & DNS Based Website Hosting

This section explains the **step-by-step configuration performed entirely on a single Host Server machine**.  
The Host Server is responsible for **IP configuration, IIS setup, DNS configuration, and website hosting**.

---

 ## 🖥️ 1️⃣ Configure IP Address on Host Server

- Press **Windows + R**
- Type `ncpa.cpl` → Press **Enter**
- Right-click the **Ethernet adapter** → **Properties**
- Select **Internet Protocol Version 4 (TCP/IPv4)** → **Properties**
- Configure the IP address as follows:

&emsp;&emsp;IP Address : 10.0.0.1 <br>
&emsp;&emsp;Subnet Mask : 255.0.0.0

- Click **OK**

---

## 🧠 2️⃣ DNS Server Role Installation

- Open **Server Manager**
- Click **Add Roles and Features**
- Select and install:
  - ✅ **DNS Server**
  - ✅ **Web server(IIS)**
- Complete the installation and close the wizard

---

## 🧾 3️⃣ DNS Configuration (Forward Lookup Zone)

- Open **Server Manager**
- Go to **Tools → DNS**
- Right-click **Forward Lookup Zones** → **New Zone**
- Select:
  - ☑️ **Primary Zone** (First DNS Server)
- Create a zone name, for example:
kurrecomputers.local
- Click **Next** (2 times)
- Click **Finish**

---

## 🧩 4️⃣ Add Host (A Record) in DNS

- Open **DNS Manager**
- Right-click the zone **kurrecomputers.local**
- Click **New Host (A or AAAA)**

Configuration:
Name : host server
IP Address : 10.0.0.1

- Click **Add Host**
- Click **OK**

---

## 🧾 5️⃣ IIS Website Configuration
🔹 Remove Default Website

- Open Server Manager
- Go to Tools → Internet Information Services (IIS) Manager
- Click on the Server Name (left panel)
- Expand Sites
- Right-click Default Web Site → Remove

## Add Custom Website

Navigate to:
C:\inetpub\wwwroot

- Paste your website file (e.g. `index.html`)

- Go back to **IIS Manager**
- Right-click **Sites** → **Add Website**

Configuration:<br>
&emsp;&emsp;Site Name : kurrecomputers<br>
&emsp;&emsp;Physical Path : C:\inetpub\wwwroot<br>
&emsp;&emsp;Binding Type : http / https<br>
&emsp;&emsp;IP Address : host server (e.g. `10.0.0.1`)

- Click **OK**

## Set Default Document

- Select your website (e.g. `kurrecomputers`)
- Click **Default Document**
- Click **Add**
- Enter: web site folder name
 index.html
- Click **OK**

---

## 🌐 6️⃣ Access Website from Client PC

- Ensure client PC is connected to the **same network**
- Open any web browser
- Type the website name:
- kurrecomputers
 
✅ Website should open successfully using DNS name resolution.

---

## ✅ Final Result

✔️ Static IP configured on Host Server
✔️ IIS installed and configured
✔️ Custom website hosted
✔️ DNS A record created
✔️ Website accessible from client machine using domain name

---

## 👨‍💻 Author

**Kumlesh Kurre**  
Bachelor of Computer Applications (BCA) – Pursuing  
IT Support & Networking Enthusiast  

---

⭐ If you find this project helpful, please give it a star on GitHub.


