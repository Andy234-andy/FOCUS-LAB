# FOCUS LAB

**A live camera-based visual focus-signal dashboard.**

🔗 **Live app:** https://focus-lab-github.vercel.app

FOCUS LAB provides a real-time dashboard that uses a webcam to observe visible eye/face direction signals during a work session. It shows a live indicator, camera preview, signal statistics, a timeline, and session history.

> **Important limitation:** A camera cannot directly read thoughts, comprehension, motivation, or a person's true mental concentration. Looking at a screen is not proof of being focused. The live score is an experimental visual proxy based on how closely visible eye/head signals match the initial calibration—not a validated concentration test or a measure of ability.

## Features

- Live session timer with start, pause, resume, and finish.
- Camera preview and local face/eye landmark processing.
- Eight-second calibration using the user's usual screen-viewing posture.
- Live visual-signal estimate, face-detection rate, and screen-direction match rate.
- Live timeline chart and session summary.
- Session history stored locally in the browser.
- No manual "how focused are you right now?" slider or check-in is required.

## How it works

1. Press **カメラで計測スタート** and grant camera permission.
2. The app requests camera access and loads MediaPipe Face Landmarker.
3. During an eight-second calibration, it records a baseline of visible eye and head landmark positions.
4. During the session, it compares recent observations with that baseline and displays a rolling visual-signal estimate.
5. Finish the session to save a local summary.

The displayed value is affected by camera placement, lighting, glasses, face/eye tracking quality, head posture, and normal gaze shifts. It can remain high while someone is daydreaming at the screen, and it can fall while someone thinks deeply away from the screen. Treat it as a visual cue, not a mind-reading system.

## Privacy

- Camera access starts only after the user presses the start button and grants browser permission.
- Video frames are processed in the browser with MediaPipe Face Landmarker.
- The app does not record, save, or upload camera frames.
- The microphone is not requested or used.
- Summary values are stored in browser `localStorage`.
- The MediaPipe JavaScript package, WASM runtime, and model are downloaded from their respective CDNs/model hosting when needed; live camera frames are not sent to those servers by this app.

## Technology

- HTML, CSS, vanilla JavaScript
- Browser `getUserMedia` API
- [MediaPipe Face Landmarker for Web](https://developers.google.com/edge/mediapipe/solutions/vision/face_landmarker/web_js)
- Canvas charts and browser `localStorage`

## Deployment

- **Production:** https://focus-lab-github.vercel.app
- **Repository:** https://github.com/Andy234-andy/FOCUS-LAB

The repository's `main` branch is connected to Vercel for automatic deployments.

---

# 日本語

FOCUS LABは、カメラで顔・目の向きなどの視覚サインを観察し、リアルタイムのダッシュボードで表示するツールです。

## 主な機能

- リアルタイムの推定値と計測タイマー
- カメラ映像のプレビュー
- 8秒間の初期調整
- 顔検出率・画面方向の一致率
- 推移グラフとセッション終了後のレポート
- ブラウザ内に保存する履歴

「今どのくらい集中しているか」を手入力するスライダーはありません。カメラの視覚サインをリアルタイムに表示します。

## 使い方

1. [公開サイト](https://focus-lab-github.vercel.app)をHTTPS対応ブラウザで開く。
2. 「カメラで計測スタート」を押し、ブラウザのカメラ利用を許可する。
3. 普段の姿勢で画面を見る8秒間の初期調整を行う。
4. ライブ推定値・顔検出率・画面方向の一致率・グラフを確認する。
5. 一時停止・再開・終了を行い、セッション履歴を振り返る。

## 測定の限界

表示する値は、初期調整時と似た目・顔の向きが観測された割合を中心とする実験的な視覚指標です。カメラだけで脳内の集中状態、理解度、思考の深さ、意欲を直接測ることはできません。画面を見ていても別のことを考えている場合や、画面外のノートを見ながら深く考えている場合を区別できません。能力・学力・健康の評価には使用しないでください。

## プライバシー

カメラ映像はブラウザ内で処理し、録画・保存・サーバー送信はしません。マイクは使用しません。集計値のみブラウザの `localStorage` に保存します。解析用ライブラリ・WASM・モデルはCDN等から読み込みますが、ライブ映像を送信する処理はありません。
