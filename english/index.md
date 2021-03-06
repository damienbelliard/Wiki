# OCS Inventory NG 2.x Documentation

To make it easier to read, the OCS Inventory NG documentation has been divided into 10 sections.

## Newbie documentation

* [OCS Inventory NG - Basics](01.Newbie-documentation/OCS-Inventory-NG-Basics.md)

## Basic documentation

* [Setting up a OCS Inventory server](02.Basic-documentation/Setting-up-a-OCS-Inventory-Server.md)
* [Setting up the UNIX agent on client computers](02.Basic-documentation/Setting-up-the-UNIX-agent-on-client-computers.md)
* [Setting up the Windows Agent 2.X on client computers](02.Basic-documentation/Setting-up-the-Windows-Agent-2.x-on-client-computers.md)
* [Setting up the MacOSX agent on client computers](02.Basic-documentation/Setting-up-the-MacOSX-agent-on-client-computers.md)
* [Setting up the Android Agent](02.Basic-documentation/Setting-up-the-Android-Agent.md)
* [Administration of OCS Inventory NG](02.Basic-documentation/Administration-of-OCS-Inventory-NG.md)
* [Deploying database server](02.Basic-documentation/Deploying-database-server.md)
* [Updating the server](02.Basic-documentation/Updating-the-server.md)

## Management console and its advanced features

* [Querying inventory results](03.Management-console-and-its-advanced-features/Querying-inventory-results.md)
* [Using computers groups](03.Management-console-and-its-advanced-features/Using-computers-groups.md)
* [Using the Plugins feature](03.Management-console-and-its-advanced-features/Using-the-Plugins-feature.md)
* [Using assets categorization](03.Management-console-and-its-advanced-features/Using-Assets-Categorization.md)
* [Using softwares categorization](03.Management-console-and-its-advanced-features/Using-Software-Categorization.md)
* [Managing users profiles of the web interface](03.Management-console-and-its-advanced-features/Managing-users-profiles-of-the-web-interface.md)
* [Managing administrative data](03.Management-console-and-its-advanced-features/Managing-administrative-data.md)
* [Synchronization between OCS and LDAP](03.Management-console-and-its-advanced-features/Synchronization-between-OCS-and-LDAP.md)
* [Export a computer](03.Management-console-and-its-advanced-features/Export-a-computer.md)
* [Configure mail notification](03.Management-console-and-its-advanced-features/Configure-mail-notification.md)

## Deployment

* [Deploying packages or executing commands on client hosts](04.Deployment/Deploying-packages-or-executing-commands-on-client-hosts.md)

## Network Discovery with OCS Inventory NG

* [Using IP discovery feature](05.Network-Discovery-with-OCS-Inventory-NG/Using-IP-discovery-feature.md)
* [Using SNMP scan feature](05.Network-Discovery-with-OCS-Inventory-NG/Using-SNMP-scan-feature.md)

## OCS Tools

* [OCS Inventory NG Agent Deployement Tool](06.OCS-Tools/OCS-Inventory-NG-Agent-Deployement-Tool.md)
* [OCS Packager](06.OCS-Tools/OCS-Packager.md)
* [OCS Packager for MacOSX](06.OCS-Tools/OCS-Packager-for-MacOSX.md)
* [OCS Packager for Unix](06.OCS-Tools/OCS-Packager-for-UNIX.md)
* [Ansible role for Unix Packager](06.OCS-Tools/OCS-Ansible-Role-for-Unix-Packager.md)

## Multi-site network architecture

* [Using local proxy cache to deploy](07.Multi-site-network-architecture/Using-local-proxy-cache-to-deploy.md)
* [Synchronisation between OCS server master/slaves](07.Multi-site-network-architecture/Synchronisation-between-OCS-server-master-slaves.md)

## Extras

* [Secure your OCS Inventory NG Server](08.Extras/Secure-your-OCS-Inventory-NG-Server.md)
* [Management server tuning](08.Extras/Management-server-tuning.md)
* [Enable Powershell Support on Windows Agent](08.Extras/Enable-Powershell-Support-on-Windows-Agent.md)
* [Backup/restore of OCS Inventory NG database ](08.Extras/Backup-restore-of-OCS-Inventory-NG-database.md)
* [Common errors](08.Extras/Common-errors.md)

## REST API
* [Introduction](09.Rest-API/Introduction.md)
* [Configuration](09.Rest-API/Configuration.md)
* [Autentification](09.Rest-API/Authentification.md)
* [GET Routes](09.Rest-API/GET-Routes.md)
* [POST Routes](09.Rest-API/POST-Routes.md)
* [DELETE Routes](09.Rest-API/DELETE-Routes.md)
* [PUT Routes](09.Rest-API/PUT-Routes.md)

## Developers

* [XML-Format](10.Developers/XML-Format.md)
* [HOWTO create theme](10.Developers/HOWTO-create-theme.md)
* [HOWTO package OCS Unix server releases](10.Developers/HOWTO-package-OCS-Unix-server-releases.md)
* [HOWTO package OCS Unix agent releases](10.Developers/HOWTO-package-OCS-Unix-agent-releases.md)
* [HOWTO package OCS MacOSX agent releases](10.Developers/HOWTO-package-OCS-MacOSX-agent-releases.md)

# Contribution

If you think something is missing feel free to open an issue or fork it and document it by yourself. 
Same for mistakes in the documentation.

The Github repository below is directly linked to our documentation.
See [our GitHub repository](https://github.com/OCSInventory-NG/Wiki)

# FAQ


* Can I upgrade my server from version X to the last stable version ?

    **Solution**: Since we made a lot of changes from 2.0 to 2.4 in the database schema. We recommend you to not upgrade your OCS from 1.0 to 2.4 and newer directly. You may need to upgrade to 2.0 before. 

* After installing the server, I go to the graphical admin console (GUI) and it asks me to install the database ?

    **Solution**: The database is installed on the first access to the graphical admin console (GUI).

* What URL must I put in the agent to contact the server ?

    **Solution**: The URL must be in this form http://dns_or_ip/ocsinventory. It is recommended that you use DNS instead of IP.

* ocsinventory directory does not exist on my server

    **Solution**: ocsinventory is a virtual directory call by mod_perl in apache. ocsinventory directory must not exist.

* Error 500 :

    **Solution**: OCS engine can't comunicate with mysql server. Probably due to a wrong mysql account. You have to check z-ocsinventory-server.conf exactly theses few lines

        # Master Database settings
          # Replace localhost by hostname or ip of MySQL server for WRITE
          PerlSetEnv OCS_DB_HOST localhost
          # Replace 3306 by port where running MySQL server, generally 3306
          PerlSetEnv OCS_DB_PORT 3306
          # Name of database
          PerlSetEnv OCS_DB_NAME ocsweb
          PerlSetEnv OCS_DB_LOCAL ocsweb
          # User allowed to connect to database
          PerlSetEnv OCS_DB_USER ocs
          # Password for user
          PerlSetVar OCS_DB_PWD ocs

    Modify **OCS_DB_USER** and **OCS_DB_PWD** with your own account, restart apache, and finaly launch an inventory.

* Error 417 :

    **Solution** : insert ignore_expect_100 on into your squid.conf file and then run squid -k reconfigure.
