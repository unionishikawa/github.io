## ようこそ 

~~~
ようこそ！
あなたはn人目の入場者です。
~~~

ここは石の遊び場です。色々参考になる情報上げていければいいなと思います。

```c++
#include<iostream>
using namespace std;

int main(){
    cout<<"Hello,World"<<endl!
}
```

<p class="codepen" data-height="265" data-theme-id="dark" data-default-tab="js,result" data-user="unionishikawa" data-slug-hash="XvNpVa" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="XvNpVa">
  <span>See the Pen <a href="https://codepen.io/unionishikawa/pen/XvNpVa/">
  XvNpVa</a> by Ishi(<a href="https://codepen.io/unionishikawa">@unionishikawa</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>
[twitter](https://twitter.com/rock_ishi)
<script>

var cook;       //cookieデータを格納する変数
var cStart,cEnd;  //訪問回数部分を切取る為の位置を格納
var cnt;        //訪問回数を格納

//cookieが使えるか確認
if (navigator.cookieEnabled)
{
  cook=document.cookie + ";";  //変数cookにcookieデータを入れる
  
  //変数cStartにカウントデータの最初の位置を入れる
  cStart = cook.indexOf("counts=",0);
  
  //データの有無で分岐
  if (cStart == -1)
  {
    //データの無い場合は最初の訪問ということ
    document.write("1回目の訪問です！");
    
    //cookieに訪問回数=1を書き込む
    document.cookie="counts=1;";  
  }
  else
  {
    //カウントデータの最後の部分「;」の位置を取得
    cEnd=cook.indexOf(";",cStart);
    
    //数値の部分だけを切り取る
    cnt=cook.substring(cStart+7,cEnd);
    
    //数値に変換できない例外が出た時の処理
    try
    {
      //取得した回数に+1して表示する
      cnt=parseInt(cnt)+1;
      document.write(cnt+"回目の訪問です！");
      
      //cookieに訪問回数を書き込む
      document.cookie="counts="+cnt+";";
    }
    catch(e)
    {
      document.write("訪問回数の取得に失敗しました。");
    }
  }
}
else
{
  //cookieが使用できない時の処理
  document.write("cookieが使用できません。");
}

</script>