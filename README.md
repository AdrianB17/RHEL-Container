# RHEL-Container

# ---------Installing and enabling the web console---------
<p align="left">sudo dnf install cockpit</p>
<p align="left">systemctl enable --now cockpit.socket</p>

# ---------Podman Comandoss---------
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
<p align="left">podman search httpd</p>
<p align="left">podman search httpd</p>
<p align="left">podman search httpd</p>
<p align="left">podman search httpd</p>



