# k8s-env-prep Ubuntu (18)
Steps for k8s managment cosole preparation

# Docker dep instalation

sudo apt-get install -y \  
    apt-transport-https \  
    ca-certificates \  
    curl \  
    software-properties-common  

# Download and add Docker PGP key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  

# Verify the fingerprint.
sudo apt-key fingerprint 0EBFCD88  

# Add the `stable` channel's Docker upstream repository
sudo add-apt-repository \  
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \  
   $(lsb_release -cs) \  
   stable"  
   
# Install Docker CE.
sudo apt-get update -y
sudo apt-get install -y docker-ce
 
# Allow your user to access the Docker CLI without needing root access.
sudo usermod -aG docker $USER  

#Start and autostart Docker  
sudo systemctl start docker  
sudo systemctl enable dock  
