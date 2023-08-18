# RHEL-Container

# ---------Installing and enabling the web console---------
<p align="left">sudo dnf install cockpit</p>
<p align="left">systemctl enable --now cockpit.socket</p>

# ---------Deploy Container with Podman---------
<p align="left">podman image ls</p>
<p align="left">podman search httpd</p>
<p align="left"> sed -E '/^(#|$)/d' /etc/containers/registries.conf </p>
<p align="left">podman ps -a</p>
<p align="left">podman run -d --name httpd registry.access.redhat.com/rhscl/httpd-24-rhel7</p>
<p align="left">podman stop httpd</p>
<p align="left">podman rm httpd</p>
<p align="left">podman inspect registry.access.redhat.com/rhscl/httpd-24-rhel7</p>
<p align="left">podman inspect registry.access.redhat.com/rhscl/httpd-24-rhel7 | grep expose </p>
<p align="left">podman run -d --name=httpd -p 8080:8080 registry.access.redhat.com/rhscl/httpd-24-rhel7</p>
<p align="left">curl localhost:8080</p>

# ---------Podman Comandoss---------
<p align="left">podman ps</p>
<p align="left">podman ps -a</p>
<p align="left">podman restart -l</p>
<p align="left">podman stop</p>
<p align="left">podman rm -l</p>
<p align="left">podman rm httpd</p>
<p align="left">podman rm -f -l</p>
<p align="left">podman image ls</p>
<p align="left">podman image rm -a</p>

# ---------Publishing All exposed ports---------
<p align="left">podman pull registry.access.redhat.com/rhscl/httpd-24-rhel7</p>
<p align="left">podman ps -a</p>
<p align="left">podman run --name=httpd -d --publish-all registry.access.redhat.com/rhscl/httpd-24-rhel7</p>
<p align="left">podman port -l</p>
<p align="left">sudo firewall-cmd --add-port 33069/tcp</p>
<p align="left">sudo firewall-cmd --add-port 44749/tcp</p>

# ---------Deploy MySQL---------
<p align="left">podman search --help</p>
<p align="left">podman search mysql</p>
<p align="left">podman pull registry.access.redhat.com/rhscl/mysql-57-rhel7 </p>
<p align="left">podman inspect rhscl/mysql-57-rhel7 | grep usage</p>

<p align="left">podman run --name=sql -d -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -e MYSQL_DATABASE=db -p 3306:3306 rhscl/mysql-57-rhel7</p>
<p align="left">podman ps </p>
<p align="left">podman port -l</p>
<p align="left">sudo firewall-cmd --list-all</p>
<p align="left">sudo firewall-cmd --add-port 3306/tcp</p>

# ----Connecting MySQL--------
<p align="left">sudo yum install -y mysql</p>
<p align="left">mysql -uuser -p -h192.168.18.214</p>
<p align="left">SELECT DATABASE();</p>
<p align="left">USE db;</p>
<p align="left">SELECT DATABASE();</p>
<p align="left">quit</p>


# ---- Persistent Volume--------
<p align="left">podman ps</p>
<p align="left">podman exec -it sql /bin/bash</p>

<p align="left">$ id</p>
<p align="left">$ ps -p1 -f</p>
<p align="left">$ exit</p>

<p align="left">mkdir mysql</p>
<p align="left">ls -ld mysql</p>
<p align="left">chcon -t container_file_t mysql/</p>
<p align="left">podman unshare id</p>
<p align="left">podman unshare chown 27 mysql</p>
<p align="left">ls -ld mysql</p>
<p align="left">grep ansible /etc/subuid</p>
<p align="left">ls -ld mysql</p>


# ---- Creating Data in MySQL--------
<p align="left">podman rm -f sql</p>
<p align="left">podman run --name=sql -v /home/ansible/mysql -d -e MYSQL_USER=user -e MYSQL_PASSWORD=pass -e MYSQL_DATABASE=db -p 3306:3306 rhscl/mysql-57-rhel7</p>
<p align="left">podman exec -it sql /bin/bash</p>

<p align="left">$ id</p>
<p align="left">$ ps -p1 -f</p>
<p align="left">$ exit</p>







