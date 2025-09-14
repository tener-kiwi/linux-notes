# text manipulation

## stdout:
　>(<)・・・ファイルに直接出力をリダイレクトできる。（プログラムからではなくシェルからファイルが読み込まれるためfdで操作できる。)linuxはすべてがファイル扱いされているため一部のファイルを引数として実行できないコマンドに標準入力(stidin)として差し替えて実行できる。
　>>・・・ファイルに出力を直接追記できる
　2>・・・エラー出力をリダイレクトする
　&>・・・エラー出力と標準出力をまとめてリダイレクトする
　tee・・・標準出力を画面に出力しつつリダイレクトできる（追記したいときは-a）
　例:ls > listing_file
     cat < items.txt
     ls >> add_file
     ls non_existent_file 2> stderr_file
     ls ~ non_existent_file &> combine_file
     ls | tee -a tee.txt
     
    　
