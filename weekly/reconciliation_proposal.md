# 和解プロポーザル

[iojs/io.js#978](https://github.com/iojs/io.js/issues/978) で議論されている [mikeal](https://github.com/mikeal) の和解プロポーザルを翻訳したものです。

---

<!--
A lot of questions have been coming our way about what a merger of the node.js and io.js projects might look like. People in both projects want to know their work won't be thrown away and that we can preserve the positive aspects of each project.
-->

node.js と io.js のプロジェクトをどんな風に統合するのかに関して、たくさんの質問が寄せられている。両方のプロジェクトに関わっている人は自分たちのやっていることが無駄になるのではないか、各プロジェクトのプラスの側面を保存できるのかといったことを知りたがっている。

<!--
This is a draft and will be continually updated and edited based on input from the community. It is not an ultimatum to Joyent or The Node.js Foundation but rather a collaboration point for the io.js community to produce a proposal for merging.
-->

この文書はドラフトであり、コミュニティからの意見によって随時更新され、編集されていくようにするつもりだ。
この文書は Joyent や Node.js Foundation への最終意思ではなく、むしろ統合のための提案書をこちらから提供することで io.js コミュニティにとっての協力できるポイントを明らかにする目的だ。

<!--
This document uses the terms io.js and node.js to refer to those projects prior to a merge and Node to refer to a future merged project.
-->

この文書では統合するより前のお互いのプロジェクトを指すために io.js と node.js という単語を使い、統合されたプロジェクトに関しては <i>Node</i> という単語を使う。

<!--
While io.js is often used as a starting point this document treats a future project under the foundation as a new organism made from the merger of each project and not as an extension of only node.js or only io.js. The goal of the merger should be a project that is actually greater than the sum these parts.
-->

io.js は出発点と言われることがよくあるが、本ドキュメントではfoundation下に置かれる新プロジェクトを、node.js や io.js の延長としてだけでなく両プロジェクトの統合による新たな組織体として扱う。統合の最終目標はこれらのパーツを集めただけのものよりも大きいプロジェクトになるべきだと思う。

# Technical Governance

<!--
The Node.js Foundation would adopt, as it's *Technical Governance Structure* (which is distinct and seperate from the foundation governance structure), a very simple structure which would ensure the following:
-->

Node.js Foundation は *Technical Governance Structure* (foundation の運営組織からは切り離されており、独立している組織)を採用する。Technical Governance Structure はとてもシンプルで、下記の事を保証する:

<!--
- Decision making autonomy from the foundation and its board.
- Ownership of its own governance and voting structure.
-->

- foundation や board から自律して意思決定をすること
- 自身の運用の所有権と投票システムを持つ

<!--
Because foundation bylaws are quite difficult to change and the TC wishes to make continued iterative improvements to its structure it would be a mistake to bake the entire governance structure as it exists today in to the foundation bylaws.
-->

このような事を明記したのは、foundation の規定変更がかなり難しい事が挙げられているためだ。TC はその foundation の規定に対して、現在存在する全体の運用構造を壊し、間違いを見つけては繰り返しその組織構造を改善しようと望んできた。

<!--
As an initial agreed upon structure, beyond what is in the bylaws, the following documents would be adopted from io.js.
- GOVERNANCE.md (TC, Voting, etc.)
- CONTRIBUTING.md (Collaborator policy, CoC, DCO, etc.)
- WORKING_GROUPS.md
- ROADMAP.md
-->

初期の構造として、規定内にある、以下のドキュメントは io.js が採用したものである。
- [GOVERNANCE.md](https://github.com/iojs/io.js/blob/v1.x/GOVERNANCE.md)(TC, 投票システムなど.)
- [CONTRIBUTING.md](https://github.com/iojs/io.js/blob/v1.x/CONTRIBUTING.md)(コラボレーターポリシー、コーディング規約、開発者起源証明書など)
- [WORKING_GROUPS.md](https://github.com/iojs/io.js/blob/v1.x/WORKING_GROUPS.md)
- [ROADMAP.md](https://github.com/iojs/io.js/blob/v1.x/ROADMAP.md)

<!--
In addition to the definition of "collaborator" from CONTRIBUTING.md the list of existing collaborators to io.js would also transfer.
The following changes would be made to these documents prior adoption:
-->

[CONTRIBUTING.md](https://github.com/iojs/io.js/blob/v1.x/GOVERNANCE.md)に記述されている "collaborator" の項目にある、既存の io.js の collaborators のリストに下記のメンバーを加える。

<!--
Addition of TC members:
TJ Fontaine
Alexis Campailla
Julien Gilli
Addition of Collaborators:
James M Snell
Stephen Loomis
Michael Dawson
-->

- TC メンバーに追加:
  - TJ Fontaine
  - Alexis Campailla
  - Julien Gilli
- Collaboratorに追加:
  - James M Snell
  - Stephen Loomis
  - Michael Dawson

<!--
# Long Term Support
-->

# 長期サポート

<!--
High level ideas about LTS are addressed in the io.js roadmap but it lacks specifics because io.js has not yet produced a release that breaks compatibility with prior releases which would cause it to begin executing on this plan. The node.js project has an informal Long Term Support policy which is not formally documented but it does produce patch releases for prior versions so we can assume some policy does exist.
-->

長期サポートに関する高次元に抽象化されたアイデアは io.js roadmap の中で触れられているが、具体性には欠ける、なぜなら io.js はこれまでのリリースの中で互換性を壊すリリースをしていないからだ。node.js プロジェクトは公式なドキュメントには明記されていない、非公式な長期サポートポリシーを持っている。以前の古いバージョンのパッチリリースをし続ける、そのためのいくつかのポリシーを決めることとした。

## LTS WG (Long Term Support Working Group)

<!--
The following is a draft charter for the LTS WG which would be added to WORKING_GROUPS.md.
-->

以下の文章は 長期サポートワーキンググループ(以下 LTS WG)のためのドラフトの宣言である。LTS WG については [WORKING_GROUPS.md](https://github.com/iojs/io.js/blob/v1.x/WORKING_GROUPS.md) に記述されている。

<!--
The LTS WG is responsible for maintenance and releases of prior versions of Node.
-->

LTS WG はメンテナンスと Node の古いバージョンのリリースに責任を持つ。

<!--
Node produces patch releases of prior versions for as long as community members are willing to maintain them. The LTS WG is responsible for when it no longer has the contributions necessary to support a particular version.
-->

Node (node.js + io.js)は可能な限り長く、コミュニティのメンバーがメンテナンスを望むまで、昔のバージョンの patch リリースを生成することとする。特定のバージョンをサポートするためにコントリビュートをしなければならないわけではなく、LTS WG でその時まで責任をもつということだ。

<!--
The LTS WG's responsibilities are:
-->

LTS WGの責任範囲は:

<!--
- Authoring and backporting bug fixes, stability improvements, and other relevant changes to prior releases (not CURRENT or CANARY).
- Creation and maintenance of tools to help manage and automate backporting changes.
- Documentation and enforcement of policies to ensure the stability of patch releases.
- Initial Members would include
-->

- バグ修正を作成し、下位バージョンにバックポートすること、安定性を改善すること、さらに他の適した変更の前のリリースバージョンにも適用すること(現在のバージョンや Canary は除く)。
- 管理やバックポートへの変更を効率化し、自動化するためのツールの作成とメンテナンスを行うこと。
- 安定したパッチリリースを保証するためのポリシーの文書化、徹底を行うこと。
- 初期メンバーには下記の者を含む

*Michael Dawson*

<!--
Note that specifics around managing branches is left out of the
charter but is part of the responsibilities for the working group under the last
bullet point.
-->

ブランチの管理などの具体的な事はこの文書には含めないが最後の箇条書きに記述したメンバーの下で working group がその責任の一部を持つことに注意すること。

<!--
# Versions Merger
-->

# バージョンの統合

<!--
Because there is currently no overlap between io.js and node.js versions we can, and in fact must, consider all versions of both projects as now being versions of Node. If we did not we would unnecessarily break a large portion of the community that depends on these versions.
-->

io.js と node.js でオーバーラップ(重複)しているバージョン(v0.12.0やv1.1.0など)は存在せず、実際には両プロジェクトの全てのバージョンを合わせて Node のバージョンとして捉えることができる。もしバージョンをオーバーラップさせていたら、これらのバージョンに依存してコミュニティの巨大な部分を不必要に壊していただろう。

<!--
Prior Releases
-->

## これまでのリリースしたバージョンについて

<!--
The following versions are considered "prior releases" and are under the control of the LTS WG>
-->

以下のバージョンは "以前のリリース" として考慮し、 LTS WG の支配下で運用する >

- 0.8.x
- 0.10.x
- 0.12.x

<!--
It should be noted that while 1.0+ releases follow semver versions prior to 1.0 did not and it is at the discretion of the LTS WG whether or not they would like to take API additions in to 0.12.x and 0.10.x patch releases. However, backwards incompatible changes cannot be made to these releases in following with the existing policies of both node.js and io.js.
-->

1.0 より前のリリースは準拠していなかったが、1.0+ リリースからは semver バージョンに準拠すること。0.12.x や 0.10.x のパッチリリースで API 追加を行いたい場合は LTS WG の裁量のもとで行うこと。しかしながら、後方互換性を壊す変更は node.js や io.js の両方に存在するポリシーに準拠して、これらのリリース(0.8 - 0.12のバージョン)に対して変更させることはできないものとする。

<!--
Current Release
-->

## 現在のリリース

- 1.x

<!--
As it stands there are two CURRENT development lines: node.js 0.12.x and io.js 1.x. Development, in some form, will need to continue on both of these lines as different users depending on each line. The question then becomes "which line do we put in to LTS?"
-->

現時点では2つの CURRENT 開発ラインがある。すなわち、node.js 0.12.x と io.js 1.x である。これらの開発ラインには別々にユーザーが存在する、そのため、両方の開発ライン共に継続する必要があるだろう。そうすると、"どちらのラインを LTS (長期サポート) にいれるのか?"という質問が生まれるだろう。

<!--
In the last few months io.js has made huge gains in part due to the fact that it aligned its current stable line of development with that of its dependencies. That, along with a faster release cycle, has also brought many module authors in to core and so the ecosystem is beginning to also align its current stable development with that of core. This has ushered in a new era of collaboration between projects and the larger community which Node should continue.
-->

直近数ヶ月において、io.js は巨大な成果を得ている。現在の stable な開発ラインとその依存ライブラリの両方を同期させているという事実がこの巨大な成果につながっている。さらに高速なリリースサイクルのために、多くの npm モジュール作者達にコアの内部に関わってもらってきた。そしてさらにエコシステムがコアにあわせて現在の安定開発と同期し始めている。これは各種プロジェクトとさらに巨大なコミュニティ間の新しい時代のコラボレーションを築き始めている。Node (node.js + io.js) はこれを続けるべきだろう。

<!--
This does not, however, mean that 0.12.x is a "dead" line. Far from it, 0.12.x and 0.10.x are still in use by many users and it will be the work of the LTS WG to continue to ensure those users have a stable and supported platform.
-->

ただし、0.12.x は "死んだ" ということではない。それどころか、0.12.x や 0.10.x はたくさんのユーザーによって今でも使われているし、LTS WG の活動で 0.12.x や 0.10.x を使っているユーザーは安定してサポートされたプラットフォームを持つことが保証され続けるだろう。

<!--
Non-Versioned Releases
-->

## バージョン番号無しのリリース

<!--
CANARY ("next" V8 and any changes marked as major)
-->

CANARY ("次の" V8 といくつかの変更が major バージョンとして選択される)

<!--
Along with the current stable line of development there should be a future line. This line exists as a branch and non-versioned nightly builds for testing. It is a testing ground for changes to Node that would necessitate bumping its major version as well as for testing the CANARY version of V8.
-->

現在の安定版の開発に伴って、未来版の開発をするべきである。この開発ラインは一つの branch (おそらく master?)として存在し、バージョン番号なしの test 用の nightly builds としても存在している。これは、Node (node.js + io.js) への変更のためのテストの場である。Node には V8 の CANARY バージョンのテストをする必要があるだけではなく、そのメジャーバージョンに上げる事も必要とする可能性がある。

<!--
Just as we have done with current stable, the "next" line of Node development should align with that of its dependencies. This allows the project and its users to easily test for performance regressions and potentially breaking changes in those dependencies while active development is still occuring and long before they land in a stable version of Node.
-->

現在の安定版にともなって実施されている通り、"次の" Node の開発ラインもその依存ライブラリと同調するべきである。こうすることで、アクティブな開発が行われる事になり、Node の安定バージョンが変更されるよりずっと前から、CANARY を使うことで依存ライブラリのプロジェクトとそのライブラリのユーザーには簡単にパフォーマンスの劣化や後方互換性が壊れている事が確認できるようになる。

# Website

<!--
The nodejs.org website would transfer to the Website WG and become the responsibility of that working group. The website will be retooled similar to iojs.org (gulp builds) so that it can be localized by the various language communities from io.js.
-->

nodejs.org のウェブサイトは Website WG に移管され、Working group の責任範囲の一つになるだろう。また、io.jsの言語コミュニティによってウェブサイトをローカライズができるように、iojs.org (gulp で構築されたサイト)に似たものへと再構築する。

# Social Media

<!--
The social media accounts (Twitter, Facebook, etc) will transfer to the Evangelism WG.
-->

ソーシャルメディアのアカウント(Twitter, Facebook, など)は Evangelism WG に移管。

# Evangelism WG

<!--
This io.js WG will move to Node (pending a vote by the WG) and continue to produce weekly updates, social media engagement, etc, for the Node project.
-->

io.js の Evangelism WG から Node に移管する予定である(Evangelism WG によって 投票中)。毎週の更新を生成し、 ソーシャルメディアでの拡散等は Node プロジェクトのために行う。

# i18n

<!--
All io.js language community working groups (32 individual teams by last count) will vote to
move to the Node project where they would continue to be endpoints for community members to
collaborate with each other in their language of choice and produce localizations of project resources.
-->

全ての io.js ローカライズコミュニティ WG (直近で32個のチームがある)は Node Project に移管して良いかどうかを投票すること。
これらローカライズコミュニティはプロジェクトリソースのローカライズをして、それぞれの言語内でお互いに協調するためのコミュニティメンバーにとってのエンドポイントであり続けることになるだろう。

# Roadmap WG

<!--
This io.js WG will move to Node (pending a vote by the WG) and continue to draw in feedback
from users and draft roadmap materials for consideration by the TC.
-->

io.js の Roadmap WG は Node に移管する予定である(Roadmap WG によって 投票中)。さらにユーザーからのフィードバックを引き出し続ける予定である。また、roadmap のドラフトになる材料は TC によって検討される事になる。

# Streams WG

<!--
This io.js WG will move to Node (pending a vote by the WG) along with readable-stream and will continue to define and improve streams in Node.
-->

io.js の Streams WG はNode に移管する予定である(Streams WG によって 投票中)。readable-stream と一緒に Node の中で Streams の改善を継続する。

# Tracing WG

<!--
This io.js WG will move to Node (pending a vote by the WG) and continue to improve the transparency ofNode applications.
-->

io.js の Tracing WG は Node に移管する予定である(Tracing WG によって 投票中)。Node アプリケーションの透明性の改善を継続する。

# Build WG

<!--
This io.js WG will move to Node (pending a vote by the WG) and continue to maintain and improve the build infrastructure and produce Node builds.
-->

io.js の Build WG は Node に移管する予定である(Build WG によって 投票中)。Node のビルド生成とビルドのためのインフラの改善、メンテナンスを継続する。
