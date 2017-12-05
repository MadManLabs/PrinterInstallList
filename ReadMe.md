Printer Install List (English)
=====================

It is tool install Remote Windows Machine PrinterDriver and Printer from PrinterPlace.csv and DriverList.csv.

How to use
---------------------

run main.ps1

main.ps1 is explain under.

1. import PrinterPlace.csv by Import-Csv
2. Pick up printer from Branch and Section
3. import DriverList.csv by Import-Csv
4. To use Join-Object inner join PrinterPlace and DriverList
5. load add-port.ps1,create-printe.ps1,install-driver.ps1 to remote windows machine
6. execute install-drivers.ps1,install-ports.ps1,install-printers.ps1 to remote machine.
7. Install Driver and Make PrinterPort,Make Printer to Remote Machine.

Environment
-----------------------
Windows to able to use Powershell anything use.

I can run fine under enviroment.

- Windows7
- Windows Server2008
- Windows10

I use only Powershell v2 cmdlet,So, Maybe can run WindowsXP in PowerShell v2.

Printer Install List(Japanese)
=====================

PrinterPlace.csvとDriverList.csvから必要なドライバーを抽出し、遠隔地のWindowsマシンにプリンタードライバーやプリンタをインストールするためのツール。

使い方
---------------------

main.ps1を実行させます。

main.ps1の中身を簡単に説明すると下記のようになります。

1. PrinterPlace.csvをImport-Csvで取り込む
2. プリンターをインストールしたい支店(Branch)と部署(Section)で絞り込む
3. DriverList.csvをImport-Csvで取り込む
4. Join-Objectを使って絞り込んだPrinterPlaceとDriverListをINNER JOINする。
5. functionの中にあるadd-port.ps1,create-printe.ps1,install-driver.ps1を遠隔のWindowsマシンに読み込ませる。
6. install-drivers.ps1,install-ports.ps1,install-printers.ps1を遠隔地のWindowsマシンで実行
7. 遠隔地のWindowsでドライバーのインストール,ポートの作成,プリンターの作成が行われます。

環境
-----------------------
PowerShellが使えるWindowsであれば先ずはOK。

下記の環境で実行できました。

- Windows7
- Windows Server2008
- Windows10

PowerShell v2程度のCmdletしか使っていないので、PowerShell v2搭載されたWindowsXPでも動くかもしれない。


何故作ったのか？
-----------------------

弊社にはプリンターが沢山あり、そのメーカーや種類等がバラバラである。

- プリンターモデル 21種類
- ドライバー x86とx64で 42種類
- プリンター 61台

少しでもスムーズにプリンターがインストールできるように

- プリンタードライバー
- プリンターポート
- プリンター

の変数等をcsvファイルにまとめた。

これらのcsvファイルを活用してプリンターをインストールするツールを作った。



外部のツール
----------------------
csvのデータ同士を結合させるために下記のツールを使っております。

### Join-Object.ps1

Join data from two sets of objects based on a common value

For more details, see the accompanying blog post:
    http://ramblingcookiemonster.github.io/Join-Object/

For even more details, see the original code and discussions that this borrows from:

[Dave Wyatt's Join-Object](http://powershell.org/wp/forums/topic/merging-very-large-collections)

[Lucio Silveira's Join-Object](http://blogs.msdn.com/b/powershell/archive/2012/07/13/join-object.aspx)



License
-------------------
MIT License

(c) Yusuke Arakawa

Join-ObjectのLicenseがMITなので。
