# UnbreakTheBrique

Scripts to get Internet Cube back on rails with cron

Those scripts are the result of 4 years of Frankensteining the Internet Cube.
There are no evidences that it will work on your install, but it shall.

It helps for the most common problems met when the Internet Cube gets near to a long uptime.

## What is the Internet Cube?

The Internet Cube is a wonderful project. Its noble goal is to let anyone have a 100% free (software & hardware) server at home, with a VPN from a benevolent ISP mounted so you can have a Wi-Fi connexion that goes through OpenVPN for as many devices as you want. With this kind of setup, you can be protected from surveillance (at least from your ISP).

This server is also a marvellous way to self-host your services, with an "app store" of free and decentralized projects helping you to get anything you may want without having to get lost in hard install and setup processes.

Know more on https://internetcu.be or https://labriqueinter.net.

## What are these scripts for?

### check-services

This script has to be launched hourly.
It finds out if PHP or MySQL are down, and restart the services if so.
Just place it in `/etc/cron.hourly`.

### check-vpn

This script is kind of a check-up for connexion issus.
It is a daily script, and just restarts the VPN and hotspot services.
Its point is to prevent them to crash and your Cube from a disconnect. And, of course, it prevents any loss of hotspot connexion, which is the point of the Internet Cube.
You want this on to be in `/etc/cron.daily`.

## How to use all of this?

Just put the files in the proper folders and `chmod +x` both of them.
Also, for any reboot of the Cube, you may want to manually launch them (check-vpn first, then check-services) so anything should be running fine.
