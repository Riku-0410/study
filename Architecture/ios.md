# iOSアーキテクチャ選択

## MVC(Cocoa MVC)

- View
  - 表示、入出力
- Controller
  - 入力に基づくModelとViewの制御
- Model
  - データの保持、通信

ViewControllerがViewとControllerの役割を両方持つため肥大化しがち
Massive View Controllerとか呼ばれる

普通言われるMVCとはModelがデータの変更をViewに通知すると言う点で違う

## MVP

MVCと違い入力を受け付けるのがControllerではなくViewになるViewControllerはViewとして扱われる
- Supervising Controller
  - データバインディングによりViewがModelを監視し、データ更新があれば表示も更新する
  - データを加工せずに表示できるのでPresenterの負担を軽減できるがModelがViewのレイアウトに依存する
- Passive View
  - 必ずmodelとViewの間はPresenterが介すのでViewとModelが分離するがPresenterの負担増

## MVVM

ViewとViewModelをデータバインディング。MVPと違うのはMVPはデリゲートやインターフェイスで処理を移譲・更新処理を行うのに対して、MVVMではデータバインディングでViewとViewModelを紐づける

## クリーンアーキテクチャ

- GUIアーキテクチャ
  MVC,MVP,MVVMなどUIに関するロジック

クリーンアーキテクチャはUIに関するロジック(プレゼンテーション層)とシステムに関するロジック(ドメイン)を分離するのが目的
## 3階層システム
  - プレゼンテーション層(ユーザーインターフェース層)html,swift,
    ページの表示、ページ間の遷移、ユーザーが入力した内容をビジネスロジック層に受け渡す処理などを行う、
  - ビジネスロジック層(アプリケーション層)php,python,ruby
    プレゼンテーション層、データアクセス層がすること以外が全部ここ。
  - データアクセス層 sql
    CRUDのしょりをおこなう

  よくMVCとかMVVMとかは全部プレゼンテーション層の話
  参考:https://qiita.com/os1ma/items/7a229585ebdd8b7d86c2
      https://www.ibm.com/jp-ja/cloud/learn/three-tier-architecture
      https://qiita.com/navitime_tech/items/602d3286f23952ae0149#mvp-model-view-presenter