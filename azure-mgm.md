# k8s-env-prep Ubuntu (18)
Steps for k8s managment cosole preparation

# Managment console - Azure

# Docker


<b> Docker dep instalation</b>  
  
sudo apt-get install -y \  
    apt-transport-https \  
    ca-certificates \  
    curl \  
    software-properties-common  

<b>Download and add Docker PGP key</b>  
  
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  

<b>Verify the fingerprint</b>  
  
sudo apt-key fingerprint 0EBFCD88  

<b>Add the `stable` channel's Docker upstream repository</b> 
  
sudo add-apt-repository \  
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \  
   $(lsb_release -cs) \  
   stable"  
   
<b>Install Docker CE </b>  
  
sudo apt-get update -y  
sudo apt-get install -y docker-ce
 
<b>Allow your user without root</b>  
  
sudo usermod -aG docker $USER  

<b>Start and autostart docker</b>  
  
sudo systemctl start docker  
sudo systemctl enable dock  

# kubectl

<b> Download kubectl</b>  
  
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl  

<b>Make the kubectl binary executable</b>  
  
chmod +x ./kubectl  

<b>Move the binary in to your PATH</b>  
  
sudo mv ./kubectl /usr/local/bin/kubectl

# Command prompt
<b> Install kube-ps1</b>  
git clone https://github.com/jonmosco/kube-ps1.git .kube-ps1  
git clone https://github.com/JimiDeSoto/k8s-env-prep.git .pk8s-bash  
source ~/.pk8s-bash/pk8s.sh  

# azure cli
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash  


