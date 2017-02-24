# Workshop Server

catatan-catatan untuk workshop mastering server.


### Setup virtual host untuk banyak domain

1. make directory document root for your domain

  ```
  sudo mkdir /var/www/example.test/public
  sudo mkdir /var/www/ardin.test/public
  ```

2. change ownership directory to regular user, or you can skip this step.

 ```
 sudo chown -R $USER:$USER /var/www/ardin.test/public
 ```

3. then, make demo files in ardin.tes/public/index.html

4. make virtual host, copy conf from default to your own conf sites

  ```
  sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/ardin.test.conf
  ```

5. change `ServerName` and `DocumentRoot` in file ardin.test.conf.
  ```
  ServerName ardin.test
  DocumentRoot /var/www/ardin.test/public
  ```

6. enable your virtual host 
  ```
  sudo a2ensite ardin.test.conf
  ```
  
7. then restart apache2 `sudo service apache2 restart`.

8. in windows os you can add your host in C:system32/drivers/etc/host then add your host name server and ip. or /etc/hosts
 for unix.
## References

  https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-16-04

