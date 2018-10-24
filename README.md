# rpg2k-benchmark
対象の環境でツクール2000製ゲームの起動ができて操作も難なくできるかどうかを調べる

```
git clone https://github.com/katai5plate/rpg2k-benchmark && cd rpg2k-benchmark
RUN.bat
```

## 操作と検証
1. RUN.batを起動して、ウィンドウモードで起動するかどうか
2. eと出たときにEnterで次へ遷移するかどうか
3. Zという文字が出て消えたとき、決定キーを押して次へ進むかどうか
4. Xという文字が出て消えたとき、取り消しキーを押して次へ進むかどうか
5. Sという文字が出て消えたとき、シフトキーを押して次へ進むかどうか
6. Uという文字が出て消えたとき、上キーを押して次へ進むかどうか
7. Dという文字が出て消えたとき、下キーを押して次へ進むかどうか
8. Lという文字が出て消えたとき、左キーを押して次へ進むかどうか
9. Rという文字が出て消えたとき、右キーを押して次へ進むかどうか
10. okという文字が出て消えたとき、決定キーを押して次へ進むかどうか
11. eと出たときに下・下・Enterで閉じるかどうか

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
