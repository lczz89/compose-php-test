# dockerfile
my dockerfile
#相关操作
新建runtime文件夹，运行数据目录，如logs,mysql

#502
###recv() failed (104: Connection reset by peer)
在机器配置不高的情况下，可能会出现内存泄露，某些查询大量数据的链接502，可以重新挂载php-fpm.conf  
pm模式改为dynamic
#```
pm = dynamic  
pm.max_children = 15  
pm.start_servers = 8  
pm.min_spare_servers = 6  
pm.max_spare_servers = 15  
pm.max_requests = 500  
pm.process_idle_timeout = 10s;  
; pm.max_requests = 10240  
pm.status_path = /fpm/status
#``` 
