---
title: Download and install
description: Installation in RP
layout: page
---

# Download application

The application comes in 3 flavors (**Default**, **Debug** and **Reload**) and packed in two formats
(**.zip** for windows users and **.tar.gz** for Linux users). If you don't know what to download, just use
the Default App in the zip package.

![three_flavors]({{ site.baseurl }}/img/three_flavors.png "three_flavors")

Download last release (beta):


<ul class="nav nav-tabs">
  <li class="active"><a data-toggle="tab" href="#zip"  > .zip    </a></li>
  <li>               <a data-toggle="tab" href="#targz"> .tar.gz </a></li>
</ul>

<div class="tab-content">
<div id="zip" class="tab-pane fade in active" markdown="1">

|  **Default**  |  [lock_in+pid-0.2.1-1-devbuild.zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild.zip)                |
|  **Debug**    |  [lock_in+pid-0.2.1-1-devbuild_DEBUG.zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_DEBUG.zip)    |
|  **Reload**   |  [lock_in+pid-0.2.1-1-devbuild_RELOAD.zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_RELOAD.zip)  |

</div>
<div id="targz" class="tab-pane fade" markdown="1">

|  **Default**  |  [lock_in+pid-0.2.1-1-devbuild.tar.gz]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild.tar.gz)                |
|  **Debug**    |  [lock_in+pid-0.2.1-1-devbuild_DEBUG.tar.gz]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_DEBUG.tar.gz)    |
|  **Reload**   |  [lock_in+pid-0.2.1-1-devbuild_RELOAD.tar.gz]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_RELOAD.tar.gz)  |

</div>
</div>



<a data-toggle="collapse" href="#OldReleases" aria-expanded="false" aria-controls="OldReleases">Older releases<span class="caret"></span></a>

<div id="OldReleases" class="collapse" markdown="1" style="padding: 10px; border: 1px solid gray; border-radius: 5px;">

- **lock-in+pid-0.1.1-3**:
  - lock-in+pid-0.1.1-3-devbuild [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild.tar.gz)]
  - lock-in+pid-0.1.1-3-devbuild_DEBUG [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_DEBUG.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_DEBUG.tar.gz)]
  - lock-in+pid-0.1.1-3-devbuild_RELOAD [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_RELOAD.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.1-3-devbuild_RELOAD.tar.gz)]
- **lock-in+pid-0.1.0-48**:
  - lock-in+pid-0.1.0-48-devbuild [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-48-devbuild.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-48-devbuild.tar.gz)]
  - lock-in+pid-0.1.0-48-devbuild_DEBUG [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-48-devbuild_DEBUG.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-48-devbuild_DEBUG.tar.gz)]
  - lock-in+pid-0.1.0-48-devbuild_RELOAD [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-48-devbuild_RELOAD.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-48-devbuild_RELOAD.tar.gz)]
- **lock-in+pid-0.1.0-25**:
  - lock-in+pid-0.1.0-25-devbuild [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-25-devbuild.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-25-devbuild.tar.gz)]
  - lock-in+pid-0.1.0-25-devbuild_DEBUG [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-25-devbuild_DEBUG.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-25-devbuild_DEBUG.tar.gz)]
- **lock-in+pid-0.1.0-15**:
  - lock-in+pid-0.1.0-15-devbuild [[zip]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-15-devbuild.zip),[tar]({{ site.baseurl }}/releases/lock-in+pid-0.1.0-15-devbuild.tar.gz)]

</div>

## The difference between flavors

The application itself is the **Default** flavor.
The **Debug** flavor is just the same application but with a more debugging
info printed all the time in the internal Red Pitaya log files (`/var/log/redpitaya_nginx/*.log`) and is provided
for testing and development purposes.
The **Reload flavor** has only one difference with the Default: it doesn't loads the FPGA circuit on App loading
nor reset any memory reg value. This flavor is useful if you already made an FPGA configuration
through the Default App, closed the browser and then you want to get control again of that FPGA without resetting
all the register values.


# Install App in RedPitaya

First, you need an already running RedPitaya environment. If you don't know
how to prepare the device SDCard, just follow the
[RedPitaya help page instructions](http://redpitaya.readthedocs.io/en/latest/quickStart/SDcard/SDcard.html)

To install the web application you need to upload the `rp_lock-in_pid` folder
to the RedPitaya device in the path `/opt/redpitaya/www/apps/`. You can do that with several SSH clients.


<a data-toggle="collapse" href="#How_to_find_RedPitaya" aria-expanded="false" aria-controls="How_to_find_RedPitaya"> How to find your RedPitaya <span class="caret"></span></a>

<div id="How_to_find_RedPitaya" class="collapse" markdown="1" style="padding: 10px; border: 1px solid gray; border-radius: 5px;">
If the device is connected to an standard dynamic-ip network (any standard router for internet access, any public network or network with DHCP) you can access de RedPitaya device using this name:

`rp-XXXXXX.local`

where XXXXXX are the last 6 digits of the device MAC address. The MAC address can be find in the Ethernet port of the
device:

![Red Pitaya MAC]({{ site.baseurl }}/img/rp_MAC.png "Red Pitaya MAC")

In this case, would be: `rp-F113D5.local`. This is an automatic name assignation made through [ZeroConf](https://en.wikipedia.org/wiki/Zero-configuration_networking) system.

After that, you can access several RedPitaya services using this address, for example:

 - **Web Applications:** In your web browser...

 `http://rp-XXXXXX.local/`

 - **Remote login:** From a console application (linux):

 ```bash
 ssh rp-XXXXXX.local -l root
 ```

 - **Find IP address:** From console:
 ```bash
 ping rp-XXXXXX.local
 ```
For more information or other options, refer to
[RedPitaya connect help](http://redpitaya.readthedocs.io/en/latest/quickStart/connect/connect.html)

</div>


## For Windows

Use [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) to
get shell access to the RedPitaya Operative System (Linux) and run the command `rw` (default user: root, default pass: root):

```bash
root@rp-XXXXXX:~$ rw
```

Then use [WinSCP](https://winscp.net/) to upload the `lock-in+pid` folder to
 `/opt/redpitaya/www/apps/`

If you want to use the remote control tools you need to copy the `/resources/rp_cmds/py/*.py`
content to `/root/py` in the RedPitaya device.

### Automatic login for PuTTY

<div class="alert alert-warning" role="alert">
  <strong>Under construction</strong> TO BE COMPLETED
</div>

For the while, you can follow this site instructions (using your RP address `rp-XXXXXX.local` instead of the ip address of that example, 192.168.0.100)

[ssh_key_based_logins_putty](https://www.howtoforge.com/ssh_key_based_logins_putty)

The key generated in that example can also be used in [WinSCP](https://winscp.net/eng/docs/ui_login_authentication)

## For linux

To enable `rw`, in a Terminal console run:

```bash
ssh rp-XXXXXX.local -l root  "PATH_REDPITAYA=/opt/redpitaya /boot/sbin/rw"
```

where `rp-XXXXXX.local` is the device address (copy & paste if you want).

Then upload the `rp_lock-in_pid` folder.

### With GUI

You can use any SSH file transfer client, like [FileZilla](https://filezilla-project.org/) of gftp.

### With console
Using the `scp` command (comes with linux) from console:

```bash
scp -r rp_lock-in_pid  root@rp-XXXXXX.local:/opt/redpitaya/www/apps/rp_lock-in_pid
scp -r rp_lock-in_pid/resources/rp_cmds/*  root@rp-XXXXXX.local:/root/
```

### Script for automatic upload
The installation package includes a bash script to automatically upload
the application to the RedPitaya device.

Run from the uncompressed folder path:

```bash
bash upload_app.sh rp-XXXXXX.local
```

### Configure automatic login into RP

It's useful to automate the login procedure to get into RedPitaya console without
typing user and password each time. To do this you need to have an SSH key. If you
don't have one, create it with this command in localhost console:

```bash
ssh-keygen
```
If it ask you for Pass Phrase, just hit enter key

Then upload the public key to RP:

```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub rp-XXXXXX.local
```

Now you should be able to login without a password:

```bash
ssh rp-XXXXXX.local -l root
```
