## Detect package by system

This is a repository (script bash  v1.0) to get the system and install/remove any package detecting the system or dib.

## Features
List of features then
* [x] Will do the installation package by package, if a package doesn't exist getsys will continue installing yet.
* [x] Compatible with ArchLinux, Debian, Fedora, openSUSE, suseLinux and derivatives.
* [x] You can make a array with packages for all (will detect the os) or a system  specific.
* [x] You can add parameters to make a custom installation (update packages, upgrade, sudo, etc).
* [x] 1 script in bash: the 99% of S.Os are using bash by default.
* [x] You can use this code without download.
* [x] Semi-graphical installation.

## ¿Why use this?

If you have a script and the script require some packages maybe this will be your magic script!

## Getting getsys script
You need download getsys by wget with:
```bash
wget https://raw.githubusercontent.com/CodeSh/getsys/master/getsys
```

Or install the script in your system:
```bash
git clone https://github.com/CodeSh/getsys
cd getsys
sudo make install
```

Or using getsys without download (something like online :P):
```bash
# IMPORTANT: this in the last line of the script
source <(curl -s https://raw.githubusercontent.com/CodeSh/getsys/master/getsys)
```

Examples:

```bash
sudo=true # This isn't required if you dont need sudo privileges
action=install

packages_debian=(
	"curl"
	"firefox"
	)
	
source getsys
```

If you have the script installed:
```bash
sudo=true # This isn't required if you dont need sudo privileges
action=install

packages_debian=(
	"curl"
	"firefox"
	)
	
getsys
```

## ¿Why including getsys?
Because that is the "library" to detect the system and install the package.

### action

Get the action to do it

-

Type : *install*

	the lib will get the system and will install the list of packages.
	
Example:

```bash
action=install
```
-
---
Type : *remove*

	the lib will get the system and will remove the list of packages.
	
Example:

```bash
action=remove
```
-
---
Type: *end*
	set the action to null
	
Exaple:

```bash
action=end
```
------------

### list of packages

Array : *packages_debian*

	array with a list of packages to install/remove in debian or others derivatives.
	
Example:
```bash
packages_debian=(
	"package1"
	"package2"
	"package3"
	"andmore"
	)
```

-
---

Array : *packages_fedora*

	array with a list of packages to install/remove in fedora or others derivatives.

Example:
```bash
packages_fedora=(
	"package1"
	"package2"
	"package3"
	"andmore"
	)
```

-
---

Array : *packages_suselinux*

	array with a list of packages to install/remove in suselinux or others derivatives.

Example:
```bash
packages_suselinux=(
	"package1"
	"package2"
	"package3"
	"andmore"
	)
```

-
---

Array : *packages_archlinux*

	array with a list of packages to install/remove in archlinux or others derivatives.

Example:
```bash
packages_archlinux=(
	"package1"
	"package2"
	"package3"
	"andmore"
	)
```	

Array : *packages_all*

	array with a list of packages to install/remove in archlinux : debian : suselinux : fedora and derivatives.

Example:
```bash
packages_all=(
	"package1"
	"package2"
	"package3"
	"anymore"
	)
```	

## Others methods
I've added some functions to any script, helping at `autoremove`, `update` and `upgrade`

All systems:
```bash
update_packages=true
upgrade_packages=true
autoremove_packages=true
```

This needs to be put in the first lines before than `source getsys` or `getsys` and the list of packages.

-

Or you can select a system default and add a funcion adding the next code after than `source getsys` or `getsys`

Debian/Ubuntu or derivatives:
```bash
update_packages_debian
upgrade_packages_debian
autoremove_packages_debian
```
-

Fedora or derivatives:
```bash
update_packages_fedora
upgrade_packages_fedora
autoremove_packages_fedora
```
-

SuseLinux or derivatives:
```bash
update_packages_suselinux
upgrade_packages_suselinux
autoremove_packages_suselinux
```
-

Archlinux or derivatives:
```bash
update_packages_archlinux
upgrade_packages_archlinux
autoremove_packages_archlinux
```

-

Yeah. **This also will detect the system** :P

If you have the function `update_packages_archlinux` and the script will be run in ubuntu. The script will not do nothing!

You can contribute in this proyect! I will read all the pullrequests or i will add your your dib if you need that! Just you must run this command: `lsb_release -is` and send me the reply!
