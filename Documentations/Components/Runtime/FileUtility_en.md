﻿# FileUtility

#### **Namespace**: Unity.SaveData.Core
---

## 概要:
`FileUtility` は、プラットフォームに適した方法でデータの保存と読み込みを行うためのユーティリティクラスです。JSON 形式でデータを扱い、ローカルファイルシステムまたは `PlayerPrefs` を使用してデータを永続化します。

## 機能と操作:
- **パスの生成**: 指定されたファイル名とパスに基づいて、現在のプラットフォームに適したファイルパスを生成します。
- **データの削除**: 指定されたパスと名前を持つデータファイルを削除します。
- **データの保存**: 指定された値を、指定されたパスとファイル名で保存します。保存形式は JSON です。
- **データの読み込み**: 指定されたパスとファイル名からデータを読み込み、指定された型に逆シリアライズします。データが存在する場合は `true` を返します。

## メソッド
| Name | Function |
|------|----------|
| `Save<TValue>` | 指定された値を JSON 形式で保存します。 |
| `Load<TValue>` | JSON 形式のデータを読み込み、指定された型に逆シリアライズします。 |
| `Remove` | 指定されたパスと名前を持つデータファイルを削除します。 |
| `IsExists` | 指定されたパスと名前を持つデータが存在するかどうかをチェックします。 |

## 使用例
- ゲームの設定やプレイヤーの進捗などのデータを保存する際に `Save` メソッドを使用します。
- ゲーム開始時や特定のポイントで設定や進捗を読み込む際に `Load` メソッドを使用します。
- 不要になったデータを削除する際に `Remove` メソッドを使用します。
- データの存在確認に `IsExists` メソッドを使用します。

---
## その他の注意事項
- `UNITY_WEBGL` と `UNITY_EDITOR` のディレクティブを使用して、プラットフォームごとの保存方法を分岐しています。WebGL の場合は `PlayerPrefs` を使用し、それ以外のプラットフォームではローカルファイルシステムを使用します。
- `DataStore<T>` 構造体は、`JsonUtility` が直接リストをシリアライズできない問題を解決するために使用されます。任意の型のデータを JSON 形式でシリアライズ/逆シリアライズすることができます。

`FileUtility` は、データの保存と読み込みを簡単かつ効率的に行うための便利なツールです。特に、ゲームの設定やユーザーの進捗など、永続的に保持したい情報の管理に役立ちます。

