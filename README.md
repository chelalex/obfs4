obfs4
=========

Install and configure OBFS4 ansible role<br>
Available for Ubuntu 22.04 LTS<br>

    obfs4
    ├── README.md
    ├── files
    │   └── torrc
    ├── tasks
    │   └── main.yml
    └── templates
        └── tor.list.j2

Requirements
------------

Previously you should get your own brigdes from Tor Project official site https://bridges.torproject.org/bridges?transport=obfs4 or via Telegram Bot @GetBridgesBot and add them at the end of ```/etc/tor/torrc``` file. A ```/etc/tor/torrc``` file example is given below:

    UseBridges 1
    ClientTransportPlugin obfs4 exec /usr/bin/obfs4proxy
    Bridge obfs4 a.b.c.d:xxxxx XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX cert=abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890abcdefgh iat-mode=0

Then you may use obfs4 ansible role.

Example Playbook
----------------

    - hosts: server
      roles:
         - obfs4
