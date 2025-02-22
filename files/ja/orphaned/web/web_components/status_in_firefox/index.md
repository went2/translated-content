---
title: Firefox での Web Components のサポート状況
slug: orphaned/Web/Web_Components/Status_in_Firefox
tags:
  - API
  - Experimental
  - Firefox
  - Guide
  - Web Components
  - status
translation_of: Web/Web_Components/Status_in_Firefox
original_slug: Web/Web_Components/Status_in_Firefox
---
{{DefaultAPISidebar("Web Components")}}{{SeeCompatTable}}

[Web Components](/docs/Web/Web_Components) は、とても新しい技術で、ブラウザ実装者や Web 開発者が実際に利用した経験を集めて仕様を考案しています。実装状況は変化しやすく、次々と進化していきます。この記事は、Firefox や Firefox OS で使用されている [Gecko](/docs/Mozilla/Gecko) での実装状況の一覧を示します。

<div class="blob instapaper_body" id="readme"><article class="markdown-body entry-content"><h2 id="ネイティブサポート">ネイティブサポート</h2><p>Firefox と Firefox OS では、以下の機能が実装されており、デフォルトで有効です:</p><ul><li>{{HTMLElement("template")}}</li></ul><h2 id="今後実装予定の機能">今後実装予定の機能</h2><ul><li>新しい同意に基づいた <a href="/docs/Web/Web_Components/Shadow_DOM">Shadow DOM</a> の実装は、2016 年 Q1 にリリース予定です。<a href="https://annevankesteren.nl/2015/07/shadow-dom-custom-elements-update">Anne</a> と <a href="https://hacks.mozilla.org/2015/06/the-state-of-web-components/">Wilson</a> のブログ投稿に詳細が記述されています。しかし、まだ仕様について <a href="https://github.com/w3c/webcomponents/labels/shadow-dom">多くの議論や課題</a> があり、すべてのブラウザへの実装は将来となるでしょう。</li><li><strong>Custom elements</strong> は、最初からやり直しで、ECMAScript 6 の文法を使用してリビルドする計画 (つまり、より少ないプロトタイプを基に作成) です。Apple の Ryosuke Niwa が、実装をいくつか具体化しています。<ul><li>古い文法は、しばらくの間、新しい文法と共に Chrome で動作するでしょう (例えば、{{domxref("Element.attachShadow()")}} に対して {{domxref("Element.createShadowRoot()")}})、しかし、Firefox ではネイティブでは動作しないでしょう。</li></ul></li><li>これらの問題について、<a href="https://github.com/w3c/WebPlatformWG/blob/gh-pages/meetings/29janWC.md">2016 年 1 月の会議</a> でベンダが議論するでしょう。</li></ul><h2 id="放棄された機能">放棄された機能</h2><p>これらの機能は、実装の検討がされており、実験的に実装されていたものもあります。今後は改良もされず、削除されるでしょう。</p><ul><li><strong>HTML imports</strong> の使用は、ES6 モジュールで開発者が何ができるかを確認することは、待って欲しいです (まだ実装されていません。{{bug(568953)}} をご覧ください)。Firefox から削除される予定の未完了の import の実装がありました。</li></ul><h2 id="Firefox_でポリフィルを使用する">Firefox でポリフィルを使用する</h2><p>Firefox でポリフィルを使用する際に考慮すべき注意事項があります:</p><ul><li><code>about:config</code> の <code>dom.webcomponents.enabled</code> 設定を <code>true</code> に変更して Firefox で Web Components を有効にすると、完全でないネイティブ実装が動き始め、ポリフィルが混乱する可能性があります。</li><li><a href="https://github.com/webcomponents/webcomponentsjs">webcomponents.js</a> ポリフィルを使用した Shadow DOM のポリフィルは、スタイルをカプセル化できません。そのため、スタイルは bleed through でしょう。ポリフィルを使用して構築されたサイトは、ネイティブの Shadow DOM を <strong>サポートした</strong> 環境と異なる見た目になることに注意してください。</li><li>Shadow DOM のポリフィルは、機能にフックするために DOM 要素のプロトタイプをリライトするため、とても動作が遅いです (ポリフィルというよりポリリプレイスです!)。</li><li>Shadow DOM を使用する必要がない場合、webcomponents.js ポリフィルの <a href="https://github.com/webcomponents/webcomponentsjs">webcomponents-lite.js</a> バージョンを使用することをお勧めします。このバージョンは、Shadow DOM を使用しないポリフィルです。</li></ul></article></div>
