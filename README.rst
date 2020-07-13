下記はfolk元のREADME.rstを日本語訳したものです。正確な記述は本家リポジトリをご参照ください。

SkyWaterオープンソースPDK
========================

.. image:: https://img.shields.io/github/license/google/skywater-pdk
   :alt: GitHub license - Apache 2.0
   :target: https://github.com/google/skywater-pdk

.. image:: https://travis-ci.org/google/skywater-pdk.svg?branch=master
   :alt: Travis Badge - https://travis-ci.org/google/skywater-pdk
   :target: https://travis-ci.org/google/skywater-pdk

.. image:: https://readthedocs.org/projects/skywater-pdk/badge/?version=latest&style=flat
   :alt: ReadTheDocs Badge - https://skywater-pdk.rtfd.io
   :target: https://skywater-pdk.rtfd.io

.. image:: https://img.shields.io/github/v/tag/google/skywater-pdk?include_prereleases&sort=semver
   :alt: Latest GitHub tag (including pre-releases)
   :target: https://gitHub.com/google/skywater-pdk/commit/

.. image:: https://img.shields.io/github/commits-since/google/skywater-pdk/v0.0.0
   :alt: GitHub commits since latest release (v0.0.0)
   :target: https://gitHub.com/google/skywater-pdk/commit/

SkyWaterオープンソースPDKは、GoogleとSkyWater Technology Foundryの共同企画であり、完全オープンソースの `Process Design Kit <https://en.wikipedia.org/wiki/Process_design_kit>`_ とその関連リソースを提供しています。これらを用いることで、SkyWaterの施設で製造可能なチップ設計データを作成することができます。

2020年5月の時点で、このリポジトリはSKY130プロセスノードをターゲットにしています。 SKY130プロセスノードの成功次第では、将来的に、より高度なテクノロジノードが利用可能となるかもしれません。 

SkyWaterオープンソースPDKのドキュメントはこちらです <https://skywater-pdk.rtfd.io>。

.. image:: docs/_static/skywater-pdk-logo.png
   :alt: Google + SkyWater Logo Image
   :align: center
   :target: https://github.com/google/skywater-pdk
   :width: 80%

.. |current-status| replace:: **実験的プレビュー(Experimental Preview)**

.. include:: common.inc

現在の状態 -- |current-status|
==================================

.. current_status_text

*注意*
   GoogleとSkyWaterは現在、現在のコンテンツを **実験的プレビュー(Experimental Preview)**/**アルファリリース(alpha release)** として扱っています。このオープンソースリリースの元となったSKY130プロセスノードとPDKは、多くの商用チップ設計に利用されています。しかしこのオープンソースPDKについては、現時点では製品設計への利用を意図したものではありません。テストチップや初期設計検証には利用可能と思われます（ただし、保証はされません）。

Google、SkyWater、およびパートナー企業は、現在内部検証とテスト設計をおこなっており、これらの結果については公開を予定しています。製品設計に向けた準備ができ次第、製品バージョンのタグが付けられます。バージョン番号の詳細については、"`Versioning Information <docs/versioning.rst>`_"を参照してください。 PDKの今後の新しいリリースやその他の重要なニュースについて通知を受け取るには、`skywater-pdk-announce メーリングリスト <https://groups.google.com/forum/#!forum/skywater-pdk-announce>`_
[`参加用リンク <https://groups.google.com/forum/#!forum/skywater-pdk-announce/join>`_]へ参加してください。

既知の問題の詳細については、`Known Issues <docs/known_issues.rst>`_ セクションと、 `SkyWater PDK GitHub issue list <https://github.com/google/skywater-pdk/issues>`_ を参照してください。

SKY130プロセスノード
===================

SKY130は、当初サイプレスセミコンダクタによって内部的に開発され、その後SkyWaterへと渡ったのち外部から利用可能になりました。成熟した180nm-130nmのハイブリッドテクノロジとなっています。 SkyWaterとGoogleのコラボレーションにより、誰もがこのテクノロジを利用可能になりました！

SKY130プロセスノードのテクノロジスタックは、下記のような要素から構成されます。

* 内部電圧 1.8V、I/O電圧 5.0V (2.5Vで動作可能)
* 1層ローカルインタコネクト
* 5層メタル配線
* インダクタ
* 高抵抗ポリシリコン抵抗
* MIMキャパシタ（オプション）
* SONOSセル
* 10V電源をサポート
* 高耐圧拡張ドレインNMOS, PMOS

`SKY130プロセスノード`_ は、非常に柔軟であり、標準で多くの *オプション* 機能（ローカルインタコネクト、SONOSセル、MIMキャパシタ等々）を含みます。これにより設計者は **広い範囲** の柔軟な設計選択が可能になります。必要とするものが `SKY130プロセスノード`_ に含まれる標準の機能を超える場合は、 `SkyWaterへの問い合わせ`_ を検討してみてください。 `Nb, Ge, V2O5, カーボンナノチューブといった特殊素材の追加 <https://www.skywatertechnology.com/technology/>`_ に見られるように、プロセスカスタマイズを専門としています。 GoogleとSkyWaterは、 `SkyWaterオープンソースPDK`_ および `SKY130プロセスノード`_ へと追加する新たなオプションを模索し、従来の設計にまつわる問題に対して革新的なソリューションを提供可能にします。

130nmプロセスノードの典型的な利用例
-------------------------------------

`130nmプロセス <https://en.wikichip.org/wiki/130_nm_lithography_process>`_ は2001年から2002年にかけて最初に商用化され、現在は主に研究、小型マイクロコントローラ開発、およびIoTデバイスのようなミックスドシグナルチップの開発に使用されています。最新のGoogleドキュメント <https://j.mp/si130nm> は、研究者や、営利団体、その他のグループが同様の **サイズ** のプロセスノードで行った事例から **雰囲気(原文ではinspiration)** を提供するために作成されています。製造プロセスや材料が異なるため、 `130nmプロセス設計の雰囲気ドキュメント <https://j.mp/si130nm>` に見られるのと全く同じ結果が `SKY130プロセスノード`_ でも再現できるとは限らないことに注意してください。

PDKの内容
============

SkyWaterオープンソースPDKは下記のような内容を含みます。

* SKY130プロセスノードで製造可能なデバイスを作成するための設計ルールに関するドキュメント。
* 複数のオープンソースおよびプロプライエタリな設計フローに向けたEDAツールサポートファイル。
* アナログ回路設計のためのプリミティブセルライブラリとモデル。
* **複数の** 標準デジタルセルライブラリ。
* **複数の** PDK使用例（以下を参照）。

詳細については `PDK Contents section of the SkyWater SKY130 PDK <https://skywater-pdk.rtfd.io>`_ を参照してください。

SkyWaterオープンソースPDKを使ってみる
==================================

SkyWaterオープンソースPDKは、さまざまなタイプのASIC作成を可能にするため、複数のツールと設計フローでのPDK使用例に関するドキュメントを含んでいます。

* `[TODO #11] <https://github.com/google/skywater-pdk/issues/11>`_ - `デジタル回路設計例 <https://skywater-pdk.rtfd.io>`_.
* `[TODO #14] <https://github.com/google/skywater-pdk/issues/14>`_ - `OpenROAD ASICツールフローによるRISC-V SoCの設計例 <https://skywater-pdk.rtfd.io>`_.
* `[TODO #12] <https://github.com/google/skywater-pdk/issues/12>`_ - `アナログ回路設計例 <https://skywater-pdk.rtfd.io>`_.
* `[TODO #13] <https://github.com/google/skywater-pdk/issues/13>`_ - `アナログ回路ジェネレータの活用例 <https://skywater-pdk.rtfd.io>`_ `FASoC <https://fasoc.engin.umich.edu/>`_ や `Berkeley Analog Generator (BAG) <https://github.com/bluecheetah/bag>`_.

私たちは、新たなツールや設計フローにおけるPDK使用例を楽しみにしています。追加を行う方法については、 `Contributing file <docs/contributing.rst>`_ を参照してください。

サポート
=======

多くのオープンソースプロジェクトと同様に、SkyWaterオープンソースPDKでサポートを受ける方法は複数あります。

SkyWaterは、チップ設計からパッケージングおよびテストまでのサポートを提供できるように、マーケットパートナーエコシステムを作成しました。 ASIC開発プロセスにおいて追加のサポートを受けることに興味がある場合は、下の　`SkyWaterへの問い合わせ`_　セクションの情報を使用してSkyWaterにお問い合わせください。

`ユーザメーリングリスト <https://groups.google.com/forum/#!forum/skywater-pdk-users>`_ [`参加リンク <https://groups.google.com/forum/#!forum/skywater-pdk-users/join>`_] を利用することで、ユーザ同士が相互にサポートを提供できます。

Googleは、SkyWaterオープンソースPDKを使用するためのサポートを提供せず、このリポジトリを「現状有姿」で配布します。明示の有無に関わらず、いかなる保証も規約もありません。規約の全文については、 license_ セクションを参照してください。

SkyWater Technology Foundryについて
=================================

SkyWater is a solely U.S.-based and U.S.-owned, DoD-accredited, Trusted Foundry. Through its Technology Foundry model, SkyWater provides custom design and development services, design IP, and volume manufacturing for integrated circuits and micro devices. The Company’s world-class operations and unique processing capabilities enable mixed-signal CMOS, power, rad-hard and ROIC solutions. SkyWater’s Innovation Engineering Services empower development of superconducting and 3D ICs, along with carbon nanotube, photonic and MEMS devices. SkyWater serves customers in growing markets such as aerospace & defense, automotive, cloud & computing, consumer, industrial, IoT and medical. For more information, please visit: www.skywatertechnology.com/.

SkyWater is building from a long heritage in the microelectronics industry. The SkyWater facility was originally established by Minnesota based Control Data Corporation (CDC) in the 1980s. The CDC fab was acquired by Cypress Semiconductor in 1991. During the Cypress era, the facility was expanded and upgraded multiple times, keeping pace with Moore's Law into the late 2000s and was known for being a US-based production facility that was competitive with Asian-based fabs. SkyWater spun-off from Cypress in 2017 with private equity backing from Minnesota based Oxbow Industries.

SkyWaterへの問い合わせ
-------------------
SKY130やその他のテクノロジについての詳細な情報の問い合わせに関しては <swfoundry@skywatertechnology.com> へのメールや、 `Webフォームからの投稿 <https://www.skywatertechnology.com/contact/>`_ が利用可能です。


License
=======

The SkyWater Open Source PDK is released under the `Apache 2.0 license <https://github.com/google/skywater-pdk/blob/master/LICENSE>`_.

The copyright details (which should also be found at the top of every file) are;

::

   Copyright 2020 SkyWater PDK Authors

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.

