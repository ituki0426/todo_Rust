
# comment_models.rs

このファイルでは、利用するデータの構造体を定義している。

# comments_action.rs

データのinsertなどに利用する関数を定義するファイル。

## ➀使用するモジュール

```rust
use mongodb::Collection;
use mongodb::bson::{doc, to_document};
use mongodb::options::{FindOptions, FindOneAndUpdateOptions, ReturnDocument};

use std::sync::Arc;
use anyhow::{Context, anyhow};

use crate::comments_models::TodoComments;
use crate::error::AppError;
```

## ➁DBにコメントを登録するinsert_comment

## ➂DBのデータをdeleteする関数delete_omment

## ➃DBにデータをupsertするupsert_comment

データベースのテーブルにレコードが存在しない場いいはそのレコードを新規挿入(insert)し、レコードが既に存在する場合は既存のレコードを更新(update)する処理のこと。

# lib.rs

```actix_web::App```にサービスとして登録する関数を定義する。

先程の、```comments_aciton.rs```内で定義した関数を呼び出して使用する。

# build_serser.rs

このファイルでは```aactix_web::main```内でサーバを作成します。

mongobのコレクションはアプリケーションビルダーの```app_data```メソッドで与えます。
