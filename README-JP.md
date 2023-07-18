＃AELX

AELXは、`.aelx`構成ファイルを読み込み、処理するためのコマンドラインソフトウェアです。このソフトウェアは、構成ファイルからキーと値のペアを抽出し、JSON形式または環境変数としてデータを出力するオプションをサポートしています。

## インストール

AELXをインストールするには、次の手順に従ってください:

1. AELXリポジトリをクローンします:

   ```shell
   git clone https://github.com/refaldyrk/aelx.git
   ```

2. プロジェクトディレクトリに移動します:

   ```shell
   cd aelx
   ```

3. AELXを実行します:

   ```shell
   aelx --f=something.aelx -k=key
   ```

## 使用法

次のフラグを使用して`aelx`コマンドを実行します:

- `-k`: 抽出したいキーの値。
- `--f`: 読み込む`.aelx`ファイルの名前。
- `-j`: オプションフラグ。データをJSON形式で出力します。デフォルト: `false`。
- `--o`: オプションフラグ。JSON形式の出力ファイル名を指定します。デフォルト: `aelx.json`。
- `-e`: オプションフラグ。データを環境変数として出力します。デフォルト: `false`。

### 使用例

1. 構成ファイルから特定のキーの値を取得する場合:

   ```shell
   aelx -k <キー名> --f <ファイル名.aelx>
   ```

   例:
   ```shell
   aelx -k hello --f config.aelx
   ```

2. データをJSON形式で出力する場合:

   ```shell
   aelx -k <キー名> --f <ファイル名.aelx> -j true
   ```

   例:
   ```shell
   aelx -k hello --f config.aelx -j true
   ```

3. カスタムファイル名でJSON形式でデータを出力する場合:

   ```shell
   aelx -k <キー名> --f <ファイル名.aelx> -j true --o <出力.json>
   ```

   例:
   ```shell
   aelx -k hello --f config.aelx -j true --o output.json
   ```

4. データを環境変数として出力する場合:

   ```shell
   aelx -k <キー名> --f <ファイル名.aelx> -e true
   ```

   例:
   ```shell
   aelx -k hello --f config.aelx -e true
   ```

## `.aelx`ファイル形式

`.aelx`ファイルは特定の形式を使用します。以下はサポートされている`.aelx`ファイル形式の例です:

```
project: start|
[キー1] 値1|
[キー2] 値2|
[キー3] 値3|
project: end|
```

正しいデータの抽出を保証するために、`.aelx`ファイルがこの形式に従っていることを確認してください。

## `.aelx`設定ファイルの例

以下は`.aelx`設定ファイルの例の内容です:

```
project: start|
hello[世界]|
lorem[ipsum]|
project: end|
```

この例では、2つのキーと値のペアがあります:

- キー: `hello`、値: `世界`
- キー: `lorem`、値: `ipsum`

これらのキーの値を取得したり、必要に応じてデータの抽出を行うために、`aelx`コマンドを使用できます。