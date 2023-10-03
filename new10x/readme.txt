「コナミの新10倍カートリッジ」(英語名:Konami's Game Master II)のファームウェアです。
SRAMへのセーブデータはUSBメモリのルートディレクトリのNEW10X.BINファイルに記録されます。

使用法

1. new10x.binファイルの後ろに「コナミの新10倍カートリッジ」のROMファイル(128K)を連結します。

unixのcatコマンドを使用する例
$ cat new10x.bin 新10倍.rom > firmware.bin

windowsのcopyコマンドを使用する例
>copy /b new10x.bin + 新10倍.rom firmware.bin

2. uf2conv.exeを用いて1で作成したfirmware.binをuf2ファイルに変換します。

例: windowsコマンドプロンプト上で
uf2conv.exe firmware.bin firmware.uf2

uf2conv.exeはhttps://github.com/piigaa-densetu-two-dai/MSXpi_typeAにあります。

3. MSXに刺さっていない状態のMSXπをブートモードでPCに接続します。

MSXπのBOOTSELボタンを押しながらPCとUSB接続して下さい。
接続が成功するとドライブが認識されます。

4. MSXπに2で作成したfirmware.uf2ファイルを書き込みします。

3で認識されたドライブにfirmware.uf2をドラッグアンドドロップ(コピー)します。
コピーが完了するとドライブが見えなくなります。

5. 書込みが終わったらPCから外します。

注意：PCとの接続中はバスバッファの入力がフロート状態となります。
あまり良い状態ではないので長時間のPC接続は避けてください。

6. MSXπにUSBメモリを取り付けて完了

USBメモリはFAT32でフォーマットして下さい。
ディスクラベルの無いUSBメモリ(直にFAT32フォーマットされた物)は問題があるかもしれません。
NEW10X.BINファイルが無ければ自動作成されます。NEW10X.BINファイルがあればそれを使用します。

USB変換アダプター(OTGアダプター)が必要です。100円ショップ等で入手して下さい。

注意：
セーブデータが更新されるとその度にNEW10X.BINへの書込みが発生します。
ゲームソフトによっては高頻度で書込みが発生する可能性があります。
ご使用の際はUSBメモリのアクセスランプで過度な書込みが起きていないかを確認して下さい。
過度な書込みはUSBメモリの寿命を縮めますのでご注意ください。
