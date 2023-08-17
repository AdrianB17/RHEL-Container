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

# ---------Managing Writable Data on Persistent Volumes---------
<p align="left">podman search --help</p>
<p align="left">podman search --limit 1 mysql</p>
<p align="left">podman pull openshift3/mysql-55-rhel7 </p>
<p align="left">podman inspect registry.access.redhat.com/openshift3/</p>
<p align="left">podman pull registry.access.redhat.com/openshift3/mysql-apb </p>
<p align="left">sudo firewall-cmd --add-port 33069/tcp</p>
<p align="left">sudo firewall-cmd --add-port 44749/tcp</p>



