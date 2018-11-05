# rpg2k-benchmark
対象の環境でツクール2000製ゲームの起動ができて操作も難なくできるかどうかを調べる

```
git clone https://github.com/katai5plate/rpg2k-benchmark && cd rpg2k-benchmark
```
- 通常起動
```
RUN(Normal).bat
```
- シングルコア
```
RUN(SingleCore).bat
```
- 背景ウィンドウつきシングルコア
```
RUN(SingleCoreBB).bat
```

## 操作と検証
- `RUN(Normal).bat` を起動。ウィンドウが表示され、`start`に矢印キーでカーソルを合わせEnterでき、その後`ok`の表示が出るまで画面指示に沿って操作できれば正常。
- 起動できない、または正常動作しない場合は`RUN(SingleCore)`を試す。

## 追加検証
- `操作と検証`がウィンドウモードでのみ成功し、フルスクリーンが失敗する場合、以下を試す。
1. `RPG_RT.exe`のプロパティを開き、互換モードを`Windows7`に設定し`RPG_RT.exe`を直接実行・検証->`RUN(SingleCoreFS).bat`を直接実行・検証
2. `RPG_RT.exe`のプロパティを開き、互換性設定から`640x480の解像度で実行する`に設定し`RPG_RT.exe`を直接実行・検証->`RUN(SingleCoreFS).bat`を直接実行・検証
3. `コントロールパネル`->`プログラムと機能`->`Windowsの機能の有効化または無効化`->`レガシ コンポーネント`->`DirectPlay`にチェックをつけて、`RPG_RT.exe`を直接実行・検証->`RUN(SingleCoreFS).bat`を直接実行・検証
4. `+DLL`ディレクトリに入っている`winmm.dll`を`bin`ディレクトリにコピーし`RPG_RT.exe`を直接実行・検証->`RUN(SingleCoreFS).bat`を直接実行・検証
5. `+DLL`ディレクトリに入っている`wined3d`ディレクトリの中身を`bin`ディレクトリにコピーし`RPG_RT.exe`を直接実行・検証->`RUN(SingleCoreFS).bat`を直接実行・検証
6. `bin`ディレクトリから`winmm.dll`を削除し`RPG_RT.exe`を直接実行・検証->`RUN(SingleCoreFS).bat`を直接実行・検証
- 上記検証でフルスクリーン起動自体に成功した場合、以下も確認する
1. `RPG_RT.exe`・`RUN(SingleCoreFS).bat`を実行してすぐの画面で、グレーの背景が点滅していたら異常、そうでなければ正常

## 知見
### RPG_RT CommandLine Params
```
RPG_RT.exe <NULL|TestPlay|BattleTest> <NULL|HideTitle> (Window)
```
- 引用: http://cheater.seesaa.net/article/232220137.html

### RPG_RT.ini Params
|query|desc|true|
|-|-|-|
|GameTitle|ゲームタイトル|文字列|
|MapEditMode|エディタ操作ログ（レイヤー選択）|文字列|
|MapEditZoom|エディタ操作ログ（ズーム率）|文字列|
|FullPackageFlag|RTP不要フラグ（v1.5x以前は要`Harmony.dll`）|1|

- 引用: http://logos.yumenogotoshi.com/tkool2_spec.html

### その他
- `FullPackageFlag=1`のとき、PCにRTPがインスコされてようがされてまいが同じ動作になる
