# rpg2k-benchmark
対象の環境でツクール2000製ゲームの起動ができて操作も難なくできるかどうかを調べる

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