# WinMerge

## WinMerge-2.16.30-x64-Setup.exe

```console
start /wait WinMerge-2.16.30-x64-Setup.exe /DIR="O:\sw\WinMerge" /VERYSILENT
echo %errorlevel%
```

```console
"O:\sw\WinMerge\unins000.exe" /VERYSILENT /NORESTART
echo %errorlevel%
```

## レジ情報メモ

```ini
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\WinMerge_is1]
"QuietUninstallString"="\"O:\\sw\\WinMerge\\unins000.exe\" /SILENT"
```