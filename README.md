# Setting Up and Testing Anonymous FTP 

This repository documents the configuration and testing of an anonymous FTP server using vsftpd on Ubuntu. The setup includes enabling anonymous login, creating shared directories, and verifying server accessibility.

## Setup

1. Install vsftpd:

    ```bash
    sudo apt install vsftpd
    ```

2. Navigate to the vsftpd configuration file:

    ```bash
    sudo nano /etc/vsftpd.conf
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
echo "Hello World !!" > note.txt


##  Configuration

no_anon_password=YES
anon_root=/var/ftp/
hide_ids=YES
pasv_min_port=<min_port>
pasv_max_port=<max_port>


