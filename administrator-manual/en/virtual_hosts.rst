.. index:: virtual hosts
   single: HTTP

.. _virtual_hosts-section:

==============
Virtual hosts
==============

Virtual hosting allows to host multiple domain names on a single server. On |product|, from :guilabel:`Virtual hosts` page, is possible to configure web sites as Apache named virtual hosts. 

The virtual host configuration is part of the Web Server application inside the new Server Manager.
When a new virtual host is created, the new Server Manager will also automatically create all required DNS server alias.

Virtual host names (FQDN)
-------------------------

Is the list of Fully Qualified Domain Names that are associated to the virtual host. Values must be separated with a "," (comma).
To access virtual host, is also needed a DNS record. If enabled under "Additional actions" an alias for the server is automatically created on "DNS > Server alias", but it's useful only for clients that use the server as DNS.

Configuring a web application
-----------------------------

When a new virtual host is created, also the folder /var/lib/nethserver/vhost/`NAME` is created.
If FTP access is enabled, is possible to upload files to this folder using an FTP client and, virtual host name as username.

.. warning:: FTP access is disabled by default, you also need to enable it from FTP configuration page

HTTP authentication password should be different from FTP ones, because FTP is used for upload content on virtual host and HTTP to read content.

Apache permissions
------------------

FTP uploaded files are owned by the "apache" group. If you need to allow apache write or execution access, you can change group permissions using the FTP client

.. warning:: If a virtual host contains executable code, such as PHP
             scripts, user permissions and security implications must
             be evaluated carefully.

