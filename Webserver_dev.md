## Port forwarding
```
ssh -L [bind_address:]port:host:hostport name@hostaddress
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
