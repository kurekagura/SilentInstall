# SQL Server 2022 Express

展開したオフラインインストーラの中にある`setup.exe /help`でオプションを一覧できます。

以下のようなiniファイルを利用することもできます。iniファイルとコマンド引数の兼用もできるようです（パスワード等）。

```ini
[OPTIONS]
ACTION="Install"
...
```

```console
# コマンドプロンプトの場合
setup.exe /ConfigurationFile=ConfigurationFile.ini

# PowerShellの場合
Start-Process -Wait -FilePath "Setup.exe" -ArgumentList "/ConfigurationFile=ConfigurationFile.ini"
```

## 一例

```console
setup.exe /QUIET="True" /QUIETSIMPLE="False" ^
/IACCEPTSQLSERVERLICENSETERMS="True" ^
/SUPPRESSPRIVACYSTATEMENTNOTICE="True" ^
/ACTION=install ^
/FEATURES=SQLENGINE ^
/INSTANCENAME=INSTA1 ^
/INSTANCEDIR="O:\Microsoft SQL Server" ^
/SQLSVCPASSWORD="sa password" ^
/SQLSYSADMINACCOUNTS="<HOSTNAME>\<ACCOUNT>" ^
/AGTSVCACCOUNT="NT AUTHORITY\NETWORK SERVICE"
```

※ /FEATURES=SQLではReplicationもインストされます。

各サービスのログインは次のようになります。

```text
【MSSQL$INSTA1】(表示名：SQL Server (INSTA1)):
NT Service\MSSQL$INSTA1
【SQLTELEMETRY$INSTA1】(表示名：SQL Server CEIP service (INSTA1))
NT Service\SQLTELEMETRY$INSTA1
【SQLAgent$INSTA1】(表示名：SQL Server エージェント (INSTA1))
Network Service
```

## UIインストール時のメモ

サービスアカウント

SQL Server データベースエンジン：NT Service\MSSQL$インスタンス名  
SQL Server Browser：NT AUTHORITY\LOCALSERVICE  

SQL Server管理者の指定

<ホスト名>\<インストール作業しているアカウント（自分）>

が一件追加済み。更に追加することも可能。

## 参考

- [Microsoft SQL Server 2022 Express Silent Install (How-To Guide)](https://silentinstallhq.com/microsoft-sql-server-2022-express-silent-install-how-to-guide/)