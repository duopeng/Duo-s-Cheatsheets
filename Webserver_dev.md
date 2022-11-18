## Port forwarding
```
ssh -L [bind_address:]port:host:hostport name@hostaddress 
#the host address is relative to the remote server, not the client, so 127.0.0.1 will work fine if the target application server is listening on all interfaces - 0.0.0.0
```


## PM2 Process Management
```
#start an app
pm2 start app.js

#list managed app
pm2 ls

#manage app
pm2 restart app_name
pm2 reload app_name
pm2 stop app_name
pm2 delete app_name
```
