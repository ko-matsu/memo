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
* 参考
  * 企業のCloud移行について
    * https://www.atmarkit.co.jp/ait/articles/1907/26/news021.html

* 対応表の最新版
  * https://www.apps-gcp.com/gcp-aws-service-correspondence-comparison-2019-02/
* 比較サイト
  * https://cloud-textbook.com/category/vs/
* VM比較
  * https://cloud-textbook.com/46/
  * 性能は高めだが、設定はシンプル。起動も早い。価格は若干安い。
  * グローバルIPのみでの運用となる。
* Storage比較
  * https://cloud-textbook.com/48/
  * 月額利用料金は若干安いが、Getリクエストの料金はAWSよりは高い。
  * BigQueryとの連携可能。
  * (欠点)SFTPは使用できない
* Database比較
  * https://cloud-textbook.com/50/
  * RDBMS
    * ほぼ変わらないが、細かな点では違いがあるので注意。
    * DB移行の場合、GCPは種類(バージョンやアプリ)が少ないため注意。
    * またカスタマイズの性能上限も低め。
    * その分か、GCPは価格が安い。
  * NoSQL
    * 大量データ分析に Cloud Bigtable がある。
    * これを機能を絞って使いやすくしたのがCloud Data Store。アプリ利用目的のNoSQLDBとなる
    * さらに上記をモバイルアプリ向けにしたのがCloud Firestore。
      * デバイス間でのデータ同期を容易にできるようにする。
* Networking比較
  * DNS
    * https://cloud-textbook.com/58/
      * 特徴として、他ネームサーバとのゾーン転送がある
  * ロードバランサー
    * https://daddytrevia.com/gcp/CloudLoadBalancing/
      * 論理的な、ソフトウェアデザインによるロードバランサー。非常にシンプル。
      * 性能はGoogleがNW制御に使っているだけあって高い。
  * http://comparecloud.in/?fbclid=IwAR2UXuPCL-15NlaHaqhzp4SKPkcwnQX9JQGg1v3my-EGyo_MNEFN6S-sl1E
* 管理機能比較
  * https://qiita.com/watarin/items/d867dcfac9cfd62abbc0
    * IAM
      * ADと同じく階層構造となっている。
      * インスタンスそのものに紐づくため、個別に設定が必要。
      * 以下の図が分かりやすい。
        * https://ameblo.jp/principia-ca/entry-12144854519.html
    * Firewall Rule
      * ACL
        * 優先度順にマッチしたところで決まる方式
        * （ネットワークのACLで一般的な方式）
      * アタッチ
        * VPC固有
        * 個別のルールでターゲット（適用されるインスタンス）を限定したルールが作れる。
        * タグとか、サービス アカウントとかで指定できる
* VPC比較
  * GCP は各プロジェクトを VPC で接続可能な共有 VPCという機能がある。
  * ただし、組織アカウントが必要。
  * https://qiita.com/sirotosiko/items/5dae7d6db523405a729d
    * IAM含め、この図がわかりやすい。
