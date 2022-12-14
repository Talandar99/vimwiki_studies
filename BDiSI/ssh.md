# Using SSH via terminal

### wiki pages
- https://wiki.archlinux.org/title/OpenSSH
- https://wiki.archlinux.org/title/SCP_and_SFTP

### why?
- Windows10,Windows11 and all linux distros have ssh command built in. 
- It's easier to just open terminal and type than download GUI ssh client

### how to connect 
- default port
`` ssh user@server_address ``
- custom port
`` ssh -p port user@server_address ``

## SCP
- in general ``scp <source> <destination>``

- how to send a file
`` scp remote_user@remote_host:/path/to/remote/file /path/to/local/file ``

- how to download file via ssh
`` scp /path/to/local/file remote_user@remote_host:/path/to/remote/file ``


## How to login with SSH password
- kenerate key ``ssh-keygen -b 521 -t ecdsa``
  - we can specify ssh password, or not. 
  - If ssh don't have password it will log in automaticly
- ``cd`` into .ssh directory
- copy to remote server `` ssh-copy-id -i id_ecdsa login@address ``
- now we can login using ``ssh 'login@address'``


## Tunneling
- we can create tunnel to maintain connection with server using ``-L`` flag:
- L local_socket:remote_socket
  - example `` ssh -L local_socket:remote_socket login@address``
- L local_socket:host:hostport
  - example `` ssh -L local_socket:host:hostport login@address``
- example from studies 
``ssh -L 5432:localhost:5432 s99999@example.pl``



