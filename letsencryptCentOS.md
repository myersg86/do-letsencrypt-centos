# LetsEncrypt Setup - CentOS 6/7

*   ## Step 1: Install Apache Web Server

1.  If not already installed, httpd daemon can be installed by issuing the below command:

`yum install httpd`

2.  In order for Let’s encrypt software to work with Apache, assure that the SSL/TLS module is installed by issuing the command below:

`yum -y install mod_ssl`

Setup /etc/httpd/conf.d/ssl.conf

`vi /etc/httpd/conf.d/ssl.conf`

These Lines:
>`# General setup for the virtual host, inherited from global configuration`
>
>`#DocumentRoot "/var/www/html"`
>
>`#ServerName www.example.com:443`

3.  Finally, start Apache server with the following command:

`systemctl start httpd.service          [On RHEL/CentOS 7]`

`service httpd start                    [On RHEL/CentOS 6]`

*   ## Step 2: Install Let’s Encrypt SSL Certificate

### Method #1: Wget Method (for CentOS 6)

*   Since it doesn't seem like your operating system has a packaged version of Certbot, you should use our certbot-auto script to get a copy:

`wget https://dl.eff.org/certbot-auto`

`chmod a+x certbot-auto`

### Package Method (for CentOS 7)

Certbot is packaged in EPEL (Extra Packages for Enterprise Linux).
4. To use Certbot, you must first enable the EPEL repository.

`yum -y install epel-release`

5.  After doing this, you can install Certbot by running:

`yum -y install python-certbot-apache`

### Git Method:

4.  The simplest method of installing Let’s Encrypt client is by cloning github repository in your filesystem. To install git on your system you must enable Epel repositories with the following command.

`yum -y install epel-release`
5. Once Epel repos are added in your system, go ahead and install git client by running the command below:

`yum -y install git`
6. Now , once you have installed all the required dependencies in order to deal with Let’s Encrypt, go to  /usr/local/ directory and start pulling the Let’s Encrypt client form its official github repository with the following command:

`cd /usr/local/`

`git clone https://github.com/letsencrypt/letsencrypt`

*   ## Step 3: Obtain a Free Let’s Encrypt SSL Certificate for Apache
    The process of obtaining a free Let’s Encrypt Certificate for Apache is automated for CentOS/RHEL thanks to the apache plugin.

**If using method #1(CentOS 6 ONLY - *NOT* for Git Method):**

>Run:
>
> `./path/to/certbot-auto --apache -d your_domain.tld `

**If using method #2 (CentOS 7 ONLY - *NOT* for Git Method):**

>Run:
>
> `./path/to/certbot --apache -d your_domain.tld `

**If using method Git Method:**

>Let’s run Let’s Encrypt script command in order to obtain a SSL Certificate. Go to Let’s Encrypt installation directory from `/usr/local/letsencrypt` and run the `letsencrypt-auto` command by providing  `--apache option` and the `-d` flag for every subdomain you need a certificate.
>
> `cd /usr/local/letsencrypt`
>
> `./letsencrypt-auto --apache -d your_domain.tld `

### Create Lets Encrypt SSL Certificate for Apache

8.  Supply the email address that will be used by Let’s Encrypt to recover your lost key or for urgent notices and press Enter to continue.

9.  Agree the terms of the license by hitting Enter key.

10. On CentOS/RHEL, by default, Apache server does not use the concept of separating directories for enabled hosts from available (inactive) hosts as Debian based distribution do.

Also, virtual hosting is disabled by default. The Apache statement which specifies the name of the server (ServerName) it’s not present on SSL configuration file.

To activate this directive, Let’s Encrypt will prompt you to select a virtual host. Because it does not find any Vhost available, select the ssl.conf file to be automatically modified by Let’s Encrypt client and press Enter to continue.

Active VirtualHost Directive and Select Mod_SSL

11. Next, choose the method for HTTP requests and press Enter to move forward.


12. Finally, if everything went smooth, a congratulation message should be displayed on the screen. Press Enter to release the prompt.

Lets Encrypt Enabled on Domain

That’s it! You have successfully issued a SSL/TLS certificate for your domain. Now you can start browsing your website using HTTPS protocol.

## Automating renewal

Certbot can be configured to renew your certificates automatically before they expire. Since Let's Encrypt certificates last for 90 days, it's highly advisable to take advantage of this feature. You can test automatic renewal for your certificates by running this command:

`./path/to/certbot-auto renew --dry-run         [On RHEL/CentOS 6]`

`./path/to/certbot renew --dry-run              [On RHEL/CentOS 7]`

`./path/to/letsencrypt-auto renew --dry-run     [Using Git Method]`

If that appears to be working correctly, you can arrange for automatic renewal by adding a cron or systemd job which runs the following:

`./path/to/certbot-auto renew     [On RHEL/CentOS 6]`

`./path/to/certbot renew          [On RHEL/CentOS 7]`

`./path/to/letsencrypt-auto renew [Using Git Method]`

To learn more about how to use Certbot read our documentation. - <https://certbot.eff.org/about>

More detailed information and options about renewal can be found in the full documentation. - <https://certbot.eff.org/docs/using.html#renewal>
