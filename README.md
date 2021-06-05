# sftp_new_files_to_remote_cron
Sftp all files in a folder to a remote server using sftp, both password and key file.

Readme#######


 Using u/Password--- install expect, create sample files, Use password to upload NEWER files in source folder---

yum -y install expect
touch ./source/file{1..3}
./sshsync-using-pw.sh username localhost /<abspath>/SFTP_new_files/source /<abspath>/SFTP_new_files/destination ThePassword




 Using u/key--- create sample files, Using pre placed key file to upload NEWER files in source folder---

touch ./source/file{1..3}
./sshsync.sh username localhost /<abspath>/SFTP_new_files/source /<abspath>/SFTP_new_files/destination



crontab entry
28 18 * * 1-5 /<path>/sshsync.sh >> /<path>/filesync.log 2>&1


Reference:
https://www.golinuxcloud.com/automate-sftp-shell-script-with-password-unix/

Changelog:
Made changes to handle key fingerprint question yes/no and then supply password using expect. (sshsync-using-pw.sh)
