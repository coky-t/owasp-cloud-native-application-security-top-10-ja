---
layout: col-sidebar
title: OWASP クラウドネイティブアプリケーションセキュリティ Top 10
site_side: true
tags: cloud-native-application-security
level: 2
type: documentation
auto-migrated: 0
pitch: OWASP クラウドネイティブアプリケーションセキュリティ Top 10 ドキュメントの主な目標は、クラウドネイティブアプリケーションを安全に採用しようとしている組織に支援と教育を提供することです。このガイドではクラウドネイティブアプリケーションの最も顕著なセキュリティリスク、関連する課題、それらを克服する方法についての情報を提供します。
---
[![Follow on Twitter](https://img.shields.io/twitter/follow/owaspcloudnati1?label=Follow%20%40owaspcloudnati1&style=social)](https://twitter.com/owaspcloudnati1)
## 概要

**重要なお知らせ:** このプロジェクトは **非常に活発** であり、2022年4月に最終更新されました。現在、私たちは各カテゴリのドラフトを作成してくれる協力者を探しています。お手伝いいただけるようでしたら、お気軽にメールをお送りください。

クラウドネイティブテクノロジにより組織はパブリッククラウド、プライベートクラウド、ハイブリッドクラウドなどの最新のダイナミックな環境でスケーラブルなアプリケーションを構築して実行できます。コンテナ、サービスメッシュ、マイクロサービス、イミュータブルインフラストラクチャ、宣言型 API はこのアプローチの代表例です。クラウドネイティブアプリケーションはソフトウェアを設計し構築するための根本的に新しくエキサイティングなアプローチです。しかしその一方で、まったく新しいセキュリティ上の課題も発生します。たとえば、マイクロサービスモデルに移行すると、エンドツーエンドの可視化、監視、検出がより複雑になり実行が困難になります。
<br>
<br>
OWASP クラウドネイティブアプリケーションセキュリティ Top 10 ドキュメントの主な目標は、クラウドネイティブアプリケーションを安全に採用しようとしている組織に支援と教育を提供することです。このガイドではクラウドネイティブアプリケーションの最も顕著なセキュリティリスク、関連する課題、それらを克服する方法についての情報を提供します。

## リスクリスト (暫定版) - 現在レビュー中

OWASP クラウドネイティブ Top 10 リストは現在開発中です (2021年7月) 。フィードバックを収集する取り組みの一環として、以下に暫定リストを提示します。ご意見などございましたら、プロジェクトリーダーまでお気軽にご連絡ください。

#### [CNAS-1: 安全でないクラウド、コンテナ、オーケストレーションの構成][CNAS1:2022]
例:
 * パブリックオープンなクラウドストレージバケット
 * クラウドストレージバケットの不適切なパーミッション設定
 * root として実行しているコンテナ
 * ホストとリソース (ネットワークインタフェースなど) を共有しているコンテナ
 * 安全でない Infrastructure-as-Code (IaC) 構成
 * ...

#### [CNAS-2: インジェクションの欠陥 (アプリ層、クラウドイベント、クラウドサービス)][CNAS2:2022]
例:
 * SQL インジェクション
 * XXE
 * NoSQL インジェクション
 * OS コマンドインジェクション
 * サーバーレスイベントデータインジェクション
 * ...

#### [CNAS-3: 不適切な認証と認可][CNAS3:2022]
例:
 * マイクロサービスでの未認証 API アクセス
 * 過度に寛容なクラウド IAM ロール
 * オーケストレータノードの信頼ルールの欠如 (認可されていないホストがクラスタに参加しているなど)
 * 未認証オーケストレータコンソールアクセス
 * 未認可または過度に寛容なオーケストレータアクセス

#### [CNAS-4: CI/CD パイプラインとソフトウェアサプライチェーンの欠陥][CNAS4:2022]
例:
 * CI/CD パイプラインでの不十分な認証
 * 信頼できないイメージの使用
 * 古いイメージの使用
 * レジストリへの安全でない通信チャネル
 * 過度に寛容なレジストリアクセス
 * 単一環境を使用した、異なるレベルのセキュリティを必要とするプロジェクトの CI/CD タスクの実行
 * ...

#### [CNAS-5: 安全でないシークレットの保存][CNAS5:2022]
例:
 * 暗号化されずに保存されたオーケストレータシークレット
 * コンテナ内に暗号化されずに保存された API キーやパスワード
 * ハードコードされたアプリケーションシークレット
 * 暗号化が不十分なシークレット (廃止された暗号化方式の使用、暗号化の代わりにエンコーディングの使用など)
 * 機密情報を含むストレージのマウント
 * ...

#### [CNAS-6: 過度に寛容または安全でないネットワークポリシー][CNAS6:2022]
例:
 * 過度に寛容なポッド間通信
 * パブリックインターネットに公開されている内部マイクロサービス
 * ネットワークセグメントが未定義
 * 暗号化されていないエンドツーエンド通信
 * 監視およびブロックされていない未知または潜在的に悪意のあるドメインへのネットワークトラフィック
 * ...

#### [CNAS-7: 既知の脆弱性を持つコンポーネントの使用][CNAS7:2022]
例:
 * 脆弱性を持つサードパーティ製オープンソースパッケージ
 * 脆弱性を持つバージョンのアプリケーションコンポーネント
 * 既知の脆弱性を持つコンテナイメージの使用
 * ...

#### [CNAS-8: 不適切な資産管理][CNAS8:2022]
例:
 * ドキュメント化されていないマイクロサービスと API
 * 廃止され管理されていないクラウドリソース
 * ...

#### [CNAS-9: 不適切な 'コンピュート' リソースクォータ制限][CNAS9:2022]
Examples:
 * リソースにバインドされていないコンテナ
 * API に設定された過剰に寛容なリクエストクォータ
 * ...

#### [CNAS-10: 無効なログ記録と監視 (ランタイムアクティビティなど)][CNAS10:2022]
例:
 * コンテナやホストプロセスのアクティビティ監視がない
 * マイクロサービス間のネットワーク通信の監視がない
 * 重要なリソースの可用性を確保するためのリソース消費の監視がない
 * オーケストレーション構成プロパゲーションと古い構成の監視の欠如
 * ...

## 参加するには
セキュリティの専門家やプログラマでなくても参加できます。プロジェクトリーダーに連絡して参加してください。私たちはあらゆる種類の提案やコメントを歓迎します。参加できる方法は以下のとおりです。
 * 私たちは脆弱性有病率データを提供していただける組織や個人を積極積に募集しています
 * 翻訳作業 (後工程)
 * プロジェクトに参加してくださる個人や組織は謝辞ページに掲載されます。

[CNAS1:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x01_insecure_cco_config.md  
[CNAS2:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x02_inj_flaws.md
[CNAS3:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x03_improper_auth.md
[CNAS4:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x04_cicd_ssc_flaws.md
[CNAS5:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x05_insecure_secrets.md
[CNAS6:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x06_over_permissive_network.md
[CNAS7:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x07_vuln_components.md
[CNAS8:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x08_asset_mgmt.md
[CNAS9:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x09_compute_resources.md
[CNAS10:2022]: https://github.com/OWASP/www-project-cloud-native-application-security-top-10/blob/master/2022/en/src/0x0A_logging.md
