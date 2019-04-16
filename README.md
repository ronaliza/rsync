
todo
	
ps aux|grep rsync|awk '{print $2}'|xargs kill -9

cd  /home/wwwroot/www.ck180.net
rsync -rP -arvz -e 'ssh -p 10001' --progress \
 root@104.192.84.225:/home/wwwroot/www.ck180.net/ 	/home/wwwroot/www.ck180.net/
	

cd  /www/wwwroot/img1.qdosm.cn
rsync -rP -arvz -e 'ssh -p 10001' --progress \
 root@104.192.84.225:/www/wwwroot/ck180_qdosm_cn/ 	/www/wwwroot/img1.qdosm.cn/
	

cd  /www/backup/database/
rsync -rP -arvz -e 'ssh -p 10001' --progress \
 root@104.192.84.225:/www/backup/database/Db_www_ck180_net_20190311_013837.sql.gz 	/www/backup/database/


ssh-copy-id -i  /root/.ssh/id_rsa.pub  -p 10001 root@104.192.84.225



ssh -p '10001' 'root@103.107.236.126'
