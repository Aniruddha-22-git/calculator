pipeline{
  agent{
    label('built-in')
  }
  stages{
    stage('game'){
steps {
 sh "yum install httpd -y "
  sh "service httpd start"
  sh "git clone https://github.com/Aniruddha-22-git/calculator.git /mnt "
  sh "cp -r /mnt/calculator/calculator.html /var/www/html"
  sh "chmod -R 777 /var/www/html/calculator.html "
  
 
}      
    }
  }
}
