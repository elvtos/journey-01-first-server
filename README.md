# Journey 01: First Server

🚀 My first self-hosted Flask application deployed on Ubuntu Server using NGINX as a reverse proxy.

---

## 📦 Stack

- Ubuntu Server (installed in UTM on macOS)
- Python 3 + Flask (development server)
- NGINX (reverse proxy)
- UFW (Uncomplicated Firewall)

---

## 🛠️ What I Did

1. Installed Ubuntu Server in UTM virtual machine
2. Set up Python and Flask
3. Created a simple Flask app
4. Ran the Flask app on port `5000`
5. Installed and configured NGINX to reverse proxy to the Flask app
6. Enabled HTTP/HTTPS access with `ufw`

---

## 🌐 Result

- The Flask app is accessible via `http://<server-ip>/` (no need to specify `:5000`)
- NGINX forwards requests to the running Flask development server
- UFW firewall allows ports 80 (HTTP) and 443 (HTTPS)

---

## 🧪 Test the App

Run the app manually:

```bash
python3 app.py
```

Then access it in your browser:

```
http://<your-server-ip>/
```

Make sure Flask is bound to 0.0.0.0 in app.py:

```
app.run(host='0.0.0.0', port=5000)
```

## 🔐 Firewall Settings

```
sudo ufw allow 443
sudo ufw allow 80
sudo ufw enable
```

## 🧠 Lessons Learned

	•	How to install and use a basic Ubuntu Server in a virtual machine
	•	How to build a minimal web app with Flask
	•	How to configure NGINX as a reverse proxy
	•	How to use UFW to allow traffic securely

## 🎯 Purpose

This is the first step in my journey to becoming a Linux systems administrator and DevOps engineer.  
I’m learning how to configure servers, deploy applications, and manage infrastructure using real tools and technologies.

---

> More projects coming soon — follow the journey!

## 🔗 Next Steps

- [Journey 02: Dockerizing Flask](https://github.com/yourusername/journey-02-dockerizing-flask)
- [Journey 03: PostgreSQL Setup](https://github.com/yourusername/journey-03-postgresql-setup)
- [Journey 04: Monitoring with Prometheus](https://github.com/yourusername/journey-04-monitoring-prometheus)
