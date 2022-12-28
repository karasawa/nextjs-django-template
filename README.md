# nextjs-django-template

nextjsとdjangoで開発する用のテンプレート

以下の流れでアプリを立ち上げる

-------------------

【前提】
1.
docker-compose.ymlのある階層で、以下コマンド実行
docker compose up -d

【backend】
1.
docker exec -it backend bash
で、backendコンテナに入る

2.
django-admin startproject プロジェクト名 .
でdjangoプロジェクトを作成

3.
settings.pyをpostgresql用に書き換える
（デフォルトではsqlite用の設定になっている）

4.
python manage.py runserver 0.0.0.0:8000
で、サーバ起動


【frontend】
1.
docker exec -it frontend bash
で、frontendコンテナに入る

2.
npx create-next-app@latest プロジェクト名 --typescript
でnextjsプロジェクトを作成

3.
npm run dev
で、サーバ起動


【remote container接続】
1.
backend/.devcontainer.json
を作成

2.
frontend/.devcontainer.json
を作成

3.
プロジェクトルートをvscodeで開き、左下の緑色アイコンをクリック、
「open folder in container」を選択