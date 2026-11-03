# FOCUS LAB

**A privacy-first, browser-based sustained-attention task and study-session log.**

🔗 **Live app:** https://focus-lab-github.vercel.app

FOCUS LAB deliberately keeps two kinds of information separate:

1. A **10-minute PVT-inspired visual reaction task** that records observable response performance.
2. A **study-session timer and self-rating** that records the user's own impression of a study period.

There is no single "concentration score". The app does not infer concentration from gaze, mouse movement, or time spent on a page.

## 10-minute reaction task

A visual target appears at unpredictable intervals. Press the response button or Space as quickly as you can when it appears; do not press during the waiting period.

The task records:
- Median and mean reaction time
- Mean reaction time of the fastest 10% and slowest 10% of valid responses
- Slow responses (500 ms or longer)
- False starts / anticipatory responses
- Missed targets (no response within 10 seconds)
- Number of valid responses and presented targets

Timing uses the browser's high-resolution `performance.now()` clock and a `requestAnimationFrame` timestamp for stimulus presentation. The initial wait is randomized from 2–10 seconds; after a response, the one-second feedback interval plus the next random wait totals 2–10 seconds. If the page becomes hidden or the browser window loses focus during a test, the test is invalidated because background scheduling and focus changes can distort timing.

The first three completed tests are treated as familiarization/history. After that, the app can compare a test with the previous three sessions from the same browser. No population ranking, age norm, or medical interpretation is shown.

## Study-session log

A separate stopwatch records study duration. At the end, the user can record a 1–5 self-rating. The app does not automatically infer concentration from elapsed time.

## What this can and cannot tell you

A 10-minute Psychomotor Vigilance Test (PVT) is widely used in research to assess behavioral vigilant attention using visual stimuli at random intervals. A response time of 500 ms or more is commonly treated as a lapse in the standard task. This website is a **PVT-inspired browser implementation**, not a certified or laboratory-equivalent PVT.

The task measures response performance in this specific test—not comprehension, reasoning quality, motivation, memory, mind-wandering, or concentration throughout ordinary study. Browser, screen refresh, mouse/trackpad, operating system, and input latency can affect reaction time. For personal comparisons, use the same device, browser, and input method.

Research has found that shorter PVT versions do not all behave like the 10-minute version: some 5-minute measures can be useful in specific samples, while a 3-minute version has shown convergent-validity limitations against the 10-minute version in sleep-loss research. This is why the app uses a 10-minute task rather than inventing a quick 30-second "focus score". Laboratory findings do not automatically validate this browser implementation or provide norms for adolescents.

## Privacy

- No camera or microphone is requested.
- No video or audio is recorded.
- Session and reaction-task summaries are stored in the browser's `localStorage`.
- Data is not sent to a server by this app. Clearing this site's browser storage deletes local history.

## References

- [Response speed measurements on the psychomotor vigilance test: how precise is precise enough?](https://pmc.ncbi.nlm.nih.gov/articles/PMC8240655/)
- [Test-retest reliability of the 5-minute psychomotor vigilance task in working-aged females](https://pubmed.ncbi.nlm.nih.gov/34627928/)
- [The 3-Minute Psychomotor Vigilance Test Demonstrates Inadequate Convergent Validity Relative to the 10-Minute Version](https://pubmed.ncbi.nlm.nih.gov/35242006/)

## Technology

- HTML, CSS, vanilla JavaScript
- `performance.now()` and `requestAnimationFrame()`
- Canvas for reaction-time visualization
- Browser `localStorage`

## Deployment

- **Production:** https://focus-lab-github.vercel.app
- **Repository:** https://github.com/Andy234-andy/FOCUS-LAB

The repository's `main` branch is connected to Vercel for automatic deployments.

---

# 日本語

FOCUS LABは、**反応課題の成績**と**勉強中の本人の振り返り**を別々に記録するツールです。

カメラの視線やマウスの動きから、根拠のない「集中度」を作ることはしません。

## 10分間の反応課題

ランダムなタイミングで画面に合図が出ます。合図が出たときだけボタンまたはスペースキーを押します。

記録する項目：
- 反応時間の中央値・平均値
- 速い反応10%・遅い反応10%の平均
- 500ms以上の遅い反応
- 先走り反応
- 10秒以内に反応しなかった見落とし
- 有効反応数・合図の回数

ブラウザの高分解能時計 `performance.now()` と `requestAnimationFrame` を利用します。初回の合図は2〜10秒のランダム間隔です。2回目以降は、1秒の結果表示と次のランダム待機を合わせて2〜10秒になるようにしています。テスト中に別タブへ移動したり、ブラウザのウィンドウが非アクティブになった場合は、タイミングの正確さを維持できないため、そのテストを無効にします。

最初の3回は操作への慣れを含む記録として扱います。その後は、同じブラウザに保存された過去3回の結果と個人内比較を表示できます。集団平均との差、年齢別の基準点、医学的判定は表示しません。

## 勉強セッション記録

別のタイマーで勉強時間を記録し、終了時に本人の主観的な集中感を1〜5で残せます。時間だけから集中度を推測することはありません。

## 測定の限界

10分間のPsychomotor Vigilance Test（PVT）は、ランダムな視覚刺激への反応を使って持続的な注意・覚醒状態を調べる研究課題として広く使われています。標準的なPVTでは500ms以上の反応を遅い反応（lapse）として扱うことがあります。

ただし、このサイトは**PVTに着想を得たブラウザ上の反応課題**であり、認定された医療検査・研究室用装置ではありません。測れるのはこの課題中の反応パフォーマンスです。理解力、思考の深さ、記憶、意欲、普段の勉強中の集中状態そのものは測れません。

画面更新、OS、ブラウザ、マウスやトラックパッドの入力遅延が結果に影響します。個人内で比較するときは、同じ端末・ブラウザ・入力方法を使ってください。研究室で得られた結果が、このブラウザ版や中高生の基準値を保証するわけではありません。

## プライバシー

カメラ・マイクは使用しません。記録はブラウザ内の `localStorage` に保存し、サーバーへ送信しません。ブラウザのサイトデータを削除すると履歴も消えます。
