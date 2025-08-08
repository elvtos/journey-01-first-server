# Journey 01: First Server

This project demonstrates the setup of a web server on Ubuntu Server 24.04 LTS using a virtual machine (UTM on macOS). It includes a simple Flask application served via Nginx as a reverse proxy.

## Features
- Basic Flask application running on Ubuntu Server.
- Nginx configured as a reverse proxy to route traffic from port 80 to the Flask app on port 5000.
- Secure access with firewall rules (ports 80 and 443 allowed).

## Setup Instructions
1. Install Ubuntu Server 24.04 LTS:
   - Set up a virtual machine using UTM on macOS with the Ubuntu Server 24.04 LTS ARM64 ISO.
   - Update the system:
```
sudo apt update && sudo apt upgrade -y
```

2. Install Dependencies:
   - Install required packages:
```
sudo apt install -y nginx python3 python3-pip python3-venv
```

3. Create and Configure the Flask App:
   - Create a project directory:
```
mkdir ~/web-app && cd ~/web-app
```
   - Set up a virtual environment:
```
python3 -m venv venv
```
   - Activate it:
```
source venv/bin/activate
```
   - Install Flask:
```
pip install flask
 ```

   - Create app.py with the following content: [app.py](app.py)

- Run the app:
```
python app.py &
```

4. Configure Nginx as a Reverse Proxy:
   - Create a configuration file:
```
sudo nano /etc/nginx/sites-available/flask-app
```

   - Add the following: [nginx/flask-app](nginx/flask-app)

- Enable the configuration:
```
sudo ln -s /etc/nginx/sites-available/flask-app /etc/nginx/sites-enabled/
```
   - Restart Nginx:
```
sudo systemctl restart nginx.
```

5. Configure Firewall:
   - Allow ports 80 and 443:
```
sudo ufw allow 80 && sudo ufw allow 443
```
   - Enable firewall:
```
sudo ufw enable
```

6. Access the Application:
   - Open your browser and navigate to http://<server-ip>
   - The Flask app should display: "Hello from my Linux server! Ready for Canada!".

## Future Plans
- Automate setup with Ansible.
- Containerize the application with Docker.
- Add monitoring with Prometheus and Grafana.

## Notes
- This project is a starting point for learning Linux administration, web server configuration, and basic DevOps skills.

//github.com/yourusername/journey-02-dockerizing-flask)
- [Journey 02: Dockerizing Flask](https://github.com/yourusername/journey-02-dockerizing-flask)
- [Journey 03: PostgreSQL Setup](https://github.com/yourusername/journey-03-postgresql-setup)
- [Journey 04: Monitoring with Prometheus](https://github.com/yourusername/journey-04-monitoring-prometheus)
