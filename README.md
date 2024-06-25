# FTP_Anonymous
# Anonymous FTP Configuration and Testing

## Setting Up Anonymous FTP

To set up our FTP lab, first install vsftpd:

```sh
apt install vsftpd

Each service installed on a Linux machine has a configuration file that can be used to modify the service's options and parameters. By default, anonymous login is disabled in vsftpd. To enable anonymous login, edit the configuration file /etc/vsftpd.conf:

sh

nano /etc/vsftpd.conf

Change anonymous_enabled=NO to anonymous_enabled=YES to enable anonymous login.

Next, create a directory in /var/ftp/ named pub, change
i wanna markdown file in github not a normal pargraph
ChatGPT
README for Configuring and Testing Anonymous FTP

markdown

# Anonymous FTP Configuration and Testing

## Setting Up Anonymous FTP

To set up our FTP lab, first install vsftpd:

```sh
apt install vsftpd

Each service installed on a Linux machine has a configuration file that can be used to modify the service's options and parameters. By default, anonymous login is disabled in vsftpd. To enable anonymous login, edit the configuration file /etc/vsftpd.conf:

sh

nano /etc/vsftpd.conf

Change anonymous_enabled=NO to anonymous_enabled=YES to enable anonymous login.

Next, create a directory in /var/ftp/ named pub, change its ownership, navigate to this directory, and create a file note.txt containing the message "Hello World!!":

sh

mkdir -p /var/ftp/pub
sudo chown nobody:nogroup /var/ftp/pub
cd /var/ftp/pub
echo "Hello World!!" > note.txt

Then, add specific configurations to make anonymous login functional:

plaintext

no_anon_password=YES
anon_root=/var/ftp/
hide_ids=YES

i said markdown !!!!!!!!!!!!!!!!!!!!!
ChatGPT
README.md for Configuring and Testing Anonymous FTP

markdown

# Anonymous FTP Configuration and Testing

## Setting Up Anonymous FTP

To set up our FTP lab, first install vsftpd:

```sh
apt install vsftpd

Each service installed on a Linux machine has a configuration file that can be used to modify the service's options and parameters. By default, anonymous login is disabled in vsftpd. To enable anonymous login, edit the configuration file /etc/vsftpd.conf:

sh

nano /etc/vsftpd.conf

Change anonymous_enabled=NO to anonymous_enabled=YES to enable anonymous login.

Next, create a directory in /var/ftp/ named pub, change its ownership, navigate to this directory, and create a file note.txt containing the message "Hello World!!":

sh

mkdir -p /var/ftp/pub
sudo chown nobody:nogroup /var/ftp/pub
cd /var/ftp/pub
echo "Hello World!!" > note.txt

Then, add specific configurations to make anonymous login functional:

plaintext

no_anon_password=YES
anon_root=/var/ftp/
hide_ids=YES
pasv_min_port=<min_port>
pasv_max_port=<max_port>

Restart the vsftpd service:

sh

service vsftpd restart

Testing Anonymous FTP via Kali Linux

To verify everything is working, use Nmap to scan the target:

sh

nmap -A <target IP>

Test the FTP connection:

sh

ftp <target IP>

Log in with anonymous and no password. List the contents with ls to see the /pub directory. Navigate to it and download note.txt:

sh

get note.txt

That's it! Your anonymous FTP server should now be configured and tested successfully.
