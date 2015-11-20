###### OS Provisioning through Cobbler
 * require kona rpm package
 * sample output

```

[root@server1 provision]# ./cobbler-info
- looking for Cobbler at http://server1.example.com:443/cobbler_api
Traceback (most recent call last):
  File "/usr/lib/python2.7/site-packages/koan/utils.py", line 570, in __try_connect
    xmlrpc_server.ping()
  File "/usr/lib64/python2.7/xmlrpclib.py", line 1224, in __call__
    return self.__send(self.__name, args)
  File "/usr/lib64/python2.7/xmlrpclib.py", line 1578, in __request
    verbose=self.__verbose
  File "/usr/lib64/python2.7/xmlrpclib.py", line 1264, in request
    return self.single_request(host, handler, request_body, verbose)
  File "/usr/lib64/python2.7/xmlrpclib.py", line 1312, in single_request
    response.msg,
ProtocolError: <ProtocolError for server1.example.com:443/cobbler_api: 400 Bad Request>
- looking for Cobbler at https://server1.example.com:443/cobbler_api
what is it? profiles
['CentOS-7_84-1503-01-x86_64']
what is it? systems
{ mac_address_eth0 : 08:00:27:00:93:01 }
{ allow_duplicate_macs : 0 }
what is it? distros
['CentOS-7_84-1503-01-x86_64']
what is it? repos
['CentOS-7_84-1503-01-x86_64']
what is it? images
[]

```

 * compares to cobbler

```
# cobbler system dumpvars --name=node1 | grep profile_name
profile_name : CentOS-7_84-1503-01-x86_64
```
