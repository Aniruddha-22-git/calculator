pipeline{
  agent{
    label "built-in"
    customWorkspace "/mnt/hello"
  }
  stages{
    stage('server'){
steps {
  sh "cd /mnt/hello"
  //sh "git clone https://github.com/Aniruddha-22-git/calculator.git "
  sh "apt install apache2 -y "
  sh "systemctl  start apache2"
  //sh "cd /mnt"
  //sh "mkdir calci"
  //sh "git clone https://github.com/Aniruddha-22-git/calculator.git /mnt/calci/"
  sh "cp -r calculator.html /var/www/html"
  sh "chmod -R 777 /var/www/html/calculator.html "
  
 
}      
    }
  }
}
