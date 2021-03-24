### メモ
  - docker-compose.yml
      ・privileged: true => コンテナ起動時に、privilegedオプションをつける
      ・command: - /sbin/init => これを実行させることにより、systemctlが使用できるようになる。

### build〜動作確認
* `$ docker-compose up -d`
    Name                   Command               State                       Ports                     
-------------------------------------------------------------------------------------------------------
second_mail     MailHog                          Up      0.0.0.0:1025->1025/tcp, 0.0.0.0:8025->8025/tcp
second_mysql    docker-entrypoint.sh mysqld      Up      0.0.0.0:13309->3306/tcp, 33060/tcp            
second_php      docker-php-entrypoint php-fpm    Up      0.0.0.0:55009->9000/tcp                       
second_redis    docker-entrypoint.sh redis ...   Up      0.0.0.0:6379->6379/tcp                        
second_server   /sbin/init                       Up      0.0.0.0:80->80/tcp                            
second_sftp     /entrypoint second:second_ ...   Up      0.0.0.0:2222->22/tcp      

