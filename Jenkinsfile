 node{
    stage('installing apache'){
     sh """
     echo "installing apache2"
     sudo apt update
     sudo apt install apache2 -y
     echo "instalation is completed"
     ls -la
     pwd
     """
    }
    stage('deploy application'){
     sh """
     cd /var/www/html
     ls
     pwd
     sudo rm -rf html5-simple-personal-website
     sudo git clone https://github.com/website-template/html5-simple-personal-website.git
     ls 
     pwd
     """        
    }
    stage('ansible deployment'){
     sh """
     ansible-playbook -i ./inventory.txt ansible_jenkins.yml -v
     """        
    }
 }             
    
   