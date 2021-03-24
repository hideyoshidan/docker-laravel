■ メモ
  - docker-compose.yml
      ・privileged: true => コンテナ起動時に、privilegedオプションをつける
      ・command: - /sbin/init => これを実行させることにより、systemctlが使用できるようになる。

■ build後
  - second_serverのコンテナに入る
  - 以下のコマンドを実行する
      <!-- apache 起動 -->
      # systemctl start httpd
      <!-- apache の自動起動ON -->
      # systemctl enable httpd

