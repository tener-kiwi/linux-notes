# Text Manipulation

## stdout

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

    　
