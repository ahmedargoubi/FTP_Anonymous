# Setting Up and Testing Anonymous FTP 

This repository documents the configuration and testing of an anonymous FTP server using vsftpd on Ubuntu. 

## Setup (Ubuntu machine)

1. Install vsftpd:

    ```bash
    apt install vsftpd
    ```

2. Navigate to the vsftpd configuration file:

    ```bash
    nano /etc/vsftpd.conf
    ```

3. Modify `anonymous_enabled` to allow anonymous access:

    ```plaintext
    anonymous_enabled=YES
    ```

## Configuration

Create a shared directory `/var/ftp/pub` and adjust permissions:

```bash
sudo mkdir -p /var/ftp/pub
sudo chown nobody:nogroup /var/ftp/pub
cd /var/ftp/pub
echo "Hello Friend" > file.txt
```

## Update vsftpd configuration for anonymous FTP
 
 ```plaintext
no_anon_password=YES
anon_root=/var/ftp/
hide_ids=YES
pasv_min_port=<min_port>
pasv_max_port=<max_port>
```
Restart vsftpd for changes to take effect:

```bash
service vsftpd restart
```

## Testing (Kali machine)

Use Nmap to scan for open ports:

```bash
nmap -p 21 192.168.23.150
```
OR

```bash
nmap -A 192.168.23.150
```
Connect to the FTP server anonymously using Kali Linux:

```bash
ftp 192.168.23.150
```

List contents and download files:

```bash
ls
get note.txt
```

That's it! Your anonymous FTP server should now be configured and tested successfully.




