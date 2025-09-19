# Text Manipulation

## stdin stdout stderr

- `>` : 出力をファイルにリダイレクトする  
  （プログラムからではなくシェルからファイルが読み込まれるため `fd` で操作できる。  
   Linuxはすべてをファイルとして扱うため、一部のコマンドではファイルを引数にできないが、標準入力 (`stdin`) に差し替えて実行できる。）

- `>>` : 出力をファイルに追記する  

- `2>` : エラー出力をリダイレクトする  

- `&>` : 標準出力とエラー出力をまとめてリダイレクトする  

- `tee` : 標準出力を画面に表示しつつファイルにリダイレクトできる  
  （追記したいときは `-a` オプションを使用）

### 使用例

```bash
ls > listing_file
cat < items.txt
ls >> add_file
ls non_existent_file 2> stderr_file
ls ~ non_existent_file &> combine_file
ls | tee -a tee.txt
```


 ## パイプと tee

- `|` : パイプ演算子。左側コマンドの標準出力を右側コマンドの標準入力に渡すことができる。  
  例:  
  ```bash
  ls -la /etc | less


## env (環境)

- 環境変数はシェルやプロセスに有用な情報を渡すために使われる。  
  変数の参照は `$変数名` で行う。

- 例:  
  ```bash
  echo $HOME


## cut

- `cut` : ファイルから文字やフィールドを抽出するためのコマンド。

### サンプル準備
```bash
echo 'The quick brown; fox jumps over the lazy  dog' > sample.txt


## paste

- `paste` : ファイル内の行を結合するコマンド。`cat` に似ているが、行単位で横方向に連結する。  

### サンプル準備
`sample2.txt` を以下の内容で作成する。  


## head

- `head` : ファイルの先頭部分を表示するコマンド。  
  デフォルトでは **最初の10行**を表示する。  

### 使用例
```bash
head /var/log/syslog


## tail

- `tail` : ファイルの末尾部分を表示するコマンド。  
  デフォルトでは **最後の10行**を表示する。  

### 使用例
```bash
tail /var/log/syslog


## expand と unexpand

- `expand` : テキストファイル内の **TAB をスペースに変換**する。  
- `unexpand` : **スペースを TAB に戻す**。  

### TAB をスペースに変換
```bash
expand sample.txt


## join と split

### join
- `join` : 共通のフィールドをキーにして、複数のファイルを結合するコマンド。  
- デフォルトでは **最初のフィールド**をキーにして結合される。  
- 結合するには、ファイルがあらかじめソートされている必要がある。  

#### 例1: デフォルトの結合
`file1.txt`  

