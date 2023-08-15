chrismurray.me.uk
==============

# install

## git instructions

```
sudo rm -rf chrismurray.me.uk /var/www/chrismurray-ssl
```

### git url

```
eval $(ssh-agent -s); ssh-add .ssh/github_rsa
git clone git@github.com:chris18890/chrismurray.me.uk.git
sudo cp -r chrismurray.me.uk/chrismurray/ /var/www/chrismurray-ssl; sudo chown www-data -R /var/www
```

# Setup - multiple domains/ssl sites

```
nano chrismurray.me.uk/chrismurray-ssl.conf
sudo cp chrismurray.me.uk/chrismurray-ssl.conf /etc/apache2/sites-available/chrismurray-ssl.conf; sudo a2ensite chrismurray-ssl; sudo service apache2 restart
sudo certbot --apache -d chrismurray.me.uk -d www.chrismurray.me.uk -d mta-sts.chrismurray.me.uk --agree-tos --renew-by-default --no-redirect
```
