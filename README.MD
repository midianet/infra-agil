#Exercícios Infra Agil AWS

Jenkins
    # install jdk
    1 apt update
    2  apt install openjdk-11-jdk
    3 java -version
    #add repo sources 
    5  curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
    8  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
    9  apt update
    # install Jenkins  
   10  apt install jenkins -y
    # habilitar serviço Jenkins
   11  systemctl status Jenkins
   12  systemctl enable --now jenkins
   # liberar porta (se rodando ufw)
   13  ufw allow 8080
    #instalar docker 
   14  apt install apt-transport-https curl gnupg-agent ca-certificates software-properties-common -y
   15  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   16  add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
   17  apt install docker-ce docker-ce-cli containerd.io -y
   18  docker ps
   #dar permissão a todos do socket do docker 
   20  chmod 777 /var/run/docker.sock
   # pegar a senha inicial do jenkins 
   24  cat /var/lib/jenkins/secrets/initialAdminPassword 74d4b9d6ca124ef9940c215276ef2842 
   # Caminho do java /usr/lib/jvm/java-11-openjdk-amd64
   #Instalar kubectl
   curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
   chmod +x kubectl
   mv kubectl /usr/local/bin/kubectl
   #Configurar o settings do maven 
   /var/lib/jenkins/.m2
