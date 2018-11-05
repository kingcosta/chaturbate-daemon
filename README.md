# chaturbate-daemon
Automatically downloads chaturbate streams with youtube-dl

# Requirements
Python 3, python-requests, youtube-dl, GNU screen, pgrep

# Usage
1) Add the CB profiles you want to the array
2) Edit the systemd unit file accordingly, set your user and the directory you want to download to
3) sudo systemctl start cb-daemon
4) Can use use screen -list and screen -r to connect to running youtube-dl sessions

# Info
This repository contains a very simple python script and a systemd unit file.

It runs an infinite loop, iterates through array of profiles, checks if the profile is online, if it is, uses pgrep to check if we are already downloading the stream, if not, we download the stream through youtube-dl (detaching the process using GNU screen). Sleeps 30 seconds and then restarts infinite loop.
