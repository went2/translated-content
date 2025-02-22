---
title: ハイブリッドアプローチ
slug: Web/Guide/Mobile/A_hybrid_approach
tags:
  - Mobile
  - Responsive Design
  - Web Development
translation_of: Web/Guide/Mobile/A_hybrid_approach
---
銀の弾丸はウェブ開発で見つけるのが難しいです — 状況に応じてさまざまなテクニックを最大限に活用する戦略に出くわす可能性が高くなります。 これは私たちの 3 つ目のアプローチです。 これは、[別々のサイト](/ja/docs/Web/Guide/Mobile/Separate_sites)と[レスポンシブデザイン](/ja/docs/Web_Development/Mobile/Responsive_design)のアプローチを組み合わせることでそれらの欠点のいくつかを回避することを目的としています。

このハイブリッドアプローチは、モバイル開発を[3 つの目標](/ja/docs/Web/Guide/Mobile/Mobile-friendliness)に分割し、次に各目標に個別に取り組むために利用可能な最善のテクニックを適用することを中心としています。 この記事では、ここでは例としてテクニックの潜在的な組み合わせの 1 つを紹介しますが、さまざまな状況ではさまざまな組み合わせが適切になります。 覚えておくべき最も重要な概念は、サーバー側とクライアント側のテクニックをあなたの状況に合うように組み合わせることができるということです。

## 長所

レスポンシブウェブデザインは素晴らしいです — 今のところそれはさまざまな状況でレイアウトをできるだけ良く見せるために利用可能な最良のテクニックです。 モバイルとデスクトップのユースケースが十分に似ている場合、これはレイアウト変更のための間違いなく好ましい選択肢です。 ただし、サイトのコンテンツをユーザーのコンテキストに合うように変えるためにクライアント側のテクニックを使用するのは面倒です。

幸いなことに、ここではクライアント側のテクニックを使用することに技術的に制限されていません — もう 1 つの選択肢は、サーバー側のユーザーエージェント検出を使用してユーザーに正しいコンテンツを表示することです。 これにより、サーバー側でコンテンツを変えるという複雑さが保たれますが、それでも私たちのレイアウトはレスポンシブデザインの柔軟性と将来の備えから利益を得ることができます。

レイアウトではなくコンテンツ専用のユーザーエージェント検出を使用すると、コンテンツごとに 1 つの URL を設定して、コンテンツのレイアウトをユーザーのブラウザーに合わせることもできます。 これは一般的に[良いこと](http://www.w3.org/TR/mobile-bp/#OneWeb)（英語）だと考えられています。 まったく異なる 2 つのサイトを管理するのではなく、ユーザーが気になるコンテンツのページに転送するだけです。 そしてデザインはレスポンシブなので、各ページはユーザーの画面上で可能な限り見栄えがよいことがわかります。

また、サーバー側のテクニックを取り入れることで、レスポンシブデザインのパフォーマンスの問題に対処することもできます。 例えば、レスポンシブウェブデザインに関してよく批判されている点は、フル解像度の画像が、常に縮小された画像を表示する携帯電話を含むすべてのデバイスに送信されることです。 この問題に対処するためのそのような[テクニックの 1 つ](http://wurfl.sourceforge.net/utilities/imageserver.php)（リンク切れ）は、[WURFL](http://wurfl.sourceforge.net/ "WURFL device capability library") デバイス能力ライブラリと一緒にサーバー側のユーザーエージェント検出を使用して、ユーザーのデバイス用に適切なサイズの画像を送信することです。 これをサービスとして提供する[さまざま](http://imgble.com/)な[製品](http://www.sencha.com/products/io/)（英語）も登場しています。 もちろん、このテクニックには、ユーザーエージェント検出に関連したすべての欠点があります。 それでもうまくいかなくても、[fluid images](http://unstoppablerobotninja.com/entry/fluid-images/ "Fluid Images")（利用可能なスペースに応じて拡大縮小する柔軟な画像）を使用するよりもパフォーマンスに関しては悪くありません。

上記のテクニックを組み合わせることで、純粋な別々のサイトよりも柔軟で、純粋なレスポンシブデザインよりも優れたパフォーマンスを持つ、モバイルウェブ開発戦略を得ることができます。

## 短所

混合アプローチの 1 つの欠点は、クライアント側とサーバー側の両方でコードパスの数が増加する可能性があることです。 これにより、他のアプローチよりも開発に時間がかかります。 しかし、適切に計画すれば、コードを保守可能な方法で整理することができます。 もう 1 つの欠点は、このアプローチはレスポンシブデザインに依存しているため、通常、レトロフィットとしてではなく、新しいプロジェクトまたは既存のフレキシブルレイアウトを持つプロジェクトに最も適していることです。 同様に、ユーザーエージェント検出を使用しているため、時間が経つにつれて検出ルールを更新する必要があります。

## この選択肢を選ぶのが正しいとき

サーバー側とクライアント側のテクニックを組み合わせることは、常に考慮に値するものです。 非常に多くの選択肢があるので、採用した個々のテクニックの長所と短所を比較検討する必要があります。

多くの場合、ハイブリッドアプローチの複雑さが増すことは必然ではありません。 例えば、ユーザーが実際に使用しているデバイスに基づいてコンテンツを調整する必要すらないかもしれません — ブラウザーに機能があるかどうかを知るだけで十分な場合があります。 これは、[Modernizr](http://www.modernizr.com/docs/#s2 "Features Detected by Modernizr") の JavaScript 機能検出または [Detect It](https://github.com/rafrex/detect-it "Detect if a device is mouseOnly, touchOnly, or hybrid") を使用して、クライアント側で識別できる可能性があるものです。 実際に自分のコンテンツを調整しようとしている軸を掘り下げて自問するのは害になることはありません。

サーバー側のテクニックをレスポンシブデザインに取り入れることについて説明しましたが、モバイルとデスクトップのユースケースが大きく異なる場合は、ハイブリッドアプローチを使用する方法もあります。 例えば、メディアクエリとフレキシブルレイアウトを組み合わせることで、別々のサイトのデザインの柔軟性を高めることができます。 あなたもモバイルサイトのデザインをタブレットにも快適に拡張するのに十分適応可能にすることができるかもしれません。

## 例

![webowonder_mobile_and_desktop-300x225.jpg](webowonder_mobile_and_desktop-300x225.jpg)Mozilla の Web O Wonder デモサイトでは、ハイブリッドアプローチの基本バージョンを試してみましたが、良い結果が得られました。 レスポンシブウェブデザインのいくつかの要素を使用して、サイトにモバイルレイアウトを設定したり、ユーザーエージェント検出を使用してモバイル向けの動画を提供したり、ユーザーが携帯電話の場合はデモを並べ替えたりします。 [github](https://github.com/mozilla/webowonder/ "Mozilla's Web O' Wonder Source Code") でソースコードをチェックしてください。

私達はまたこのアプローチを含むもっと多くの開発をすぐにやることができます！ 実際、次のようなメインの Mozilla サイトへの 1 つの可能性のある道筋は、上の「長所」セクションに概説されています。

- ユーザーエージェント検出を使用して、訪問者を自分のデバイス用の Firefox バージョンのランディングページに転送します。
- サイト上のすべてのページは、レスポンシブデザインを念頭に置いて作成されており、さまざまな解像度で見栄えがよいはずです。
- 今後の計画では、ユーザーエージェントに基づいて画像を提供することを検討します。

物事はまだ開発段階にあるので、これまでのところモバイルについてはそれほど多くはありませんが、新しい mozilla.org が [github](https://github.com/mozilla/bedrock "New Mozilla.com Source Code") で成長するのをいつでも見ることができます。 私たちの進歩についての最新情報は [Mozilla Webdev](http://blog.mozilla.com/webdev/) ブログを購読してください。

## まとめ

万能の解決策はありません。 モバイルユーザーのコンテンツやユーザーフローを大幅に変更したいウェブアプリケーションは、おそらく別のモバイルサイトに移動する必要があります。 モバイルユーザー向けにコンテンツを変更する必要がないコンテンツ指向のページは、レスポンシブデザインで満足するでしょう。 モバイルユーザー向けのサイトのメッセージを少し変える必要があるが、レスポンシブデザインのメリットを享受したい場合は、ハイブリッドアプローチが最善の策です。 このような決定は、モバイルウェブ開発の中核をなすものです。 達成したいことについて具体的に考え、妥協点を認識しながら実用的なアプローチを選択することです。 がんばろう！

## モバイルウェブ開発への取り組み

モバイルプラットフォーム向けに開発するための背景やその他のアプローチについては、以下の記事を参照してください。

- [モバイルの親しみやすさとは？](/ja/docs/Web/Guide/Mobile/Mobile-friendliness)
- [別々のサイト](/ja/docs/Web/Guide/Mobile/Separate_sites)
- [レスポンシブデザイン](/ja/docs/Web_Development/Mobile/Responsive_design)

### 原本情報

この記事は、もともと 2011 年 6 月 27 日に Mozilla Webdev ブログで「[モバイルウェブ開発へのアプローチ 第 4 回 – ハイブリッドアプローチ](http://blog.mozilla.com/webdev/2011/06/27/approaches-to-mobile-web-development-part-4-%E2%80%93-a-hybrid-approach/)」として Jason Grlicky によって公開されました。（英語）
