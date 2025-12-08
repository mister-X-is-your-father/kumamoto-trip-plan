# Firebase セットアップ手順

## 1. Firebaseプロジェクト作成

1. **Firebase Console** にアクセス
   - URL: https://console.firebase.google.com/
   - Googleアカウントでログイン

2. **「プロジェクトを追加」** をクリック

3. プロジェクト名を入力
   - 例: `kumamoto-trip-plan`
   - 「続行」をクリック

4. Google Analyticsの設定（任意）
   - 「このプロジェクトでGoogle Analyticsを有効にする」は**オフでOK**
   - 「プロジェクトを作成」をクリック

5. プロジェクト作成完了を待つ（数秒）

---

## 2. Firestoreデータベース作成

1. 左メニューから **「Firestore Database」** を選択

2. **「データベースの作成」** をクリック

3. セキュリティルールの設定
   - **「テストモードで開始」** を選択
   - 「次へ」をクリック

4. ロケーションの選択
   - **「asia-northeast1 (Tokyo)」** を選択
   - 「有効にする」をクリック

5. データベース作成完了を待つ

---

## 3. Webアプリの登録

1. プロジェクト概要画面に戻る

2. **「ウェブ」アイコン（</>）** をクリック

3. アプリのニックネーム入力
   - 例: `kumamoto-map`
   - 「アプリを登録」をクリック

4. **Firebase SDK** の設定コードが表示される
   - このコードは後で使います
   - 「コンソールに進む」をクリック

---

## 4. Firebase設定の取得

1. プロジェクト概要 > 「プロジェクトの設定」（⚙️アイコン）

2. 下にスクロールして **「マイアプリ」** セクションを確認

3. **Firebase SDK snippet** で **「構成」** を選択

4. 以下のような設定情報が表示されます：

```javascript
const firebaseConfig = {
  apiKey: "AIza...（長い文字列）",
  authDomain: "kumamoto-trip-plan.firebaseapp.com",
  projectId: "kumamoto-trip-plan",
  storageBucket: "kumamoto-trip-plan.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef1234567890"
};
```

5. **この設定情報をコピーして保存してください**

---

## 5. セキュリティルールの設定（本番用）

テストモードは30日間のみ有効です。本番運用する場合は以下のルールに変更：

1. Firestore Database > 「ルール」タブ

2. 以下のルールを設定：

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // ratingsコレクションは誰でも読み書き可能
    match /ratings/{document=**} {
      allow read, write: if true;
    }
    // exclusionsコレクションは誰でも読み書き可能
    match /exclusions/{document=**} {
      allow read, write: if true;
    }
  }
}
```

3. 「公開」をクリック

---

## 完了！

Firebase設定が完了しました。次のステップ：
- コピーした `firebaseConfig` をClaude Codeに提供してください
- map.htmlにFirebase統合コードを追加します

---

## トラブルシューティング

### Q: データベースが作成できない
A: Googleアカウントの2段階認証が必要な場合があります

### Q: 料金はかかりますか？
A: 無料枠（Sparkプラン）で十分です
- 読み取り: 50,000/日
- 書き込み: 20,000/日
- 小規模使用なら完全無料

### Q: セキュリティは大丈夫？
A: 現在の設定は誰でもアクセス可能です
- より厳密なセキュリティが必要な場合は認証機能を追加できます
