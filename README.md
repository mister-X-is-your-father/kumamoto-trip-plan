# 熊本子連れ旅行プラン

子ども連れで楽しめる熊本の観光スポットとアクティビティをまとめたリポジトリです。

## 📁 ファイル構成

### メインコンテンツ
- **熊本子連れ旅行プラン.md** - 全21箇所の観光スポット詳細情報
- **map.html** - インタラクティブマップ（LocalStorage版）
- **map-firebase.html** - インタラクティブマップ（Firebase版）✨推奨

### セットアップガイド
- **FIREBASE_SETUP.md** - Firebase初期設定の詳細手順

---

## 🗺️ マップの使い方

### オプション1: LocalStorage版（map.html）

**特徴:**
- ブラウザのLocalStorageでデータ保存
- サーバー不要、すぐ使える
- ⚠️ PC間でデータ共有不可

**使い方:**
1. map.htmlをブラウザで開く
2. レーティングを入力
3. データはそのブラウザにのみ保存される

---

### オプション2: Firebase版（map-firebase.html）✨推奨

**特徴:**
- ✅ リアルタイム同期
- ✅ PC・デバイス間でデータ共有
- ✅ 松下さん・森田さんが同時にアクセス可能
- ✅ データが自動的に同期される

**セットアップ手順:**

#### ステップ1: Firebaseプロジェクト作成
`FIREBASE_SETUP.md` の手順に従ってFirebaseプロジェクトを作成してください（5分程度）

#### ステップ2: 設定情報の取得
Firebaseコンソールから以下のような設定情報をコピー：

```javascript
const firebaseConfig = {
  apiKey: "AIza...",
  authDomain: "your-project.firebaseapp.com",
  projectId: "your-project",
  storageBucket: "your-project.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123"
};
```

#### ステップ3: map-firebase.htmlに設定を入力
`map-firebase.html` の26行目付近にある設定部分を置き換え：

```javascript
// ⚠️ Firebase設定 - ここに設定情報を入力してください
const firebaseConfig = {
    apiKey: "YOUR_API_KEY_HERE",  // ← ここを変更
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",  // ← ここを変更
    projectId: "YOUR_PROJECT_ID",  // ← ここを変更
    // ... 以下同様
};
```

#### ステップ4: 使用開始
1. 設定後のmap-firebase.htmlをブラウザで開く
2. 「Firebase接続成功」メッセージが表示されればOK！
3. レーティングを入力
4. 他のデバイスでも同じファイルを開けば自動的に同期される

---

## ⭐ レーティング機能

### 評価項目（各5段階）
- **子ども喜び度** - 子どもがどれくらい楽しめるか
- **行きやすさ** - アクセスの良さ
- **ここならでは** - その場所独自の魅力

### 評価者
- **松下** - ユーザー1
- **森田** - ユーザー2

### 除外機能
- チェックボックスで特定のスポットを除外
- 除外したスポットはグレーアウト（カードは残る）
- 地図上のマーカーは非表示

---

## 🚀 GitHub Pagesでの公開

### 現在のURL
- **マップ（LocalStorage版）:** https://mister-x-is-your-father.github.io/kumamoto-trip-plan/map.html
- **マップ（Firebase版）:** https://mister-x-is-your-father.github.io/kumamoto-trip-plan/map-firebase.html

### 注意
Firebase版を使用する場合、`map-firebase.html`に設定を入力してからコミット・プッシュする必要があります。

---

## 📝 スポット一覧

### メインスポット（6箇所）
1. グリーンランド（遊園地）
2. 阿蘇ファームランド（体験型テーマパーク）
3. 熊本市動植物園
4. ひごっこジャングル（公園）
5. 阿蘇ネイチャーランド（アウトドア）
6. 熊本城

### その他のおすすめスポット（15箇所）
7. ONE PIECE 麦わらの一味像めぐり
8. 黒川温泉 湯あかり
9. 高森田楽保存会
10. 崎津教会（世界遺産）
11. 御船町恐竜博物館
12. 草千里ヶ浜
13. 阿蘇ミルク牧場
14. 阿蘇ミルクロード
15. 天草市立御所浦恐竜の島博物館
16. 海中水族館シードーナツ
17. 道の駅 有明リップルランド
18. 山鹿灯籠民芸館
19. 肥後民家村
20. にしきひみつ基地ミュージアム
21. 釜田醸造所

---

## 💡 よくある質問

### Q: Firebase版とLocalStorage版、どちらを使うべき？
A: **Firebase版を推奨**します。PC間でデータを共有したい場合は必須です。

### Q: Firebase版の設定は難しい？
A: 5分程度で完了します。`FIREBASE_SETUP.md`に詳しい手順があります。

### Q: 料金はかかる？
A: Firebaseの無料枠（Sparkプラン）で十分です。小規模利用なら完全無料。

### Q: データは安全？
A: 現在の設定では誰でもアクセス可能です。より厳密なセキュリティが必要な場合は、Firebase Authenticationを追加できます。

### Q: LocalStorage版からFirebase版へデータ移行できる？
A: 手動で移行可能ですが、新規で入力することを推奨します。

---

## 🛠️ 技術スタック

- **フロントエンド:** HTML, CSS, JavaScript
- **マップ:** Google Maps JavaScript API
- **データベース:** Firebase Firestore (Firebase版のみ)
- **ホスティング:** GitHub Pages

---

## 📜 ライセンス

MIT License

---

## 👥 作成者

生成: Claude Code
プロジェクト: 熊本子連れ旅行プラン
