
Instalação do jenkins
https://phoenixnap.com/kb/install-jenkins-ubuntu


Criar ec2 t2-micro

Criar ip elastico
Associar ip elastico
Liberar no firewall a rede de saída e entrada

  Configurar ferramentas de Configuração

  Jdk  NOME: JDK11 
        JAVA_HOME: /usr/lib/jvm/java-11-openjdk-amd64
  Maven instalar ultima

Instalar docker
https://cloudcone.com/docs/article/how-to-install-docker-on-ubuntu-22-04-20-04/
sudo chmod 777 /var/run/docker.soc


Nexus
https://www.howtoforge.com/how-to-install-nexus-repository-manager-on-ubuntu-22-04/


https://download.sonatype.com/nexus/3/nexus-3.45.1-01-unix.tar.gz


Sonar
https://www.fosstechnix.com/how-to-install-sonarqube-on-ubuntu-22-04-lts/

7a2118a2ff9b18a4bff6f27fe51dcd2f41f19d8f


mvn sonar:sonar -Dsonar.projectKey=carros-api -Dsonar.host.url=http://44.211.102.32:9000 -Dsonar.login=7a2118a2ff9b18a4bff6f27fe51dcd2f41f19d8f



mvn sonar:sonar \
  -Dsonar.projectKey=carros-api \
  -Dsonar.host.url=http://44.211.102.32:9000 \
  -Dsonar.login=7a2118a2ff9b18a4bff6f27fe51dcd2f41f19d8f


/etc/sysctl.conf and set vm.max_map_count to 262144.




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
