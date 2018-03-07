# How To Set Up a Remote Desktop with X2Go on Ubuntu 16.04

### Introduction

In this guide, you will [configure/set up/build/deploy] [some thing]...

When you're finished, you'll be able to...

For efficiency, security, and the ability to do everything from the command line, many servers don't use a graphical user interface (GUI).
Sometimes you may want to run GUI applications on your remote servers, however.

The typical solution to interacting with a graphical interface on a remote computer running Linux  is Virtual Network Computing (VNC)., VNC connections are notioursly sluggish and can seem unresponsive on slow connections. Setting VNC servers up to allow encrypted remote access also requires a lot of configuration. X2Go was created as a solution to this problem.

X2Go uses the nx library originally developed by NoMachine. 
Latency intensive parts of X-forwarding have worked around by creating a proxy on each side of the network connection and sending compressed updates back and forth.

In contrast, X2Go provides several advantages:
- X2Go doesn't require complex manual configuration.
- Responsive Graphical Remote Desktop that works well even over low bandwidth connections
- X2Go works with your existing SSH daemon, encrypting all traffic between the client and the server while relying on the same well-tested and secure mechanism of authentication.
- X2Go supports multiple login sessions, desktops, and users logged in to their own separate environments.
- Instead of a whole desktop environment, you can launch single graphical applications in X2Go, saving your local machine's resources while taking advantage of a server's more powerful resources, even leaving tasks running remotely for days at a time.

Such a setup is useful when:

- You need this desktop environment but can't install a Linux-based operating system locally.
- You're going on a trip but can't take your computer with you.
- Your Internet service provider gives you very little bandwidth, but you need access to tens or hundreds of gigabytes of data.
- You need a separate machine to work on something for weeks or months at a time.
- You're working with a team, and everybody needs access to a single remote desktop.
- You need some combination of graphical desktop, high-speed Internet, reliable power source, and ability to scale resources up and down quickly.


## Prerequisites

Before you begin this guide you'll need the following:

- An Ubuntu 16.04 instance with at least 2GB of RAM. (2GB is minimal, 4GB is better to start with, and 8GB+ would be optimal). Choose a server location that is as close as possible to the area where you intend to connect from.
-   A CentOS 7 droplet with SSH access. For more information, visit [this tutorial](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-centos-7)
-   A LAMP stack, which you can install by following [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-centos-7)

## Step 1 — Install Let’s Encrypt SSL Certificate

Introduction to the step. What are we going to do and why are we doing it?

First....

Next...

Finally...

Now transition to the next step by telling the reader what's next.

## Step 2 — Title Case

Another introduction

Your content

Transition to the next step.

## Step 3 — Title Case

Another introduction

Your content

Transition to the next step.

## Conclusion

In this article you [configured/set up/built/deployed] [something]. Now you can....
