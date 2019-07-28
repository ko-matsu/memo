memo

# AWS, GCP

* AWS (https://aws.amazon.com/jp/)
  * EC2
    * 仮想サーバー（OS:win,linux）
  * S3 (simple storage service)
    * ディスクへのデータ格納（AzureのStorage相当）
  * EBS (EC2 Block Store)
    * ☆Block単位でのStorage機能。迅速なスケールが可能。☆
  * RDS
    * リレーショナルデータベース
  * ElastiCache
    * インメモリデータストア。メモリ上でStorageを一時保存できる。
  * DynamoDB
    * NoSQL database
  * Route53
    * DNS
  * ELB (Elastic Load Balancing)
    * ロードバランサー
  * IAM (Identity and Access Management)
    * AWSのサービスやリソースへのアクセス管理機能。
  * VPC (Virtual Private Cloud)
    * 定義した仮想ネットワーク内でAWSリソースを起動できる。
      * VPN接続との連動か？
  * セキュリティグループ (EC2 セキュリティグループ)
    * EC2へのアクセス制御？
  * 雑感
    * StorageやNetwork周りが強い印象。
    * ロボットやAIなどはGCPと同じくらい？（かは微妙）
    * ゲーム系やロボット/人工衛星のサービスが存在（他には無い）。
    * 管理機能関連はかなり多いので、細かいチューニングが強そうではある。
* GCP (https://cloud.google.com/?hl=ja)
  * Compute Engine
    * EC2相当。
  * Cloud Storage
    * S3相当のStorage機能
  * Persistent Disk
    * EBS (EC2 Block Store)相当、らしい。でも劣っているような。。
  * Cloud SQL
    * RDBMS。RDS相当。ただしサポートはMySQL、PostgreSQL、SQL Serverなので少ない。
  * Cloud Memorystore
    * ElastiCache相当。
  * Cloud Bigtable
    * Dynamo DB相当。
  * Cloud DNS
    * Route53相当
  * Cloud Load Balancing
    * ELB (Elastic Load Balancing)相当
    * 強力らしい。
  * Cloud IAM (Identity & Access Management)
    * 同上
  * Virtual Private Cloud
    * AWS VPC相当。
    * 基本的に全インスタンスに外部IPをつけようとする。
  * ファイアウォールルール
    * EC2 セキュリティグループ相当
    * ただしAWSと異なり、 インスタンス毎に許可されている情報を追跡するのが大変とのこと。
  * 対応表
    * https://dev.classmethod.jp/cloud/aws/aws-gcp-fit-and-gap-2016-07/
  * 参考になりそうなサイト
    * https://qiita.com/kazu23pole/items/9828a5e025c7fdd15932
    * http://www.mpon.me/entry/2017/04/22/020428
    * http://album.cloudit.co.jp/?p=4075
    * https://qiita.com/hayao_k/items/906ac1fba9e239e08ae8
    * https://goworkship.com/magazine/4-cloud-services/
  * 雑感
    * 一応、AWSと同じサービスは持ってはいるようだが、痒い所に手が届くかは不明。
      * 個人的に、StorageとNetworkはAWSの方が強そうに思える。ただし少し高め。
    * ロードバランサーは強力とのこと。
      * https://www.apps-gcp.com/gcp-load-balancer-setting/
    * 権限管理(IAM)もあるが、どうやらGCPは雑らしい。
      * セキュリティ的には（設定範囲が雑そうで）微妙か？
    * どうもG Suiteとの連携を前提にしている模様。
      * AzureでのAD前提と同じ感じか？
      * G Suite前提なら、割と良いのかも？
    * AI関連は強そうに感じる。研究用途の印象あり。
    * IoT関連はAWS,Azureに(サービスの豊富さで)一歩劣る感じである。
    * サービス全体として、取捨選択がはっきりしているように思える。
    * 価格安い
    * ビッグデータ解析強い。
    * インフラは強靭？らしい。サービスではなく、サーバーの強みかな？
    * 仮想マシンの起動速度は速いらしい。
    * 総評：インフラは強力なものの独自色が非常に強い。
* Azure
  * 雑感
    * 感覚的には、AD連携やOffice365連携が強みなのだろうと思う。
    * Windowsおよび.NET(C#)などとの連携については、間違いなく強そうである。
    * あとPower BI連携があるので、データ可視化も強いかもしれない。
