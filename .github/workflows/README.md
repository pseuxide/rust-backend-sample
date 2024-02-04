必要なもの
- Github Actions Secrets
  - PROJECT_ID: GCPのプロジェクトID。
  - DB_PASSWORD: databaseのパスワード。
  - TERRAFORM_SA_KEY_JSON_BASE64: terraform が SQLなどの作成に使用するサービスアカウントのキー。echo コマンドがバグらないようにBASE64でエンコードしておく。必要な権限は以下の通り:
    - Artifact Registry 管理者
    - Cloud SQL 管理者
    - サービス アカウント ユーザー
  - WORKLOAD_IDENTITY_PROVIDER: OIDCに使うprovider
- Github Actions env
  - PROJECT_ID: Secrets内のPROJECT_ID。
  - GAR_REPO_NAME: Artifact Registryのリポジトリ名。
  - IMAGE: Artifact Registryに保存するイメージの名前。
  - REGION: リージョン。asia-northeast1でいい。
  - TAG: latest
  - WORKLOAD_IDENTITY_PROVIDER: サービスアカウントの権限を借用するときに使う。
  - SERVICE_ACCOUNT: Cloud RunやArtifact Registry push時に使うサービスアカウント。アタッチする権限は以下の通り:
    - Artifact Registry 管理者
    - Cloud Run 管理者
    - Cloud SQL クライアント
    - サービス アカウント トークン作成者
    - サービス アカウント ユーザー
  - TERRAFORM_SA_KEY_JSON: Secrets内のTERRAFORM_SA_KEY_JSON。
  - DB_INSTANCE_NAME: Cloud SQLのインスタンス名。
  - DB_PASSWORD: Cloud SQLのパスワード。
  - DATABASE_URL: DBの接続用のURL。
