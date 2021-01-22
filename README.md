## SIGNATE JR東日本 列車運行予測 34th Place Solution
https://signate.jp/competitions/363
## 解法
### Preprocessing
testデータのtargetが1である全てのグループに対してNoneの比率を計算し、その中からrandomに取り出した比率でtrainデータの各グループをNoneに置き換えました

###  Feature Engineering
- ラグ特徴量
- 年月日
- 遅延時間の平均や中央値、最大値など
- 欠損情報

### Validation
GroupKFold 10-Fold(3 random seed average)

### Model
- LightGBM
	- 特にパラメータチューニングは行いませんでした
	- lossにはhuberを使用しました

### Postprocessing
予測値が負の値を0に置換しました
### Result
![](https://user-images.githubusercontent.com/63792861/105370202-acb5e500-5c46-11eb-9902-e5853564ef05.png)
