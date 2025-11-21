# 🌈 Bluesky⇔Tokimeki 切り替え (bskyTokimeki) v7.8

このスクリプトは、**Bluesky (bsky.app)** と **Tokimeki (tokimeki.blue)** のURLを、**ボタン、キーボードショートカット、右クリックメニュー**で瞬時に切り替えるUserScriptです。

* **「bsky.app/profile/neon-ai.art」** が表示されているとき、**「tokimeki.blue/profile/neon-ai.art」** へ切り替えます。
* 逆に、TokimekiのページからはBlueskyの同じページへ戻る、**相互切り替え**が可能です。

---

## 🚀 インストール方法

UserScriptのインストールは、**GreasyFork**から行うのが**最も簡単**です。

**[✨ GreasyForkでインストールする ✨](https://greasyfork.org/ja/scripts/545465)**

### 拡張機能の準備

このスクリプトを使うには、UserScript管理のための拡張機能が必要です。

* **Tampermonkey**: 
    * [Chrome ウェブストア](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
    * [Firefox Add-ons](https://addons.mozilla.org/ja/firefox/addon/tampermonkey/)
* **Violentmonkey**: 
    * [Chrome ウェブストア](https://chrome.google.com/webstore/detail/violent-monkey/jinjaccalgkegednnccohejagnlnfdag)
    * [Firefox Add-ons](https://addons.mozilla.org/ja/firefox/addon/violentmonkey/)

---

## 🎀 機能紹介

このスクリプトは、**利用者の操作環境**に合わせて、**3つのクールな操作方法**を提供します。

* **切り替えボタン**: ページ上に表示されるボタンをワンクリックで切り替えできます。
    * ボタンのON/OFF、位置は設定画面から変更可能です。
    * 設定はTampermonkeyのアイコンか右クリックメニューにあります
* **キーボードショートカット**: 設定したショートカットキー（デフォルトは`Ctrl+Shift+H`）で、すぐに切り替えできます。
* **右クリックメニュー**: Tampermonkeyなどの拡張機能のメニューからも切り替えを実行できます。

---

## 💻 技術的な特徴 (SPAをハックする高度なDOM操作よ！✨)

このスクリプトの価値は、単なるURL切り替えではなく、**BlueskyやTokimekiといった複雑なSPA（シングルページアプリケーション）** において、**現在開いているタブの状態**を正確に維持したまま移動させる、**高度なロジック**にあります。

* **🎨 Bluesky側の「アクティブタブ」検出の妙技**:
    * Blueskyのプロフィールページで**現在選択中のタブ**（メディア、いいね等）を示す**青い下線（スタイル属性）を直接解析**することで、**DOMにIDがない難解な部分**でも、ユーザーがどのタブを見ているかを正確に判別します。
* **🖱️ Tokimeki側の二段階自動ナビゲーション**:
    * Tokimekiへ移動後、**`MutationObserver`**という監視機能を使って、**メインのサイドバーボタン**の出現を待ち（Step 1）、さらにクリック後に**動的に出現するネストされたタブ**（フィード、リスト等）を**再度監視**してクリック（Step 2）することで、**目的のタブまで確実に自動遷移**させます。
* **🧹 URLクリーンアップ**:
    * 自動タブ切り替え完了後、URLに残っている**遷移用のパラメータ（`?switchTab=...`）を即座に削除**（`history.replaceState`）し、URLを清潔な状態に戻します。これは**ユーザー体験を損なわないための知的でクールな配慮**です。

---

## 🛡️ ライセンスについて

このスクリプトは、ねおんが著作権を保有しています。

* **ライセンス**: **CC BY-NC 4.0** です。（**LICENSEファイル**をご参照ください。）

* **お願い**: 個人での利用や改変、非営利の範囲内での再配布はOKです。でも、**商用目的での利用はご遠慮ください**。

※ ご利用は自己責任でお願いします。（悪用できるようなものではないですが、念のため！）
