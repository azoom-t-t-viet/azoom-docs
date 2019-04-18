
##  VPC peeringの設定手順
目標はGCPの複数のプロジェクトのnetworkを接続するようにすることです。

以下は設定手順です。

**1. GCPのConsole画面にログイン**

**2. 新規Networkを作成**

* プロジェクトを選択し、NETWORKING > VPC network > VPC networks を選択します。

* `CREATE VPC NETWORK`ボタンを押下し、VPC networkの情報を入力します。

  * Name: network名を小文字、空白なしで入力します。
  
  * Description: networkの説明を入力します。
  
  * Subnets: 
  
    * Subnet creation mode: `Custom`を選択します。
    
    * New subnet:
    
      * Name: subnet名を小文字、空白なしで入力します。
      
      * Region: `asia-northeast1`を選択します。
      
      * IP address range: `default`というnetworkのIP address range以外を入力します。
        
        （例）10.69.0.0/20
      * Private Google access: `On`を選択します。
      
      * Flow logs: `Off`を選択します。
        
        New subnetを入力した上で、`Done`ボタンを押下
        
    * Dynamic routing mode: `Regional`を選択します。
    
    * DNS server policy: `No server policy`を選択します。
    
  その後、`Create`ボタンを押下します。

**3. VPC peeringを接続**

  * VPC network画面で`VPC Network Peering`を選択します。

  * `CREATE PEERING CONNECTION` ボタンを押下します。

  * `Continue` ボタンを押下します。

  * Peering connection情報を入力します。
  
    * Name: Peering connection名を小文字、空白なしで入力します。
    
    * Your VPC network: 自分のプロジェクトのNetworkを選択します。
    
    * Peered VPC network: 同じプロジェクトあるは、他のプロジェクトが選択できます。今回、他のプロジェクトを選択します。
    
      * Project ID: プロジェクト名を入力します。

      * VPC network name: プロジェクトのNetwork名を入力します。

    *  Exchange custom routesをクリックし、`Import custom routes`と`Export custom routes`をチェックに入れます。

  * `Create`ボタンを押下します。
    
    その後、VPC Network Peering画面が自動的に移動し、作成したPeering connectionのStatusは`Connected.`になったら、完成します。
