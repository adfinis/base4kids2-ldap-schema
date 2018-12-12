# base4kids2 LDAP schema
This repository contains an LDAP schema with additional attributes and object
classes for [Base4Kids](http://www.base4kids.ch). The schema is currently
available in the [LDIF form](base4kids2.ldif) required by the [389 Directory
Server](https://directory.fedoraproject.org/).

## Usage
### Import the schema
To import the schema into a 389 directory server, proceeed with the following
steps on CentOS 7 or RHEL 7:
```bash
# The name of the 389 directory server instance
serverInstanceName="example-01"

# Download the base4kids2 schema
wget -O "/etc/dirsrv/slapd-${serverInstanceName}/schema/99base4kids2.ldif" \
    "https://raw.githubusercontent.com/adfinis-sygroup/base4kids2-ldap-schema/master/base4kids2.ldif"

# Restart the directory server instance
systemctl restart "dirsrv@${serverInstanceName}.service"
systemctl status "dirsrv@${serverInstanceName}.service"
```

## License
base4kids2-ldap-schema is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as published by the
Free Software Foundation, version 3 of the License.

## Copyright
Copyright (c) 2018 [Adfinis SyGroup AG](https://adfinis-sygroup.ch)
