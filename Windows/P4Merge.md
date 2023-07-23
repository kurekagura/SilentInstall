# P4Merge

## 2023.2/2446649

```console
start /wait msiexec /i p4vinst64.msi INSTALLDIR="O:\sw\Perforce" ADDLOCAL=P4MERGE,QT /q /passive
echo %errorlevel%
```

```console
start /wait msiexec /x {D72F1405-94FE-45F3-A4CD-F6809CE3B7EE} /q /passive
echo %errorlevel%
```

- [Automated Deployment of Helix Visual Client (P4V) 2020.1 and later versions](https://portal.perforce.com/s/article/17304#msi)
