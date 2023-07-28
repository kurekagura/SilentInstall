# KDiff3

## kdiff3-1.9.6-windows-64-cl.exe

```console
start /wait kdiff3-1.9.6-windows-64-cl.exe /S /D="O:\sw\KDiff3"
echo %errorlevel%
```

- /SILENTや/VERYSILENTではNG
- /DIRはNG
- /Dが効いてない（C:\Program Files\KDiff3になる）

```console
"O:\sw\KDiff3\uninstall.exe" /S
echo %errorlevel%
```

- /SILENT /VERYSILENTでもサイレントアンインストールできない。

## レジ情報メモ

```ini
[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\KDiff3]
"UninstallString"="\"O:\\sw\\KDiff3\\uninstall.exe\""
```

## 機能メモ

- コメント付与機能はない。
- パック機能はない。

## TIPS

- フォントを`MSゴシック 標準`にすると見やすくなる。

## 参考

- [KDiff3 Silent Install (How-To Guide)](https://silentinstallhq.com/kdiff3-silent-install-how-to-guide/)
- [KDiff3-Readme](https://invent.kde.org/sdk/kdiff3/-/blob/master/INSTALL)
