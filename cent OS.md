Failed to download metadata for repo 'appstream': Cannot prepare internal mirrorlist: No URLs in mirrorlist
```

 sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
 
sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*

```
python
```
yum install openssl-devel bzip2-devel libffi-devel
yum groupinstall "Development Tools"
wget https://www.python.org/ftp/python/3.11.0/Python-3.11.0a4.tgz
tar -xzf Python-3.11.0a4.tgz
cd Python-3.11.0a4
./configure --enable-optimizations
make altinstall
python3.10 -V

ln -fs /usr/local/bin/python3.11 /usr/bin/python3
python3 -V
python3 -m pip install --upgrade pip
python3 -m pip install ansible
```