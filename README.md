# cloudformation-terraform-backend

このリポジトリはTerraformのステートファイルを格納し、ステートのロックを制御するためのAWSのS3バケットとDynamoDBテーブルを作成するためのAWS CloudFormationテンプレートを含みます。テーブルとバケットはTerraformのステートを安全に管理するために使用されます。

## デプロイ方法

### AWS Management Consoleからデプロイ

1. AWS Management Consoleにログインします。
1. CloudFormationサービスに移動します。
1. Create Stack をクリックします。
1. Upload a template fileを選択し、リポジトリのCloudFormationテンプレートファイルをアップロードします。
1. 必要なパラメータを入力し、Nextをクリックします。
1. Nextをクリックし、Create stackをクリックしてデプロイを開始します。

### AWS CLIを使用してデプロイ

前提条件として、あなたのローカル環境にはAWS CLIがインストールされており、適切に設定されている必要があります。
AWS CLIを使用して、以下のコマンドを実行します:

```bash
aws cloudformation create-stack --stack-name {your-stack-name} --template-body file://path/to/your/template.yaml
```

ここで、`{your-stack-name}`を任意のスタック名に、path/to/your/template.yamlを実際のテンプレートファイルのパスに置き換えます。
デプロイのステータスを確認するために、以下のコマンドを実行します:

```bash
aws cloudformation describe-stacks --stack-name {your-stack-name}
```

このコマンドはスタックの状態を表示します。"CREATE_COMPLETE"が表示されればデプロイが成功しています。
