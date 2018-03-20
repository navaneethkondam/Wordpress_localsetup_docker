# Wordpress_localsetup_docker

This repo will trigger four containers ( NGINX, Wordpress, MYSQL and phpmyadmin) which can be managed with docker-compose.
Worked with docker-compose volumes to map containers data to local folders to access and modify nginx and wordpress files.
  
  Verify whether docker and docker-compose are installed properly with below commands.(If not insatll docker)
       
       docker info
       docker-compose -version

1. Command to make containers up and running
 
               docker-compose up -d  
    
2. Access wordpress  at 
   
               0.0.0.0:80

3. Need to install wordpress by giving details such as site title, user name and email id (can modify later).
 
   While installing if you get 500 server error as below:
      
               0.0.0.0/wp-admin/install.php?step=2
               500 server error (it is pointing to wrong url while insatlling but installation is done)
    
    Chcek it by changing url:
          
               0.0.0.0/wp-admin/install.php
           
4. Add below lines in wordpress/wp-config.php file.

               define('WP_SITEURL', 'http://localhost/');
               
               define('WP_HOME','http://localhost/wordpress.com/');  
                       (OR)
               Log in to wp-admin console and in settings change site address to http://localhost/ and home address to 
               http://localhost/wordpress.com/
               
5. Access wordpress at 

               http://localhost/wordpress.com/
               
To check ports on which containers are running

                docker ps -a

For stopping docker containers:
          
                docker-compose down               
               