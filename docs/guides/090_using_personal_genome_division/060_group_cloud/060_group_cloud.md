---
id: group_cloud
title: DDBJ グループクラウド
---


DDBJ グループクラウドは、個人ゲノムデータを含みアクセス制限を必要とするデータを、研究グループ内で共有するためのサービスです。

- OwnCloud または MinIO を使って、データのアクセス権を細かく設定できます。
  - [OwnCloud 公式ページ](https://owncloud.com/)
  - [MinIO 公式ページ](https://min.io/)

![](group_cloud_fig.png)

- リモートデスクトップと組み合わせることにより、データをユーザのクライアント計算機にダウンロードすることを禁止できます。（申請時提出する利用計画表に、利用したい計算機リソース量を書いて下さい。）
    - リモートデスクトップ環境はユーザの計算機(Windows や Mac など)の Web ブラウザの中から利用します。
    - Linux デスクトップ内でデータ共有ミドルウェア（画面右下のウインドウに表示されている MinIO または OwnCloud）にアクセスすることでデータ共有も可能となります。データ共有ミドルウェアからユーザの手元の計算機へのデータダウンロードが可能な構成とすることも不可能な構成にすることも環境の初期設定により指定できます。
    - 解析のための計算は Linux デスクトップ上の GUI 環境を用いて実行できます。
    - 計算ノードを追加することでリモートデスクトップ内で動作している Linux 環境のターミナルエミュレータからジョブスケジューラを用いてジョブを実行することが出来ます。



## アカウント申請の方法 {#how-to-apply-for-use}

 サービス利用の際は、利用規程および利用規程別表（料金表）ご確認いただき、[利用計画表](/application/resource_extension)をダウンロードし必要事項を記入の上、![](sc-helpdesk.png)までメールにてお送りください。利用目的を審査の上、課金サービス利用許可の案内をお送りします。遺伝研スパコンの混雑状況によってはご利用できない場合がありますのでご了承願います。


- [スパコン(2025)利用規程および利用規程別表](/application/terms_and_policies/terms_of_use_2025/)

## 利用料金 {#usage-fees}

データ共有のためのストレージの使用料金の他に、基本料金 350 万円が別途かかります。（ユーザ管理、セキュリティー監視などのため）


利用規程別表（料金表）から抜粋。


![](ddbj_group_cloud_price_table.png)


リモートデスクトップや計算ノードを使用する場合はノードの料金がかかります。

詳細は利用規程別表（料金表）をご確認下さい。


- [スパコン(2025)利用規程別表](/application/terms_and_policies/terms_of_use_2025/#price-list-revised-on-2025)
