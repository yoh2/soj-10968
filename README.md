これは何？
----------

スタックオーバーフロー日本語版に投稿された質問 [Git のマージで「共通の祖先」は何故必要ですか？](http://ja.stackoverflow.com/questions/10968/git-のマージで-共通の祖先-は何故必要ですか) に付けられた、 @unarist さん回答の実証用ソース。
各ブランチの意味は以下の通り。

 - master: 共通の祖先。hoge1.txt ～ hoge5.txt まで、祖先となるファイルが異なっている。
    * hoge1.txt: 元々なかった `hoge` と `piyo` をそれぞれ追加した
    * hoge2.txt: `hoge` と `piyo` をそれぞれ削除した
    * hoge3.txt: 実は branchA は何も変更していない
    * hoge4.txt: 実は branchB は何も変更していない
    * hoge5.txt: そもそも `B` すらなかった
 - branchA, branchB: それぞれ hoge1.txt ～ hoge5.txt を編集したもの。
   各ブランチ内では、 hoge1.txt ～ hoge5.txt までの内容がすべて同一になっている。

clone した後、 branchA を branchB へマージ、あるいはその逆を行うと、共通の祖先が異なることにより、異なるマージ結果になるのが分かります。

