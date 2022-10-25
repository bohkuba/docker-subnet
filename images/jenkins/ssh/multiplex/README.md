# Multiplexing SSH Over a Single TCP Connection

SSH multiplexing re-uses the same TCP connection for multiple SSH sessions. This removes some of the work necessary to establish a new session, possibly speeding things up. Limiting the number of connections may also be helpful for other reasons.

The ControlMaster should be set to “auto” in able to automatically allow multiplexing if possible. The ControlPath will establish the path to control socket. The first session will create this socket and subsequent sessions will be able to find it because it is labeled by username, host, and port.

Setting the ControlPersist option to 1 will allow the initial master connection to be backgrounded. The 1 specifies that the TCP connection should automatically terminate one second after the last SSH session is closed:

(c) [DigitalOcean: SSH Essentials](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys#multiplexing-ssh-over-a-single-tcp-connection)
