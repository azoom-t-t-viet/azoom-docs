**1. KubernetesのClusterを作成**

* Kubernetes Engine > Clusters を選択します。

* `CREATE CLUSTER`ボタンを押下します。 

* cluster情報を入力します。

  * 左コラムのCluster templatesにStandard clusterを選択します。その後、右クラムに情報を入力します。
   
  * Name: cluster名を小文字、数字、ハイフンのみ入力できます。
  
  * Location type: `Zonal`を選択します。
  
  * Zone: `asia-northeast1-b`（東京）を選択します。
  
  * Master version: `(default)`を含むのを選択します。
  
  * Node pools > default-toolの情報を入力します。
  
    * Number of nodes: node数です。`2`を入力します。
    
    * Machine type: `1 vCPU`を選択します。
    
  * Availability, networking, security, and additional featuresをクリックし、入力します。
  
    以下は必須な設定項目だけ書きます。他の項目はデフォルト値がいいです。

    * Networking:
    
        * VPC-native: `Enable VPC-native (using alias IP)`をチェックを入れます。
        
        * Network: `VPC peeringの設定手順`ステップの作成したnetworkを選択します。
        
    * Stackdriver: `Enable Stackdriver Logging service`や`Enable Stackdriver Monitoring service`や`Try the new Stackdriver beta Monitoring and Logging experience`をチェックを入れます。
            
* `Create`ボタンを押下し、Kubernetes clusters画面から作成したclusterの状態が確認できます。
