# 監視

* AWS CloudWatch
  * 参考
    * https://geeknavi.net/aws/cloudwatch-metrics
  * 設定が複雑
    * その分、表示は多彩にできる
  * デメリット
    * ~データは2週間以内のメトリクスのみ。~
      * 変更あり。
  * 標準メトリクス(アラーム参照)
    * CPU Utilization(CPU使用率)
    * Disk Reads(ディスク読み込み状況)
    * Disk Writes(ディスク書き込み状況)
    * Network In,Out(ネットワーク状況)
    * Status Check Failed(インスタンスのステータスチェック失敗)
  * ロギング
    * VM：CloudWatch エージェント
    * アプリ：CloudWatch Application Insights
* Azure Monitor
  * Azure Application Insights 前提？
  * ロギング
    * VM：Log Analyticsのエージェント
    * アプリ：Application Insights
* Google Stackdriver(Monitoring)
  * 参考
    * https://www.topgate.co.jp/gcp16-what-is-stackdriver-monitoring
    * https://qiita.com/koshilife/items/ac9dbed4ef11b57f4fac
  * 設定は簡素
  * AWSの情報もbuiltinで収集可能。
    * Azureもカスタムで設定すれば可能のはず。
  * 通知時の外部連携が豊富
  * ロギング
    * VM：Stackdriver エージェント
    * アプリ：GCP サービス？
  * デメリット
    * Amazon Linux2には非対応
    * グラフの色指定はできない？
    * データ保存期間が短い
    * 基本、英語のみ

|name|AWS CloudWatch|Azure Monitor|Google Stackdriver Monitoring|
|:---|:---|:---|:---|
|table|アラーム,イベント,ログ,メトリクス|アラート,メトリック,ログ,Service Health|Monitoring,Logging,Error Reporting|
|Monitoring|同上|-|Alering,Uptime Checks,Groups,dashboards|

* https://www.acronis.com/ja-jp/articles/cloud-services-comparison/
* 管理ツール：Gartner Peer 視点のベスト：Google Cloud
  * Google Cloud Platform
    * Google Stackdriver内の統合監視、ログ記録と診断、フルスタック監視、リアルタイム管理分析、リアルタイム例外監視と警告、分散トレース用のStackdriver Trace、ログ記録ステートメントを使用せずにコードを検査するStackdriverデバッガ、リソースを確認するDeployment Manager 、AP管理、導入、拡張、生産診断のためのGoogle Cloud Console、Google Cloud Shell、Cloud Platform Mobileアプリ、課金APIのドキュメント、およびワークフローの管理と自動化のためのGoogle Cloud APIなどのサービスを提供しています。
  * Amazon Web Services
    * AWSはロビジョニング用のAWS CloudFormation、リソースの監視と運用タスクの自動化用のAWS Systems Manager、インベントリ設定用のAWS CloudTrail、クラウドリソースとアプリケーションの監視用のAmazon CloudWatch、さらに設定とスケールの管理用のAWS OpsWorksを提供しています。
  * Microsoft Azure
    * Azureは、プラットフォームコンポーネントの状態監視用Azure Monitor、オンプレミスおよびクラウドデータの収集用Log Analytics、パフォーマンスの問題を診断するためのApplication Insights、ネットワークの問題を監視するためのNetwork Watcher、リソースの自動化、環境管理のためのAzure Advisor、Azure Resource Manageを提供します。 リソースの管理とデプロイのためのScheduler、アプリケーションの作業のスケジュールのためのScheduler、パフォーマンスと可用性を制御するためのTraffic Manager、ソリューションのデプロイのためのAzure Managed Applications、環境の管理のためのMicrosoft Azureポータル、リソースを接続するためのAzure Mobile App 、支出を検討するためのコスト管理、包括的なポリシー設定のためのAzureポリシー、繰り返し管理される環境のためのAzure Blueprints、データ損失から保護するためのAzure Backup、災害復旧を可能にするためのAzure Site Recovery、さらに脅威から保護するためのセキュリティセンターを提供しています。

* https://logmi.jp/tech/articles/320138

* 調査事項
  * 機能
  * 価格
  * ログ保存期間
  * メトリクスの種類
  * 表示のカスタマイズ
  * ドキュメントの調べやすさ　（AWS≧Azure＞GCP）
  * 操作しやすさ
  * その他の特徴

