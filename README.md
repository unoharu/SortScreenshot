# Sort Files Script

このリポジトリには、指定されたディレクトリ内のファイルを日付ごとに整理するシェルスクリプト `sort_files.sh` が含まれています。

## 機能

`sort_files.sh` スクリプトは、指定されたディレクトリ内のファイルを作成日ごとにサブディレクトリに整理します。各ファイルはその作成日を基にしたディレクトリに移動されます。

## 使用方法

### 前提条件

- macOS
- Bash

### 手順

1. `.env` ファイルを作成し、整理対象のディレクトリパスを設定。

    ```sh
    TARGET_DIR=/path/to/your/ScreenShot
    ```

2. `.env` ファイルをプロジェクトのルートディレクトリに配置。

3. `sort_files.sh` スクリプトに実行権限を付与。

    ```sh
    chmod +x /path/to/your/sort_files.sh
    ```

4. スクリプトを実行

    ```sh
    /path/to/your/sort_files.sh
    ```

5. スクリプトエディタを用いてアプリケーション化
   
   ```sh
    do shell script "/path/to/your/sort_files.sh"
    ```

6. 実行デモ
   
   ![Sort_ScreenShot](https://github.com/user-attachments/assets/890a14da-5ac9-4884-9394-b0f015105f16)
