#### Grep folder
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ps -ef | grep name-of-busy-dir
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Showed me the process and the PID (column two).
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo kill -15 pid-here
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Copy all from source to dest folder
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cp -a /source/. /dest/
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### So, for example, if the data was in / home / myuser / myfolder at the time from / home / myuser / the command was run.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
mv myfolder/* .
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### How to add RSA key to authorized_keys file?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cat <your_public_key_file> >> ~/.ssh/authorized_keys
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Getting the Size of a Directory
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo du -sh var/
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Output
85G	/var

#### Getting the Size of a Directory human readable
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
du --summarize --human-readable *
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### File search ( views.py -the file we are looking for )
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
find ./ -name “views.py”
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### File search ( all files with views in the name )
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
find ./ -name “views.*”
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### File search
 1. rin search in this and all nested directories
 1. i insensitive - large and small letters
 1. n numbers strings
 1. --include= in which files are we looking for
 1. dot means in the current directory
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
grep -rin –include=”*.py” “charfield” .
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Best file search ( It skips binaries and reads gitignore files and won't look in them )
`Highlighting results`
1. sudo apt update
1. sudo apt install snapd
1.  sudo snap install ripgrep --classic
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
rg -i “target” .
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### All startup
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
systemctl list-dependencies multi-user.target
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### See open ports
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo netstat -pnltu
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#### Copy some file from Server to local mashine
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
scp -i "insert key file here" -r "insert ec2 instance here" "your local directory"
scp -i amazon.pem -r ec2-user@ec2-##-##-##:/source/dir /destination/dir
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Copy some file from Local mashine to Server
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
scp -i /path/to/your/.pemkey -r /copy/from/path user@server:/copy/to/path
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#### Add the public key to the authorized_keys
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cat <your_public_key_file> >> ~/.ssh/authorized_keys
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
