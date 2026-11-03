# FOCUS LAB

**A privacy-first focus session tracker that turns your study/work sessions into understandable insights.**

🔗 **Live demo:** https://focus-lab-andy127.vercel.app

FOCUS LAB helps you record a focus session, check in with yourself, and review simple visual summaries afterwards. It is designed as a lightweight reflection tool—not as a medical or scientifically validated concentration test.

## Features

- **Live session timer** — start, pause, resume, and finish a session.
- **Estimated focus score** — a 0–100 indicator based on self-check-ins, interaction/activity signals, idle time, and interruptions.
- **Self check-ins** — record how focused you feel during a session.
- **Live chart and session summary** — review score changes, average/peak estimates, duration, and interruptions.
- **Session history** — keep recent results in your browser.
- **Privacy-first by design** — no account, server-side session database, camera, or microphone is used.

## How to use

1. Open the [live app](https://focus-lab-andy127.vercel.app).
2. Press **計測開始** to begin a session.
3. Use **集中度を記録** from time to time to record your own rating.
4. Pause/resume when needed.
5. Finish the session to see your summary and suggestions.

## Run locally

No build step or package installation is required.

1. Download or clone this repository.
2. Open `index.html` in a modern browser.

## Privacy

Session history is stored in the browser's `localStorage`. Clearing this site's browser storage removes the locally saved history. The app does not request camera or microphone access and does not send session records to a backend.

## Important limitations

The score is an **experimental estimate**, not an objective measurement of attention. Keyboard/mouse interaction can be low during perfectly focused activities such as reading, watching a lesson, or thinking. For that reason, the score should be treated as a reflection aid—not a judgment of your ability, health, or performance.

## Deployment

The production app is hosted on Vercel:

- https://focus-lab-andy127.vercel.app

The GitHub repository's `main` branch is intended to be the source of truth for the Git-connected Vercel project. Commits pushed to `main` should trigger a production deployment once the Git integration is connected.

---

# 日本語

FOCUS LABは、勉強や作業中の集中セッションを記録し、グラフや振り返りで「集中の傾向」を見える化する軽量ツールです。

## 主な機能

- 計測の開始・一時停止・再開・終了
- 自己評価、操作状況、アイドル時間、中断回数などを使った推定スコア
- 集中度の推移を表示するリアルタイムグラフ
- セッション終了後の平均・最高スコア、時間、中断回数のまとめ
- ブラウザ内に保存するセッション履歴

## プライバシー

セッション履歴はブラウザ内の `localStorage` に保存されます。アカウント登録やサーバーへのセッションデータ送信は不要です。カメラ・マイクも使用しません。

## 注意

集中スコアは実験的な推定値であり、科学的・医学的に確立された集中力検査ではありません。読書・思考・動画学習のように操作が少ない活動では、集中していても低く表示される場合があります。自分の状態を振り返るための参考値として使ってください。
