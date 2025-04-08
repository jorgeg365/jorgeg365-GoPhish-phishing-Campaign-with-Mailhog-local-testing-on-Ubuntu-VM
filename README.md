# jorgeg365-GoPhish-phishing-Campaign-with-Mailhog-local-testing-on-Ubuntu-VM

🧰 Full Setup: GoPhish + MailHog on Ubuntu VM
✅ Prerequisites
Make sure your Ubuntu VM is up to date:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install unzip curl wget git -y
```
🧑‍💻 Step 1: Install GoPhish
1. Download the latest GoPhish release

```bash
wget https://github.com/gophish/gophish/releases/download/v0.12.1/gophish-v0.12.1-linux-64bit.zip
unzip gophish-v0.12.1-linux-64bit.zip
cd gophish
```
-cd gophish- did not work for me so use this if that's the case 

```bash
chmod +x gophish
```
2. Run GoPhish

```bash
sudo ./gophish
```
You’ll see output showing:

Admin server on https://127.0.0.1:3333

Phishing server on http://0.0.0.0:80

⚠️ First-time use will show a default admin password—copy it.

![Screenshot 2025-04-08 172702](https://github.com/user-attachments/assets/4c32489e-dc38-4b16-9d1c-ede489f8d598)


🔐 Step 2: Access GoPhish Admin Interface
In your browser, go to:

```bash
https://localhost:3333
```

Login using:

Username: admin

Password: (from the terminal output)

You can change the password in config.json later if needed.

![Screenshot 2025-04-08 172738](https://github.com/user-attachments/assets/771c11f8-e7b9-46cb-b3ce-01a5db4919e0)

📬 Step 3: Install MailHog (SMTP Catcher)
Option A: Install with Go (cleanest option)
```bash
sudo apt install golang-go -y
go install github.com/mailhog/MailHog@latest
```
Run MailHog:
```bash
~/go/bin/MailHog
```
You have to run both Gophish and MailHog at the same time so you need to use screen -S
🖥️ Install screen on Ubuntu
Just run:
```bash
sudo apt update
sudo apt install screen -y
```
Find MaiHog in Directory should be 

![Screenshot 2025-04-08 181803](https://github.com/user-attachments/assets/7933a412-3cf9-4187-8293-6a435e6255eb)

then run 
```bash
screen -S MailHog
```
press ctrl + a + d   to keep it running and be able to start Gophish
![Screenshot 2025-04-08 182003](https://github.com/user-attachments/assets/5df95e74-b796-45b1-816f-48e2d1098507)

Go back to gophish browser and refresh page and re log-in
I'll use my example
Go to Users & Groups and name is Facebook put Joe Fname and Joe Lname email I google a temporay email site and filled that slot with that. Save changes

![Screenshot 2025-04-08 174448](https://github.com/user-attachments/assets/7df71c25-04b3-48c8-a8f4-bcae62b6957b)







