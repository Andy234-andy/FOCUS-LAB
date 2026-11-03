# FOCUS LAB

**A privacy-first, camera-assisted screen-attention signal tracker.**

🔗 **Live app:** https://focus-lab-github.vercel.app

FOCUS LAB analyzes the visible direction of your eyes and face while you work, then visualizes how often those signals remain close to a short calibration baseline.

> **Important:** This is not a direct measurement of concentration, comprehension, motivation, or mental state. Looking at a screen does not prove that someone is mentally focused, and looking away does not prove that they are distracted. Treat the result as a limited visual proxy—not a score of your ability.

## What it measures

- **Face detection rate:** how often a face is detected during the recent measurement window.
- **Screen-direction match:** how often estimated eye and head landmarks stay near the user's own calibration baseline.
- **Visual signal score:** the proportion of measurement frames where a face is detected and its eye/head signals match that baseline.
- **Separate self-check-ins:** a personal 1–5 rating, stored separately and never used to fabricate the camera score.
- **Session timeline and history:** recent estimates, session duration, and face-detection statistics.

The score stays blank until enough live camera observations exist. There is no default starting score such as 72 or 77.

## How to use

1. Open the [live app](https://focus-lab-github.vercel.app) in a modern browser over HTTPS.
2. Press **カメラで計測スタート** and grant camera permission.
3. Keep the camera at a comfortable position and look at the screen as you normally would during the 8-second calibration.
4. The session begins after calibration. Pause, resume, or finish whenever needed.
5. Optionally record your own 1–5 focus feeling. This is kept separate from the camera signal.

## Privacy

- Camera access starts only after the user presses the start button and grants browser permission.
- Video frames are processed locally in the browser with MediaPipe Face Landmarker.
- The app does not record, save, or upload camera frames.
- The microphone is not requested or used.
- Session summaries are stored in the browser's `localStorage`; clearing this site's browser storage removes them.
- The MediaPipe JavaScript package, WASM runtime, and model are downloaded from their respective CDNs/model hosting when needed. Live camera frames are not sent to those servers by this app.

## Limitations

This is a **visual screen-direction signal**, not an objective concentration test. It can be affected by camera placement, lighting, glasses, eye anatomy, calibration posture, and the user's activity. For example, someone can think deeply while looking away, read paper notes while focused, or look at a screen while daydreaming. The app cannot tell those situations apart.

Do not use this score to judge health, intelligence, learning ability, school performance, or another person.

## Technology

- HTML, CSS, and vanilla JavaScript
- [MediaPipe Face Landmarker for Web](https://developers.google.com/edge/mediapipe/solutions/vision/face_landmarker/web_js)
- Browser `getUserMedia` camera API
- Canvas chart rendering and `localStorage`

## Deployment

The repository's `main` branch is connected to Vercel. Commits to `main` are configured to trigger deployments.

- **Production:** https://focus-lab-github.vercel.app
- **Repository:** https://github.com/Andy234-andy/FOCUS-LAB

---

# 日本語

FOCUS LABは、カメラ映像から顔・目のランドマークを解析し、初期調整時と似た画面方向を保っていた割合を可視化するツールです。

## できること

- 顔が検出できた割合を表示
- 目と顔の向きが初期調整時に近かった割合を推定
- 画面方向サインの推移をグラフ化
- 本人の1〜5の自己評価を、カメラの数値とは別に記録
- セッションの結果をブラウザ内に保存

十分なカメラデータが集まるまではスコアを表示しません。初期値の72点・77点などを勝手に表示する仕組みはありません。

## 使い方

1. [公開サイト](https://focus-lab-github.vercel.app)をHTTPS対応ブラウザで開く。
2. 「カメラで計測スタート」を押し、ブラウザのカメラ利用を許可する。
3. 普段どおりの姿勢で画面を見ながら、8秒間の初期調整を行う。
4. 初期調整が終わると計測が始まる。
5. 必要に応じて一時停止・再開・終了を行う。

## プライバシー

- カメラはユーザーが計測開始を押し、ブラウザで許可した後にだけ動作する。
- 映像フレームはMediaPipeを使ってブラウザ内で解析する。
- 映像の録画・保存・サーバー送信はしない。
- マイクは要求せず、使用しない。
- セッションの集計値だけをブラウザの `localStorage` に保存する。
- 解析用ライブラリ・WASM・モデルはCDN等から読み込むが、ライブ映像を送信する処理はない。

## 大切な限界

この数値は**集中力そのものではなく、画面方向に関する視覚的な代理指標**です。画面を見ていても頭の中で別のことを考えている場合や、画面外のノートを見ながら深く考えている場合は区別できません。カメラだけで理解度・思考・記憶・本当の集中状態を読み取ることはできません。

健康・知能・学力・能力を評価するためには使わないでください。
