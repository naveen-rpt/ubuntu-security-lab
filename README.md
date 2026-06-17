Here are the exact step-by-step details to run the project on your new Ubuntu system:

Step 1: Install the unrar utility
Ubuntu does not come with .rar support by default. Install it by running:
sudo apt update
sudo apt install -y unrar

Step 2: Extract the file
Use the x command to extract the files while keeping your folder structure intact (this is important so the folders like app and data are created correctly):
unrar x ubuntu-security-lab.rar

Step 3: Install Docker on the new Ubuntu system (if not already installed)
Open the terminal on your Ubuntu system and run these commands to install Docker and Docker Compose:
sudo apt update
sudo apt install -y docker.io docker-compose-v2
Ensure the Docker service is running:
sudo systemctl enable --now docker
Step 4: Download your project files to the Ubuntu system
You can download them in two ways:

Option A (If repository is public/private on GitHub):
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd ubuntu-security-lab

Option B (If you copied the folder manually): Just open your terminal, navigate (cd) into the folder you copied:
cd /path/to/copied/ubuntu-security-lab

Step 5: Run the project
Start the system in the background using Docker:
sudo docker compose up --build -d
(This will automatically download the required Ubuntu packages, install the Python requirements, start the FastAPI server, setup SSH access, and start the dashboard interface).

Step 4: Access the System
Web Dashboard:

If you are accessing it on the Ubuntu machine: Open browser and go to http://localhost:8000
If you are accessing it from another machine on the same network: Go to http://<ubuntu-ip-address>:8000
API Key (to login/authenticate): default-key-super-secret-12345
SSH Terminal Access:

Run the following command from any terminal to log in to the secure environment:
ssh root@<ubuntu-ip-address> -p 2222
Default Password: admin-secure-password-2026
