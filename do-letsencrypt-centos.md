# How To Set Up a Remote Desktop with X2Go on Ubuntu 16.04

### Introduction

For efficiency, security, and the ability to do everything from the command line, many servers don't use a graphical user interface (GUI). However, there are times when you'll want to run GUI applications on your remote servers, like when you're testing web sites in browsers or you're looking to set up a remotely accessible workstation with a full desktop environment (DE).

The typical solution to interacting with a graphical interface on a remote computer running Linux or other *nix variants is Virtual Network Computing (VNC). Unfortunately, VNC is notoriously sluggish, insecure by default, and requires a lot of manual configuration to get up and running.
x2go uses the nx library that was developed by NoMachine. All of the latency intensive parts of X forwarding was worked around by creating a nx proxy on each side of the network connection and sending compressed updates between the two proxies.

In contrast, X2Go provides several advantages:


In contrast, X2Go provides several advantages:
- Graphical Remote Desktop that is responsive and works well even over low bandwidth connections
- Instead of sending images from the remote machine to your computer like VNC, X2Go uses a modified version of the X (graphical) server and X11 protocol to minimize the amount of data exchanged between client and server. This gives you a near local-like desktop experience. The only requirement for this kind of performance is that the network distance between client and server isn't too large. When you ping the server from the client machine, the round-trip time should not exceed 100 milliseconds. Close to 50ms would be optimal, and 200ms would be acceptable but not great.
- X2Go works with your existing SSH daemon, encrypting all traffic between the client and the server while relying on the same well-tested and secure mechanism of authentication.
- X2Go doesn't require complex manual configuration. It knows how to set up the session and launch popular desktop environments like XFCE, LXDE, MATE, and others automatically.
- Unlike VNC, X2Go sets up the environment when you log in, so you don't need to leave an X server running all the time. Plus, your session continues running even after you disconnect, which means that when you reconnect you'll find everything as you left it, just like on a local desktop.
- X2Go supports multiple login sessions, desktops, and users logged in to their own separate environments.
- Instead of a whole desktop environment, you can launch single graphical applications in X2Go, saving your local machine's resources while taking advantage of a server's more powerful resources, even leaving tasks running remotely for days at a time.

Such a setup is useful when:

- You need this type of desktop environment but can't install a Linux-based operating system locally.
- You're going on a trip but can't take your computer with you.
- Your Internet service provider gives you very little bandwidth, but you need access to tens or hundreds of gigabytes of data.
- You need a separate machine to work on something for weeks or months at a time.
- You're working with a team, and everybody needs access to a single remote desktop.
- You need some combination of graphical desktop, high-speed Internet, reliable power source, and ability to scale resources up and down quickly.

Introductory paragraph about the topic that explains what this topic is about and why the reader should care; what problem does it solve?

In this guide, you will [configure/set up/build/deploy] [some thing]...

When you're finished, you'll be able to...

## Prerequisites

Before you begin this guide you'll need the following:

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
