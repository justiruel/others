## start new process
 - go to /snaap-api-feathers
 - run :

```
pm2 start src --name "snaapp-api-feathers" // ini seperti nodemon src
```

## delete process 

```
pm2 delete snaapp-api-feathers
```

## restart process

```
pm2 restart snaapp-api-feathers
```
## stop process

```
pm2 stop snaapp-api-feathers
```

## log process

```
pm2 logs 0 --lines 1000
```

## list

```
pm2 list
```
