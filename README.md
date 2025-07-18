# 🚀 LibreSpeed - Self-Hosted Internet Speed Test

LibreSpeed is a **lightweight**, **fully open-source** internet speed test tool that you can run on **your own server** 🖥️—no third-party tracking, no external dependencies, and no Flash or Java required!  

With LibreSpeed, you can measure:
- 📥 **Download Speed**
- 📤 **Upload Speed**
- 🛰️ **Ping (Latency)**
- 🔁 **Jitter (Latency Variation)**
- 🌐 **Public IP Address**

<img width="2772" height="941" alt="image" src="https://github.com/user-attachments/assets/1fd2a7b2-70a5-4fcf-8f7c-64fb32658e9e" />

## 🌍 Browser Compatibility

LibreSpeed supports **all modern web browsers**:

- ✅ Internet Explorer 11
- ✅ Microsoft Edge (Latest)
- ✅ Google Chrome (Latest)
- ✅ Mozilla Firefox (Latest)
- ✅ Apple Safari (Latest)
- ✅ Android/iOS Browsers (Mobile Support Included)

## 🔧 Key Features

✔️ Easy to use web interface  
✔️ Accurate **Download/Upload** speed measurement  
✔️ Realtime **Ping & Jitter** results  
✔️ Shows **Client IP address**  
✔️ Customizable interface & backend  
✔️ Optional **results logging** to database  

🗃️ Advanced (Optional):
- Save test results in a **MySQL/MariaDB** database
- Analyze historical data with charts or dashboards

## 🧰 Server Requirements

To deploy LibreSpeed on **Ubuntu Server**, you’ll need:

- ✅ A fast and stable **Internet connection**
- ✅ A working **Apache2**, **nginx**, or **IIS** web server
- ✅ **PHP 5.4 or newer**
- (Optional) **MariaDB/MySQL** for results logging

Supported databases:
- MySQL / MariaDB ✅  
- PostgreSQL ✅  
- SQLite ✅  
- Microsoft SQL Server ✅

## 🐧 Ubuntu Installation Guide (Recommended Setup)

Follow these steps to install LibreSpeed on Ubuntu (20.04 or later):

### 📦 Required Packages

🗃️ 1. Install 

sudo apt update && sudo apt upgrade -y
sudo apt install apache2 php libapache2-mod-php unzip git -y

<img width="1191" height="79" alt="image" src="https://github.com/user-attachments/assets/0d51c928-e24e-4d18-acc6-11fe3cb645c4" />


📁 2. Download LibreSpeed Files

cd /var/www/html
sudo git clone https://github.com/librespeed/speedtest.git
sudo mv speedtest librespeed
cd librespeed

🔒 3. Set Permissions

sudo chown -R www-data:www-data /var/www/html/librespeed
sudo chmod -R 755 /var/www/html/librespeed

🌐 4. Enable Apache and Restart

sudo systemctl enable apache2
sudo systemctl restart apache2
Now visit your server in a browser:

✅ 5. Start testing your internal/external bandwidth directly!

http://YOUR_SERVER_IP/librespeed/index.html
You should see the LibreSpeed test interface ready to use! 🎉

🗃️ Optional: Enable Result Logging (Database)

#1. Configure Database

sudo mysql -u root -p
Then in MySQL shell:

sql
CREATE DATABASE librespeed;
CREATE USER 'speeduser'@'localhost' IDENTIFIED BY 'strongpassword';
GRANT ALL PRIVILEGES ON librespeed.* TO 'speeduser'@'localhost';
FLUSH PRIVILEGES;
EXIT;

#2. Set Up Tables

cd /var/www/html/librespeed/results
mysql -u speeduser -p librespeed < telemetry_mysql.sql

#3. Configure Backend
Edit the config file:

sudo nano /var/www/html/librespeed/results/config.php
Update your DB credentials accordingly.

🎯 Access the Speed Test
Open your browser and go to:

http://your-server-ip/librespeed/
✅ Start testing your internal bandwidth directly!

📝 Notes
LibreSpeed does not use third-party CDN or external services
Ideal for ISPs, corporate networks, universities, or home labs
Easy to customize look & feel via HTML/CSS

🧑‍💻 Project Links
🔗 Official GitHub Repo

🌐 LibreSpeed Website

💬 Community Support & Discussions

⚖️ License
LibreSpeed is licensed under the GNU GPL v3 license.

🙏 Credits
Developed and maintained by the open-source community at https://librespeed.org.
Customized & deployed for self-hosted networks by 🚀 you!

# 🧡 Happy Testing!

Open your browser and navigate to:


✅ Start testing your **internal** network bandwidth instantly — right from your browser!

🌐 URL: http://YOUR_SERVER_IP/librespeed

📊 After each test, LibreSpeed will display:
- 📥 **Download Speed** (in Mbps)
- 📤 **Upload Speed** (in Mbps)
- 🛰️ **Ping** (in ms)
- 🔁 **Jitter** (in ms)
- 🌐 Your **Internal IP Address**

No clutter, no ads — just clean, real-time results! 🚀

<img width="1013" height="830" alt="image" src="https://github.com/user-attachments/assets/d2e762dc-0481-4cc0-a14e-b6a41d95066e" />

