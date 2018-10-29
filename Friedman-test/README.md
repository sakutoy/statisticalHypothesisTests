# Friedman-test
フリードマン検定
- 対応あり多群(3群以上)の検定
- 「複数ある群の中で母集団が異なる群が少なくとも一つ含まれるかどうか」を検定する
  - 例)ある薬を0mg, 5mg, 10mg投与したとき,薬の効果があるか否か検定せよ
- ノンパラメトリック検定
- Repeated-measures ANOVAに対するノンパラメトリックの代替方法

### 使い方
##### データの準備
- `testData.csv`に比較したい標本を`,`で区切りながら貼り付ける  
- 群間で対応しているデータが同じ列に並ぶように貼る
- 各行の先頭に群の名前を書く
- 必ず3群以上必要

```
GroupA,2,4,3,1,2,3,3,2,3,1
GroupB,3,5,4,2,4,3,5,5,3,2
GroupC,2,1,1,1,2,3,2,2,2,3
```

##### 実行
- 有意水準0.05で実行
```
python friedman-test.py
```
- 有意水準を設定したい場合
```
python friedman-test.py --level 0.01
```

別にデータを用意している場合
```
python friedman-test.py --input "csvファイルへのパス"
```

##### 結果
p値(p-value)が出力される  
有意差が観測された場合は`*`がつく
```
p-value = 0.000405329269196*
```