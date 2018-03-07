# LetsEncrypt CentOS 7

*   Step 1: Install Apache

    First, clean-up yum:

    `sudo yum clean all`

    As a matter of best practice we’ll update our packages:

    `sudo yum -y update`

    Installing Apache is as simple as running just one command:

    `sudo yum -y install httpd`

*   Step 2: (If Using Firewall)Allow Apache Through the Firewall
    Allow the default HTTP and HTTPS port, ports 80 and 443, through firewalld:

    `sudo firewall-cmd --permanent --add-port=80/tcp`

    `sudo firewall-cmd --permanent --add-port=443/tcp`

    And reload the firewall:

    `sudo firewall-cmd --reload`

*   Step 3: Configure Apache to Start on Boot
    And then start Apache:

    `sudo systemctl start httpd   [On RHEL/CentOS 7]`
    -or-
    `service httpd start     [On RHEL/CentOS 6]`

    Be sure that Apache starts at boot:

    `sudo systemctl enable httpd [On RHEL/CentOS 7]`
    -or-
    `chkconfig httpd on         [On RHEL/CentOS 6]`
