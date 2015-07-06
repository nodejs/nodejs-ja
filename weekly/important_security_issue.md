<!--
Critical security releases for node.js and io.js
-->

# Node.js と io.js のCritical Security Issue について

緊急のセキュリティパッチについて

---

<!--
node.js-v0.12.6
io.js-v2.3.3
io.js-v1.8.3
-->

- [node.js-v0.12.6](http://nodejs.org/dist/v0.12.6/)
- [io.js-v2.3.3](https://iojs.org/dist/v2.3.3/)
- [io.js-v1.8.3](https://iojs.org/dist/v1.8.3/)

<!--
First, the obvious: the handling of this hasn’t been ideal, it would have been nice to take our time and do this more strategically. It’s evening in the USA and it’s the weekend of the 4th of July.
-->

初めに、このような処理は我々にとって理想的な方法ではありません。もっと戦略的に更新し、時間を使って更新する方がより良い方法である事は明らかでしょう。今は USA の夕方で、 7/4 の週末です。

<!--
We made the call to push forward because details about the bug and potential exploit has inadvertently made its way to a public forum so we’d rather given companies and users the tools to protect themselves and mitigate DoS if they happen to become a reality than sit on it and cross our fingers. The timing sucks, particularly for the USA where it’s hitting the weekend and the whole 4th of July thing makes this a nightmare for people managing large deployments but this is the call we made with the information available.
-->

バグの詳細と潜在的なエクスプロイトが public なフォーラムでその脆弱性を突くための方法が公開されてしまいました。そのため、我々はNode.jsを使っている企業やユーザーに現実的に発生する DoS 攻撃を和らげて、それらから守るためのツールを与えたほうが、ただ座って起きないように祈るよりも良いだろうと判断し、緊急パッチを公開することにしました。 タイミングはありえないほどダメでした。特に USA では週末に重なっていて、7/4 （独立記念日）の中で大きな開発を行うのは人々にとっては悪夢に近いです。しかしこの情報を公開することを決定しました。

<!--
A short history
-->

# 経緯

<!--
Kris Reeves and Trevor Norris pinpointed a bug in V8 in the way it decodes UTF strings. This impacts Node at the Buffer to UTF8 String conversion and can cause a process to crash. The security concern comes from the fact that a lot of data from outside of an application is delivered to Node via this mechanism which means that users can potentially deliver specially crafted input data that can cause an application to crash when it goes through this path. We know that most networking and filesystem operations are impacted as would be many user-land uses of Buffer to UTF8 String conversion. We know that HTTP(S) header parsing is not vulnerable because Node does not convert this data as UTF8. This is a small consolation because it restricts the way HTTP(S) can be exploited but there is more to HTTP(S) than header parsing obviously. We also have no information yet on how the various TLS terminators and forward-proxies in use may potentially mitigate against the form of data required for this exploit.
-->

Kris Reeves と Trevor Norris は V8 のバグを UTF 文字列のデコードを検証している最中にピンポイントで発見しました。これは Node のバッファをUTF文字列に変換する時に、プロセスをクラッシュさせる可能性があります。セキュリティ上の懸念としてはアプリケーションの外から Node のプロセスに対して大量のデータを送った時に発生します。この仕組みはユーザーがこっそり特殊に作成した入力データを送りつけることでアプリケーションをクラッシュさせることができるという事を意味します。ほとんどのネットワークやファイル操作が影響を受けます。多くのユーザーランドで使われているバッファからUTF8文字列への変換も同様にこれに影響を受けます。 HTTP(S) ヘッダーのパースは脆弱性ではありません。なぜなら Node ではこのデータを UTF8 に変換しないからです。これは不幸中の幸いです。 HTTP(S) が脅威にさらされる危険性を少しだけ制限できたからです。しかし HTTP(S) がヘッダーのパース以外にもたくさんのことをやっているというのは明らかです。様々なTLSの終端やフォワードプロキシと一緒に使用した場合にもしかしたら脆弱性は軽減されるかもしれませんが、我々はそれを提示するのに十分な情報をまだ持っていません。


<!--
The initial ETA was midday PDT. Unfortunately, the patch wasn’t quite ready and there was an extended test and verification process for V8, io.js and Node.js during the day. The builds also take some time on top of that, hence the delay. Fedor Indutny created the fix, Ben Noordhuis, Trevor Norris, Julien Gilli, Rod Vagg, Michael Dawson and Jeremiah Senkpiel all worked very hard to make this land successfully.
-->

最初はもう少し早くパッチを提供する予定でしたが、不幸なことに、初期のパッチはまだ十分ではありませんでした。追加のテストと V8, io.js と Node.jsの検証プロセスを経る必要がありました。 少し遅れましたが、このページのトップにビルドを追加することができました。 Fedor Indutny が修正パッチを作成し、 Ben Noordhuis, Trevor Norris, Julien Gilli, Rod Vagg, Michael Dawson そして Jeremiah Sankpiel がこのパッチをビルドするのに多くの労力を尽くし、成功させました。
