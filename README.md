<!DOCTYPE html>
<html lang="zh-HK">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>星光語文探險島：小四中文8分鐘限時大挑戰</title>
  <style>
    /* ============================================================
       1. 核心變數與系統繁體中文字體（無外部字體阻塞）
    ============================================================ */
    :root {
      --font-tc: "PingFang TC", "Hiragino Sans TC", "Microsoft JhengHei", "Noto Sans TC", sans-serif;
      --bg-cream: #fffdf7;
      --card-bg: #ffffff;
      --ink-dark: #1e293b;
      --ink-muted: #475569;
      --gold: #f59e0b;
      --gold-dark: #b45309;
      --gold-soft: #fef3c7;
      --sky: #0ea5e9;
      --sky-dark: #0369a1;
      --sky-soft: #e0f2fe;
      --emerald: #10b981;
      --emerald-dark: #047857;
      --emerald-soft: #d1fae5;
      --coral: #f97316;
      --coral-dark: #c2410c;
      --violet: #7c3aed;
      --violet-dark: #5b21b6;
      --violet-soft: #ede9fe;
      --rose: #ef4444;
      --rose-soft: #fee2e2;
      --border: #e2e8f0;
      --radius-lg: 24px;
      --radius-md: 16px;
      --shadow-card: 0 14px 34px rgba(30, 58, 108, 0.14), 0 4px 10px rgba(30, 58, 108, 0.06);
    }

    * {
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
    }

    html, body {
      margin: 0;
      padding: 0;
      min-height: 100%;
      font-family: var(--font-tc);
      color: var(--ink-dark);
      background: linear-gradient(165deg, #dbeafe 0%, #eff6ff 34%, #fef9e7 72%, #fde68a 100%);
      background-attachment: fixed;
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* 關鍵穩定性規則：所有隱藏區塊強制 display: none，絕不留下隱形遮罩 */
    .hidden {
      display: none !important;
    }

    /* ============================================================
       2. 共用排版容器與按鈕（針對 iPad 觸控優化，高度 >= 48px）
    ============================================================ */
    .app-shell {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }

    .container {
      width: 100%;
      max-width: 860px;
      margin: 0 auto;
      padding: 16px;
    }

    .card {
      background: var(--card-bg);
      border: 3px solid #ffffff;
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-card);
      padding: 24px;
    }

    /* 立體手感按鈕 */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      min-height: 50px;
      padding: 12px 22px;
      border: none;
      border-radius: var(--radius-md);
      font-family: var(--font-tc);
      font-size: 19px;
      font-weight: 800;
      cursor: pointer;
      user-select: none;
      touch-action: manipulation;
      transition: transform 0.1s ease, box-shadow 0.1s ease, filter 0.15s ease;
    }

    .btn:active:not(:disabled) {
      transform: translateY(3px);
    }

    .btn:disabled {
      opacity: 0.52;
      cursor: not-allowed;
    }

    .btn-gold {
      background: linear-gradient(180deg, #fcd34d 0%, #f59e0b 100%);
      color: #451a03;
      box-shadow: 0 5px 0 var(--gold-dark);
    }
    .btn-gold:active:not(:disabled) {
      box-shadow: 0 2px 0 var(--gold-dark);
    }

    .btn-emerald {
      background: linear-gradient(180deg, #34d399 0%, #10b981 100%);
      color: #ffffff;
      box-shadow: 0 5px 0 var(--emerald-dark);
    }
    .btn-emerald:active:not(:disabled) {
      box-shadow: 0 2px 0 var(--emerald-dark);
    }

    .btn-sky {
      background: linear-gradient(180deg, #38bdf8 0%, #0284c7 100%);
      color: #ffffff;
      box-shadow: 0 5px 0 var(--sky-dark);
    }
    .btn-sky:active:not(:disabled) {
      box-shadow: 0 2px 0 var(--sky-dark);
    }

    .btn-coral {
      background: linear-gradient(180deg, #fb923c 0%, #f97316 100%);
      color: #ffffff;
      box-shadow: 0 5px 0 var(--coral-dark);
    }
    .btn-coral:active:not(:disabled) {
      box-shadow: 0 2px 0 var(--coral-dark);
    }

    .btn-violet {
      background: linear-gradient(180deg, #8b5cf6 0%, #7c3aed 100%);
      color: #ffffff;
      box-shadow: 0 5px 0 var(--violet-dark);
    }
    .btn-violet:active:not(:disabled) {
      box-shadow: 0 2px 0 var(--violet-dark);
    }

    .btn-soft {
      background: #ffffff;
      color: var(--ink-dark);
      border: 2px solid #cbd5e1;
      box-shadow: 0 4px 0 #cbd5e1;
    }
    .btn-soft:active:not(:disabled) {
      box-shadow: 0 1px 0 #cbd5e1;
    }

    .btn-sm {
      min-height: 44px;
      padding: 8px 16px;
      font-size: 16px;
      border-radius: 12px;
    }

    .btn-full {
      width: 100%;
    }

    /* 輸入框：防止 iPad Safari 自動縮放，字體 >= 18px */
    .text-input {
      width: 100%;
      min-height: 52px;
      padding: 12px 16px;
      border: 2.5px solid #cbd5e1;
      border-radius: 14px;
      font-family: var(--font-tc);
      font-size: 20px;
      font-weight: 700;
      color: var(--ink-dark);
      background: #ffffff;
      outline: none;
      transition: border-color 0.15s ease, box-shadow 0.15s ease;
    }

    .text-input:focus {
      border-color: var(--sky);
      box-shadow: 0 0 0 4px rgba(14, 165, 233, 0.2);
    }

    /* 徽章 */
    .badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 6px 14px;
      border-radius: 999px;
      font-size: 15px;
      font-weight: 800;
    }
    .badge-gold { background: var(--gold-soft); color: #92400e; border: 1.5px solid #fcd34d; }
    .badge-emerald { background: var(--emerald-soft); color: #065f46; border: 1.5px solid #6ee7b7; }
    .badge-violet { background: var(--violet-soft); color: #5b21b6; border: 1.5px solid #c4b5fd; }
    .badge-sky { background: var(--sky-soft); color: #075985; border: 1.5px solid #7dd3fc; }

    /* ============================================================
       3. 頂部常駐狀態列 (HUD)
    ============================================================ */
    .hud {
      position: sticky;
      top: 0;
      z-index: 30;
      background: rgba(15, 23, 42, 0.92);
      color: #ffffff;
      padding: 10px 14px 12px;
      box-shadow: 0 4px 16px rgba(15, 23, 42, 0.25);
    }

    .hud-inner {
      max-width: 860px;
      margin: 0 auto;
    }

    .hud-row {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
    }

    .hud-group {
      display: flex;
      align-items: center;
      gap: 8px;
      flex-wrap: wrap;
    }

    .hud-icon-btn {
      min-width: 44px;
      min-height: 44px;
      padding: 0 12px;
      border: 1.5px solid rgba(255, 255, 255, 0.25);
      border-radius: 12px;
      background: rgba(255, 255, 255, 0.12);
      color: #ffffff;
      font-family: var(--font-tc);
      font-size: 16px;
      font-weight: 800;
      cursor: pointer;
    }
    .hud-icon-btn:active {
      transform: translateY(2px);
    }

    .hud-pill {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 6px 12px;
      border-radius: 999px;
      font-size: 16px;
      font-weight: 800;
      background: rgba(255, 255, 255, 0.14);
      border: 1.5px solid rgba(255, 255, 255, 0.2);
    }

    .hud-pill-score {
      background: rgba(245, 158, 11, 0.25);
      border-color: rgba(252, 211, 77, 0.6);
      color: #fde68a;
    }

    .hud-pill-timer {
      font-variant-numeric: tabular-nums;
      min-width: 96px;
      justify-content: center;
    }

    .hud-pill-timer.urgent {
      background: #dc2626;
      border-color: #fca5a5;
      color: #ffffff;
      animation: pulseUrgent 1s ease-in-out infinite;
    }

    @keyframes pulseUrgent {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.06); }
    }

    .progress-track {
      margin-top: 10px;
      height: 10px;
      width: 100%;
      background: rgba(255, 255, 255, 0.18);
      border-radius: 999px;
      overflow: hidden;
    }

    .progress-fill {
      height: 100%;
      width: 4%;
      background: linear-gradient(90deg, #fcd34d, #34d399, #38bdf8);
      border-radius: 999px;
      transition: width 0.35s ease;
    }

    /* ============================================================
       4. 首頁設計
    ============================================================ */
    .top-bar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      margin-bottom: 14px;
      flex-wrap: wrap;
    }

    .hero-title {
      margin: 8px 0 6px;
      font-size: clamp(28px, 5vw, 42px);
      font-weight: 900;
      color: #1e3a8a;
      line-height: 1.2;
    }

    .hero-subtitle {
      margin: 0;
      font-size: clamp(17px, 2.6vw, 21px);
      font-weight: 800;
      color: #b45309;
    }

    .stage-preview-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      margin: 20px 0;
    }

    .stage-preview-box {
      border-radius: 18px;
      padding: 16px 14px;
      text-align: center;
      border: 2px solid transparent;
    }

    .sp-1 { background: #ecfdf5; border-color: #a7f3d0; }
    .sp-2 { background: #f5f3ff; border-color: #ddd6fe; }
    .sp-3 { background: #f0f9ff; border-color: #bae6fd; }

    .sp-emoji { font-size: 32px; display: block; margin-bottom: 6px; }
    .sp-name { font-size: 18px; font-weight: 900; color: var(--ink-dark); }
    .sp-desc { font-size: 14px; font-weight: 700; color: var(--ink-muted); margin-top: 4px; }

    .student-box {
      background: #fffbeb;
      border: 2px solid #fde68a;
      border-radius: 18px;
      padding: 16px;
      margin-bottom: 20px;
    }

    .student-box label {
      display: block;
      font-size: 16px;
      font-weight: 800;
      color: #92400e;
      margin-bottom: 8px;
    }

    /* ============================================================
       5. 遊戲主畫面與題目元件
    ============================================================ */
    .mascot-strip {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 14px;
    }

    .mascot-avatar {
      width: 56px;
      height: 56px;
      border-radius: 50%;
      background: linear-gradient(135deg, #fef08a, #fbbf24);
      border: 3px solid #ffffff;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.12);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 32px;
      flex-shrink: 0;
    }

    .mascot-bubble {
      background: #ffffff;
      border: 2px solid #e2e8f0;
      border-radius: 18px;
      border-bottom-left-radius: 4px;
      padding: 10px 16px;
      font-size: 16px;
      font-weight: 700;
      color: var(--ink-dark);
      box-shadow: 0 3px 8px rgba(0, 0, 0, 0.06);
      flex: 1;
    }

    .q-header {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
      margin-bottom: 16px;
    }

    .sentence-box {
      background: #f8fafc;
      border: 2.5px solid #cbd5e1;
      border-radius: 18px;
      padding: 20px;
      font-size: clamp(20px, 3vw, 24px);
      font-weight: 800;
      color: #0f172a;
      line-height: 1.9;
    }

    .sentence-box-s1 { background: #f0fdf4; border-color: #86efac; }
    .sentence-box-s2 { background: #f5f3ff; border-color: #c4b5fd; }
    .sentence-box-s3 { background: #f0f9ff; border-color: #7dd3fc; }

    .inline-blank {
      display: inline-block;
      min-width: 64px;
      padding: 0 12px;
      margin: 0 4px;
      background: #ffffff;
      border-bottom: 4px solid var(--emerald);
      border-radius: 10px;
      color: var(--emerald-dark);
      text-align: center;
      font-weight: 900;
    }

    .inline-blank.solved {
      background: var(--emerald);
      color: #ffffff;
      border-bottom-color: var(--emerald-dark);
    }

    .inline-blank.revealed {
      background: var(--coral);
      color: #ffffff;
      border-bottom-color: var(--coral-dark);
    }

    /* 字數方格視覺提示 */
    .char-boxes {
      display: flex;
      justify-content: center;
      gap: 10px;
      margin: 18px 0 14px;
    }

    .char-box {
      width: 54px;
      height: 56px;
      border-radius: 14px;
      border: 2.5px solid #94a3b8;
      background: #f8fafc;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 26px;
      font-weight: 900;
      color: var(--ink-dark);
      transition: all 0.15s ease;
    }

    .char-box.filled {
      border-color: var(--emerald);
      background: #ecfdf5;
      color: var(--emerald-dark);
    }

    .input-row {
      display: flex;
      gap: 10px;
      max-width: 520px;
      margin: 0 auto;
    }

    /* 回饋與提示框 */
    .hint-box {
      margin-top: 14px;
      background: #fffbeb;
      border: 2px solid #fcd34d;
      border-radius: 14px;
      padding: 12px 16px;
      font-size: 17px;
      font-weight: 700;
      color: #92400e;
    }

    .feedback-box {
      margin-top: 16px;
      border-radius: 16px;
      padding: 16px 18px;
      font-size: 18px;
      font-weight: 700;
      border: 2px solid transparent;
    }

    .fb-ok {
      background: #ecfdf5;
      border-color: #34d399;
      color: #065f46;
    }

    .fb-warn {
      background: #fffbeb;
      border-color: #fbbf24;
      color: #92400e;
    }

    .fb-err {
      background: #fef2f2;
      border-color: #f87171;
      color: #991b1b;
    }

    .action-row {
      margin-top: 16px;
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      justify-content: flex-end;
      align-items: center;
    }

    /* 選擇題選項按鈕 */
    .option-list {
      display: flex;
      flex-direction: column;
      gap: 12px;
      margin-top: 16px;
    }

    .option-btn {
      width: 100%;
      min-height: 58px;
      padding: 14px 16px;
      border-radius: 16px;
      border: 2.5px solid #cbd5e1;
      background: #ffffff;
      box-shadow: 0 4px 0 #cbd5e1;
      font-family: var(--font-tc);
      font-size: 19px;
      font-weight: 700;
      color: var(--ink-dark);
      text-align: left;
      display: flex;
      align-items: flex-start;
      gap: 12px;
      cursor: pointer;
      touch-action: manipulation;
    }

    .option-btn:active:not(:disabled) {
      transform: translateY(2px);
      box-shadow: 0 2px 0 #cbd5e1;
    }

    .option-btn.opt-correct {
      background: #ecfdf5;
      border-color: #10b981;
      box-shadow: 0 4px 0 #059669;
      color: #065f46;
    }

    .option-btn.opt-wrong {
      background: #fef2f2;
      border-color: #ef4444;
      box-shadow: 0 4px 0 #b91c1c;
      color: #991b1b;
    }

    .opt-tag {
      width: 34px;
      height: 34px;
      border-radius: 10px;
      background: #e0f2fe;
      color: #0369a1;
      font-weight: 900;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }

    /* 第二關配對與重組卡片 */
    .pair-slot-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-width: 88px;
      min-height: 44px;
      padding: 4px 14px;
      margin: 4px;
      border-radius: 12px;
      border: 2.5px dashed var(--violet);
      background: #ffffff;
      color: var(--violet);
      font-family: var(--font-tc);
      font-size: 20px;
      font-weight: 900;
      cursor: pointer;
      vertical-align: middle;
    }

    .pair-slot-btn.filled {
      border-style: solid;
      background: var(--violet);
      color: #ffffff;
    }

    .word-card-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      justify-content: center;
      margin-top: 18px;
    }

    .reorder-tray {
      min-height: 82px;
      background: #f5f3ff;
      border: 2.5px dashed #a78bfa;
      border-radius: 16px;
      padding: 14px;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 10px;
      margin-top: 14px;
    }

    .topic-chips {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin: 12px 0 16px;
    }

    .topic-chip {
      min-height: 40px;
      padding: 6px 14px;
      border-radius: 999px;
      border: 2px solid #c4b5fd;
      background: #f5f3ff;
      color: #5b21b6;
      font-family: var(--font-tc);
      font-size: 15px;
      font-weight: 800;
      cursor: pointer;
    }

    /* 第三關分類大按鈕與放標點按鈕 */
    .classify-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 14px;
      margin-top: 18px;
    }

    .classify-btn {
      min-height: 108px;
      padding: 16px;
      border-radius: 18px;
      border: 2.5px solid #cbd5e1;
      background: #ffffff;
      box-shadow: 0 5px 0 #cbd5e1;
      font-family: var(--font-tc);
      cursor: pointer;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 6px;
      touch-action: manipulation;
    }

    .classify-btn:active:not(:disabled) {
      transform: translateY(3px);
    }

    .classify-btn.opt-correct {
      background: #ecfdf5;
      border-color: #10b981;
      box-shadow: 0 5px 0 #059669;
    }

    .classify-btn.opt-wrong {
      background: #fef2f2;
      border-color: #ef4444;
      box-shadow: 0 5px 0 #b91c1c;
    }

    .slot-pill-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-height: 44px;
      padding: 4px 12px;
      margin: 4px 6px;
      border-radius: 12px;
      border: 2.5px dashed var(--sky);
      background: #e0f2fe;
      color: var(--sky-dark);
      font-family: var(--font-tc);
      font-size: 18px;
      font-weight: 900;
      cursor: pointer;
      vertical-align: middle;
    }

    .slot-pill-btn.slot-ok {
      border-style: solid;
      border-color: var(--emerald-dark);
      background: var(--emerald);
      color: #ffffff;
      font-size: 22px;
    }

    .slot-pill-btn.slot-bad {
      border-style: solid;
      border-color: var(--rose);
      background: var(--rose-soft);
      color: #b91c1c;
    }

    /* ============================================================
       6. 結算榮譽證書
    ============================================================ */
    .cert-card {
      border: 4px solid #fbbf24;
      background: linear-gradient(180deg, #fffef9 0%, #fffbeb 100%);
    }

    .stars-row {
      font-size: 46px;
      letter-spacing: 8px;
      margin: 8px 0;
    }

    .stats-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      margin: 18px 0;
    }

    .stat-box {
      background: #ffffff;
      border: 2px solid #e2e8f0;
      border-radius: 16px;
      padding: 14px 10px;
      text-align: center;
    }

    .stat-label { font-size: 14px; font-weight: 800; color: var(--ink-muted); }
    .stat-value { font-size: 24px; font-weight: 900; color: #1e3a8a; margin-top: 4px; }

    .stage-bars {
      background: #ffffff;
      border: 2px solid #e2e8f0;
      border-radius: 16px;
      padding: 16px;
      margin-bottom: 16px;
    }

    .bar-item { margin-bottom: 12px; }
    .bar-item:last-child { margin-bottom: 0; }
    .bar-head {
      display: flex;
      justify-content: space-between;
      font-size: 16px;
      font-weight: 800;
      margin-bottom: 6px;
    }
    .bar-track {
      height: 12px;
      background: #f1f5f9;
      border-radius: 999px;
      overflow: hidden;
    }
    .bar-fill {
      height: 100%;
      border-radius: 999px;
      transition: width 0.5s ease;
    }

    .showcase-box {
      background: #f5f3ff;
      border: 2px solid #c4b5fd;
      border-radius: 16px;
      padding: 16px;
      margin-bottom: 16px;
    }

    .review-box {
      background: #ffffff;
      border: 2px solid #fed7aa;
      border-radius: 16px;
      padding: 16px;
      margin-bottom: 20px;
    }

    .review-item {
      padding: 10px 12px;
      border-radius: 12px;
      background: #fff7ed;
      margin-top: 8px;
      font-size: 16px;
    }

    /* ============================================================
       7. 彈窗與老師專區／全螢幕 QR Code
    ============================================================ */
    .modal-backdrop {
      position: fixed;
      inset: 0;
      z-index: 60;
      background: rgba(15, 23, 42, 0.72);
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 14px;
    }

    .modal-box {
      background: #ffffff;
      width: 100%;
      max-width: 720px;
      max-height: 90vh;
      border-radius: 24px;
      box-shadow: 0 24px 50px rgba(0, 0, 0, 0.35);
      display: flex;
      flex-direction: column;
      overflow: hidden;
    }

    .modal-box-sm {
      max-width: 440px;
      padding: 24px;
      text-align: center;
    }

    .modal-head {
      background: #0f172a;
      color: #ffffff;
      padding: 16px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
    }

    .modal-body {
      padding: 20px;
      overflow-y: auto;
      -webkit-overflow-scrolling: touch;
    }

    .teacher-section {
      background: #f8fafc;
      border: 2px solid #e2e8f0;
      border-radius: 18px;
      padding: 16px;
      margin-bottom: 16px;
    }

    .teacher-section h3 {
      margin: 0 0 12px;
      font-size: 19px;
      font-weight: 900;
      color: #0f172a;
    }

    .qr-preview-frame {
      display: flex;
      flex-direction: column;
      align-items: center;
      background: #ffffff;
      border: 2px dashed #94a3b8;
      border-radius: 18px;
      padding: 18px;
      margin-top: 12px;
    }

    .qr-img-wrap {
      background: #ffffff;
      padding: 10px;
      border-radius: 14px;
      border: 2px solid #e2e8f0;
      display: flex;
      align-items: center;
      justify-content: center;
      min-width: 240px;
      min-height: 240px;
    }

    .qr-img-wrap img {
      display: block;
      width: 220px;
      height: 220px;
      object-fit: contain;
    }

    .switch-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      padding: 10px 12px;
      background: #ffffff;
      border: 1.5px solid #e2e8f0;
      border-radius: 12px;
      margin-bottom: 8px;
      font-size: 16px;
      font-weight: 800;
      cursor: pointer;
    }

    .switch-row input[type="checkbox"] {
      width: 24px;
      height: 24px;
      accent-color: var(--sky-dark);
      cursor: pointer;
    }

    .jump-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
    }

    .ans-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 15px;
      margin-top: 10px;
      background: #ffffff;
    }
    .ans-table th, .ans-table td {
      border: 1px solid #cbd5e1;
      padding: 8px 10px;
      text-align: left;
      vertical-align: top;
    }
    .ans-table th {
      background: #f1f5f9;
      font-weight: 900;
    }

    /* 全螢幕投影二維碼 */
    .qr-fullscreen {
      position: fixed;
      inset: 0;
      z-index: 80;
      background: linear-gradient(155deg, #0f172a 0%, #1e3a8a 100%);
      color: #ffffff;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 24px;
      text-align: center;
    }

    .qr-fs-close {
      position: fixed;
      top: 18px;
      right: 18px;
      z-index: 85;
    }

    .qr-fs-board {
      background: #ffffff;
      padding: 24px;
      border-radius: 28px;
      border: 6px solid #fcd34d;
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.45);
      margin: 18px 0;
    }

    .qr-fs-board img {
      display: block;
      width: min(320px, 70vw);
      height: min(320px, 70vw);
      object-fit: contain;
    }

    /* ============================================================
       8. 響應式微調（手機與 iPad 直／橫向）
    ============================================================ */
    @media (max-width: 680px) {
      .card { padding: 18px; }
      .stage-preview-grid { grid-template-columns: 1fr; }
      .classify-grid { grid-template-columns: 1fr; }
      .stats-grid { grid-template-columns: 1fr; }
      .input-row { flex-direction: column; }
      .jump-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <div class="app-shell">

    <!-- ==========================================================
         頂部常駐狀態列 (HUD：開始挑戰後顯示)
    ========================================================== -->
    <header id="game-hud" class="hud hidden">
      <div class="hud-inner">
        <div class="hud-row">
          <div class="hud-group">
            <button type="button" id="hud-home-btn" class="hud-icon-btn" title="返回首頁">🏠 首頁</button>
            <span id="hud-stage-label" class="hud-pill">⛰️ 第一關：神秘字詞谷</span>
            <span id="hud-progress-text" class="hud-pill">第 1 / 13 題</span>
          </div>
          <div class="hud-group">
            <span class="hud-pill hud-pill-score">⭐ <span id="hud-score">0</span> 分</span>
            <span id="hud-timer-box" class="hud-pill hud-pill-timer">⏱️ <span id="hud-timer">08:00</span></span>
            <button type="button" id="hud-sound-btn" class="hud-icon-btn" title="切換音效">🔊</button>
          </div>
        </div>
        <div class="progress-track">
          <div id="hud-progress-fill" class="progress-fill"></div>
        </div>
      </div>
    </header>

    <!-- ==========================================================
         畫面 1：首頁畫面
    ========================================================== -->
    <main id="screen-welcome" class="container">
      <div class="top-bar">
        <button type="button" id="welcome-sound-btn" class="btn btn-soft btn-sm">🔊 音效：開</button>
        <button type="button" id="open-teacher-btn" class="btn btn-sky btn-sm">👨‍🏫 老師專區 / QR Code</button>
      </div>

      <section class="card" style="text-align: center;">
        <span class="badge badge-gold">✨ 香港小學四年級中文科課堂挑戰</span>
        <h1 class="hero-title">🌟 星光語文探險島</h1>
        <p class="hero-subtitle">小四中文 8 分鐘限時大挑戰</p>

        <div class="stage-preview-grid">
          <div class="stage-preview-box sp-1">
            <span class="sp-emoji">⛰️</span>
            <div class="sp-name">第一關：神秘字詞谷</div>
            <div class="sp-desc">不供詞填充 13 題</div>
          </div>
          <div class="stage-preview-box sp-2">
            <span class="sp-emoji">🌉</span>
            <div class="sp-name">第二關：魔法句式橋</div>
            <div class="sp-desc">「那麼⋯⋯那麼⋯⋯」4 題</div>
          </div>
          <div class="stage-preview-box sp-3">
            <span class="sp-emoji">🔎</span>
            <div class="sp-name">第三關：標點偵探社</div>
            <div class="sp-desc">省略號兩種用法 6 題</div>
          </div>
        </div>

        <div class="student-box" style="text-align: left;">
          <label for="student-name-input">🪪 探險家姓名／班別學號（選填，將印於結算榮譽證書上）</label>
          <input
            id="student-name-input"
            class="text-input"
            type="text"
            maxlength="20"
            placeholder="例如：4A 12 陳小明（不填預設「小探險家」）"
            autocomplete="off"
            autocorrect="off"
            autocapitalize="off"
            spellcheck="false"
          />
        </div>

        <button type="button" id="start-game-btn" class="btn btn-gold btn-full" style="font-size: 22px; min-height: 60px;">
          🚀 開始 8 分鐘挑戰
        </button>
        <p style="margin: 12px 0 0; font-size: 14px; font-weight: 700; color: #64748b;">
          共 23 題互動任務 ‧ 支援 iPad 手寫、速成、倉頡及拼音輸入
        </p>
      </section>
    </main>

    <!-- ==========================================================
         畫面 2：關卡出發介紹頁
    ========================================================== -->
    <main id="screen-stage-intro" class="container hidden">
      <section class="card" style="text-align: center; max-width: 680px; margin: 16px auto;">
        <span id="intro-badge" class="badge badge-emerald">第一關</span>
        <div id="intro-emoji" style="font-size: 62px; margin: 10px 0;">⛰️</div>
        <h2 id="intro-title" style="margin: 0 0 10px; font-size: 28px; font-weight: 900;">神秘字詞谷</h2>
        <p id="intro-desc" style="margin: 0 0 18px; font-size: 18px; font-weight: 700; color: #475569;"></p>
        <div id="intro-tips" class="hint-box" style="text-align: left; margin-bottom: 22px;"></div>
        <button type="button" id="intro-start-btn" class="btn btn-gold" style="min-width: 240px; font-size: 21px;">
          出發闖關 ➡️
        </button>
      </section>
    </main>

    <!-- ==========================================================
         畫面 3：遊戲作答主畫面
    ========================================================== -->
    <main id="screen-game" class="container hidden">
      <div class="mascot-strip">
        <div id="mascot-emoji" class="mascot-avatar">🦉</div>
        <div id="mascot-bubble" class="mascot-bubble">加油！細心讀一讀句子，你一定做得到！</div>
      </div>

      <section id="question-card" class="card"></section>
    </main>

    <!-- ==========================================================
         畫面 4：結算榮譽探險證書
    ========================================================== -->
    <main id="screen-report" class="container hidden">
      <section class="card cert-card">
        <div style="text-align: center;">
          <span class="badge badge-gold">🏆 星光語文探險島 ‧ 榮譽探險證書</span>
          <div id="report-stars" class="stars-row">⭐⭐⭐</div>
          <h2 id="report-title" style="margin: 4px 0; font-size: 30px; font-weight: 900; color: #1e3a8a;">語文探險大師</h2>
          <p id="report-student" style="margin: 4px 0 0; font-size: 20px; font-weight: 800; color: #b45309;">頒發予：小探險家</p>
        </div>

        <div class="stats-grid">
          <div class="stat-box">
            <div class="stat-label">星光總分</div>
            <div id="report-score" class="stat-value">0 分</div>
          </div>
          <div class="stat-box">
            <div class="stat-label">完成用時</div>
            <div id="report-time" class="stat-value">00分00秒</div>
          </div>
          <div class="stat-box">
            <div class="stat-label">總答對題數</div>
            <div id="report-total" class="stat-value">0 / 23</div>
          </div>
        </div>

        <div class="stage-bars">
          <div class="bar-item">
            <div class="bar-head">
              <span>⛰️ 第一關：神秘字詞谷（不供詞填充）</span>
              <span id="report-s1" style="color: #047857;">0 / 13</span>
            </div>
            <div class="bar-track">
              <div id="report-s1-bar" class="bar-fill" style="width: 0%; background: #10b981;"></div>
            </div>
          </div>

          <div class="bar-item">
            <div class="bar-head">
              <span>🌉 第二關：魔法句式橋（那麼⋯⋯那麼⋯⋯）</span>
              <span id="report-s2" style="color: #5b21b6;">0 / 4</span>
            </div>
            <div class="bar-track">
              <div id="report-s2-bar" class="bar-fill" style="width: 0%; background: #7c3aed;"></div>
            </div>
          </div>

          <div class="bar-item">
            <div class="bar-head">
              <span>🔎 第三關：標點偵探社（省略號用法）</span>
              <span id="report-s3" style="color: #0369a1;">0 / 6</span>
            </div>
            <div class="bar-track">
              <div id="report-s3-bar" class="bar-fill" style="width: 0%; background: #0ea5e9;"></div>
            </div>
          </div>
        </div>

        <!-- 學生原創造句展示 -->
        <div class="showcase-box">
          <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 8px; margin-bottom: 8px;">
            <strong style="font-size: 17px; color: #5b21b6;">✍️ 我的「那麼⋯⋯那麼⋯⋯」原創佳句</strong>
            <span class="badge badge-violet" style="font-size: 13px;">📸 可截圖給老師欣賞</span>
          </div>
          <div id="report-sentence-text" style="font-size: 20px; font-weight: 800; color: #1e293b; background: #ffffff; padding: 12px 14px; border-radius: 12px; border: 1.5px solid #ddd6fe;">
            （尚未填寫造句）
          </div>
        </div>

        <!-- 溫故知新小清單 -->
        <div id="report-review-area" class="review-box"></div>

        <div style="display: flex; flex-wrap: wrap; gap: 12px; justify-content: center;">
          <button type="button" id="report-retry-btn" class="btn btn-gold">🔄 重新挑戰</button>
          <button type="button" id="report-home-btn" class="btn btn-soft">🏠 返回首頁</button>
        </div>
      </section>
    </main>
  </div>

  <!-- ==========================================================
       彈窗 1：返回首頁確認（不使用瀏覽器 confirm）
  ========================================================== -->
  <div id="modal-exit" class="modal-backdrop hidden">
    <div class="modal-box modal-box-sm">
      <div style="font-size: 46px; margin-bottom: 6px;">🧭</div>
      <h3 style="margin: 0 0 8px; font-size: 22px; font-weight: 900;">確定要返回首頁嗎？</h3>
      <p style="margin: 0 0 20px; font-size: 16px; color: #475569; font-weight: 700;">
        返回首頁將會重新計算這次的探險進度喔！
      </p>
      <div style="display: flex; gap: 10px;">
        <button type="button" id="exit-cancel-btn" class="btn btn-soft btn-full">繼續闖關</button>
        <button type="button" id="exit-confirm-btn" class="btn btn-coral btn-full">返回首頁</button>
      </div>
    </div>
  </div>

  <!-- ==========================================================
       彈窗 2：8 分鐘時間到提醒
  ========================================================== -->
  <div id="modal-timeup" class="modal-backdrop hidden">
    <div class="modal-box modal-box-sm">
      <div style="font-size: 50px; margin-bottom: 6px;">⏰</div>
      <h3 style="margin: 0 0 8px; font-size: 24px; font-weight: 900;">8 分鐘時間到啦！</h3>
      <p style="margin: 0 0 20px; font-size: 17px; color: #475569; font-weight: 700;">
        你表現得非常棒！現在要領取榮譽證書，還是繼續完成餘下題目呢？
      </p>
      <div style="display: flex; flex-direction: column; gap: 10px;">
        <button type="button" id="timeup-finish-btn" class="btn btn-gold btn-full">🏆 立即查看榮譽證書</button>
        <button type="button" id="timeup-continue-btn" class="btn btn-emerald btn-full">✏️ 繼續完成餘下題目</button>
      </div>
    </div>
  </div>

  <!-- ==========================================================
       彈窗 3：👨‍🏫 老師專區 / QR Code 面板
  ========================================================== -->
  <div id="modal-teacher" class="modal-backdrop hidden">
    <div class="modal-box">
      <div class="modal-head">
        <div>
          <strong style="font-size: 20px;">👨‍🏫 老師專區 / 課堂二維碼</strong>
          <div style="font-size: 13px; color: #cbd5e1;">投影 QR Code ‧ 課堂開關 ‧ 快速試玩 ‧ 參考答案</div>
        </div>
        <button type="button" id="close-teacher-btn" class="btn btn-soft btn-sm">✕ 關閉</button>
      </div>

      <div class="modal-body">
        <!-- 區塊 A：QR Code 生成與投影 -->
        <div class="teacher-section">
          <h3>📱 課堂掃描二維碼（iPad 專用）</h3>

          <div id="qr-notice" class="hint-box hidden" style="margin: 0 0 12px; font-size: 15px;">
            💡 提示：目前偵測到本機檔案或預覽環境。將本網頁上傳至 GitHub Pages 或學校網頁後，把公開網址貼在下方即可生成學生 iPad 掃描用的二維碼（下方現正展示示例網址的二維碼供確認）。
          </div>

          <input
            id="qr-url-input"
            class="text-input"
            type="text"
            placeholder="請貼上公開網址，例如：https://school.edu.hk/starlight.html"
            autocomplete="off"
            autocorrect="off"
            autocapitalize="off"
            spellcheck="false"
            style="font-size: 16px; min-height: 46px;"
          />

          <div style="display: flex; flex-wrap: wrap; gap: 8px; margin-top: 10px;">
            <button type="button" id="qr-update-btn" class="btn btn-sky btn-sm">🔄 更新二維碼</button>
            <button type="button" id="qr-copy-btn" class="btn btn-soft btn-sm">📋 複製網址</button>
            <button type="button" id="qr-fullscreen-btn" class="btn btn-gold btn-sm">📺 全螢幕投影二維碼</button>
          </div>

          <div class="qr-preview-frame">
            <div class="qr-img-wrap">
              <img id="qr-img" src="" alt="學生掃描用二維碼" />
            </div>
            <div id="qr-url-display" style="margin-top: 10px; font-size: 13px; color: #475569; word-break: break-all; text-align: center;"></div>
          </div>
        </div>

        <!-- 區塊 B：課堂設定開關 -->
        <div class="teacher-section">
          <h3>⚙️ 課堂設定開關</h3>
          <label class="switch-row">
            <span>⏱️ 8 分鐘限時倒數（關閉則不限時）</span>
            <input type="checkbox" id="set-timer" checked />
          </label>
          <label class="switch-row">
            <span>💡 學生「錦囊提示」按鈕（不透露答案字詞）</span>
            <input type="checkbox" id="set-hints" checked />
          </label>
          <label class="switch-row" style="margin-bottom: 0;">
            <span>🔀 第一關 13 題隨機次序出題</span>
            <input type="checkbox" id="set-shuffle" />
          </label>
        </div>

        <!-- 區塊 C：快速試玩跳關 -->
        <div class="teacher-section">
          <h3>⚡ 快速試玩跳關（課前預覽用）</h3>
          <div class="jump-grid">
            <button type="button" id="jump-s1" class="btn btn-emerald btn-sm">⛰️ 跳至第一關（字詞）</button>
            <button type="button" id="jump-s2" class="btn btn-violet btn-sm">🌉 跳至第二關（句式）</button>
            <button type="button" id="jump-s3" class="btn btn-sky btn-sm">🔎 跳至第三關（省略號）</button>
            <button type="button" id="jump-report" class="btn btn-gold btn-sm">🏆 預覽證書結算頁</button>
          </div>
        </div>

        <!-- 區塊 D：完整參考答案表（折疊展開） -->
        <div class="teacher-section" style="margin-bottom: 0;">
          <div style="display: flex; justify-content: space-between; align-items: center; gap: 8px; flex-wrap: wrap;">
            <h3 style="margin: 0;">📖 完整參考答案表</h3>
            <button type="button" id="toggle-answers-btn" class="btn btn-soft btn-sm">展開答案表 ▼</button>
          </div>
          <div id="answers-panel" class="hidden" style="margin-top: 12px;"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- ==========================================================
       彈窗 4：📺 全螢幕高清投影二維碼
  ========================================================== -->
  <div id="modal-qr-fullscreen" class="qr-fullscreen hidden">
    <button type="button" id="close-qr-fullscreen-btn" class="btn btn-gold btn-sm qr-fs-close">✕ 關閉全螢幕</button>
    <span class="badge badge-gold" style="font-size: 16px;">✨ 小四中文 ‧ 8 分鐘限時大挑戰</span>
    <h2 style="margin: 12px 0 4px; font-size: clamp(24px, 4vw, 38px); font-weight: 900;">
      請用 iPad 掃描二維碼進入《星光語文探險島》
    </h2>
    <div class="qr-fs-board">
      <img id="qr-fullscreen-img" src="" alt="全螢幕投影二維碼" />
    </div>
    <div id="qr-fullscreen-url" style="font-size: 16px; color: #bae6fd; word-break: break-all; max-width: 90%;"></div>
  </div>

  <!-- ==========================================================
       JAVASCRIPT：純淨、模組化、零崩潰互動邏輯
  ========================================================== -->
  <script>
    (function () {
      'use strict';

      /* ----------------------------------------------------------
         1. 安全工具函數與 Web Audio 音效引擎（全部 try/catch 保護）
      ---------------------------------------------------------- */
      function byId(id) {
        return document.getElementById(id);
      }

      function on(id, evt, handler) {
        var el = byId(id);
        if (el) {
          el.addEventListener(evt, handler);
        }
      }

      var Sound = {
        muted: false,
        ctx: null,
        playTone: function (freq, dur, type, vol, delay) {
          if (this.muted) return;
          try {
            var AudioCtx = window.AudioContext || window.webkitAudioContext;
            if (!AudioCtx) return;
            if (!this.ctx) this.ctx = new AudioCtx();
            if (this.ctx.state === 'suspended') this.ctx.resume();
            var start = this.ctx.currentTime + (delay || 0);
            var osc = this.ctx.createOscillator();
            var gain = this.ctx.createGain();
            osc.type = type || 'sine';
            osc.frequency.setValueAtTime(freq, start);
            gain.gain.setValueAtTime(0.001, start);
            gain.gain.exponentialRampToValueAtTime(vol || 0.12, start + 0.015);
            gain.gain.exponentialRampToValueAtTime(0.001, start + dur);
            osc.connect(gain);
            gain.connect(this.ctx.destination);
            osc.start(start);
            osc.stop(start + dur + 0.02);
          } catch (e) {
            // 在 iPad 靜音或受限模式下安靜略過，絕不拋出錯誤
          }
        },
        click: function () {
          this.playTone(520, 0.06, 'triangle', 0.08, 0);
        },
        correct: function () {
          this.playTone(523.25, 0.12, 'triangle', 0.13, 0);
          this.playTone(659.25, 0.12, 'triangle', 0.13, 0.09);
          this.playTone(783.99, 0.22, 'sine', 0.15, 0.18);
        },
        wrong: function () {
          this.playTone(300, 0.15, 'sine', 0.11, 0);
          this.playTone(240, 0.2, 'sine', 0.11, 0.12);
        },
        hint: function () {
          this.playTone(660, 0.09, 'sine', 0.09, 0);
          this.playTone(880, 0.14, 'sine', 0.09, 0.08);
        },
        victory: function () {
          this.playTone(523.25, 0.14, 'triangle', 0.14, 0);
          this.playTone(659.25, 0.14, 'triangle', 0.14, 0.12);
          this.playTone(783.99, 0.14, 'triangle', 0.14, 0.24);
          this.playTone(1046.5, 0.3, 'triangle', 0.16, 0.36);
        }
      };

      /* ----------------------------------------------------------
         2. 完整題庫資料（共 23 題）
      ---------------------------------------------------------- */
      // 第一關：13 個不供詞填充詞語
      var STAGE1_DATA = [
        {
          answer: '燦爛',
          len: 2,
          before: '雨過天晴後，陽光顯得格外',
          after: '，把整個校園照得金光閃閃。',
          hint: '形容光彩鮮明耀眼，也常形容笑容。',
          note: '「燦爛」形容光彩鮮明耀眼，兩個字都是「火」部。'
        },
        {
          answer: '醜惡',
          len: 2,
          before: '童話裏的壞巫婆不但樣子可怕，內心更是十分',
          after: '，總愛欺負弱小。',
          hint: '形容外貌或品行非常不好，與「美麗、善良」相反。',
          note: '「醜惡」形容外貌難看或心腸邪惡。'
        },
        {
          answer: '窮困',
          len: 2,
          before: '雖然他童年時家境十分',
          after: '，連買新鞋的錢也沒有，卻依然非常努力讀書。',
          hint: '形容生活貧窮、缺乏金錢。',
          note: '「窮困」指生活貧窮困難。'
        },
        {
          answer: '作樂',
          len: 2,
          before: '明天就要中文測驗了，弟弟卻只顧着玩電子遊戲，終日尋歡',
          after: '，完全不肯溫習。',
          hint: '指尋找歡樂、盡情玩樂，常與「尋歡」連用。',
          note: '「尋歡作樂」指只顧尋找歡樂、沉迷玩樂。'
        },
        {
          answer: '搧',
          len: 1,
          before: '夏天停電時熱得滿頭大汗，婆婆拿著大蒲扇不停替我',
          after: '風降溫。',
          hint: '用手搖動扇子等物品生風，注意是「手部」旁！',
          note: '「搧」是動詞，表示用手搖動扇子生風，所以用提手旁（扌）。',
          nudgeInput: '扇',
          nudgeMsg: '差一點點！這裏是動作，記得用「扌」手部的字喔，請再試一次！'
        },
        {
          answer: '相安無事',
          len: 4,
          before: '經過老師耐心的調解，原本爭吵的兩位同學終於和好如初，從此',
          after: '。',
          hint: '指彼此相處平安，沒有再發生衝突或事故。',
          note: '「相安無事」形容彼此和平相處，沒有衝突。'
        },
        {
          answer: '挺身而出',
          len: 4,
          before: '看見小同學被頑皮的學生欺負，正義感十足的班長立刻',
          after: '，上前保護他。',
          hint: '形容遇到困難或危急時，勇敢地站出來幫忙或承擔。',
          note: '「挺身而出」形容勇敢地站出來承擔或保護他人。'
        },
        {
          answer: '息事寧人',
          len: 4,
          before: '面對鄰居的誤會，爸爸不想把事情鬧大，決定主動道歉退讓，好讓大家',
          after: '。',
          hint: '指設法平息爭執，令雙方相安無事、不再糾紛。',
          note: '「息事寧人」指平息紛爭，讓大家恢復安寧。'
        },
        {
          answer: '閃爍',
          len: 2,
          before: '漆黑的夜空中，無數顆小星星一閃一滅地',
          after: '着美麗的光芒。',
          hint: '形容光亮忽明忽暗、動搖不定地發光。',
          note: '「閃爍」形容光亮忽明忽暗地發光，第二字是「火」部。'
        },
        {
          answer: '和藹',
          len: 2,
          before: '校長每天早上都會微笑着向同學問好，態度非常',
          after: '可親，大家都喜歡他。',
          hint: '形容態度溫和、容易親近，常與「可親」連用。',
          note: '「和藹」形容態度溫和親切，「藹」字是草字頭（艹）。'
        },
        {
          answer: '憂愁',
          len: 2,
          before: '自從心愛的小狗走失後，妹妹每天眉頭深鎖，臉上滿是',
          after: '，吃不下飯。',
          hint: '形容心裏擔憂、發愁、不開心。',
          note: '「憂愁」形容心裏非常擔憂發愁。'
        },
        {
          answer: '暖和',
          len: 2,
          before: '寒冷的冬天裏，喝完媽媽煲的熱湯，全身頓時變得',
          after: '起來。',
          hint: '形容天氣或身體溫暖舒適。',
          note: '「暖和」形容溫暖舒適。'
        },
        {
          answer: '饑餓',
          len: 2,
          before: '我們遠足走了四個小時，到了中午肚子咕咕作響，大家都感到十分',
          after: '。',
          hint: '指肚子非常餓、很想吃東西。',
          note: '「饑餓」指肚子非常餓，兩個字都是「飠」部。',
          altAccept: '飢餓',
          altMsg: '答對了！溫馨提示：課本標準寫法是「饑餓」喔！'
        }
      ];

      // 第二關：「那麼⋯⋯那麼⋯⋯」句式運用（4 題）
      var STAGE2_DATA = [
        {
          type: 'mcq',
          tag: '題目 1 ‧ 辨別正誤',
          prompt: '以下哪一句最恰當運用了「那麼⋯⋯那麼⋯⋯」句式？',
          options: [
            { label: 'A', text: '夜空中的星星那麼閃爍，那麼迷人，教人看得入神。', ok: true, fb: '答對了！「閃爍」和「迷人」是星星兩個並列的優美特點，運用得非常恰當！' },
            { label: 'B', text: '因為今天那麼下雨，那麼我帶了雨傘。', ok: false, fb: '「因為……所以……」才表示因果關係，「那麼⋯⋯那麼⋯⋯」用來並列描寫兩個特點喔！' },
            { label: 'C', text: '只要你那麼努力溫習，那麼就會考好成績。', ok: false, fb: '「只要……就……」是條件句，這裏不需要加上兩個「那麼」喔！' },
            { label: 'D', text: '哥哥那麼吃了一碗飯，那麼喝了一杯水。', ok: false, fb: '「那麼」後面一般接形容詞或描寫狀態的詞語，不能直接放在「吃了一碗飯」這類動作前喔！' }
          ],
          correctAnswer: 'A. 夜空中的星星那麼閃爍，那麼迷人，教人看得入神。'
        },
        {
          type: 'pair',
          tag: '題目 2 ‧ 詞語配對點選',
          prompt: '點擊下方詞語卡，把合適的詞語填入空位完成句子（點擊空位可取消重選）：',
          parts: ['秋天的微風總是那麼', '，天上的白雲也那麼', '，最適合去郊遊了。'],
          cards: ['涼爽', '潔白', '醜惡', '吵鬧'],
          answerPair: ['涼爽', '潔白'],
          explanation: '秋天的「微風」配「涼爽」，天上的「白雲」配「潔白」，生動寫出秋高氣爽的美景！'
        },
        {
          type: 'reorder',
          tag: '題目 3 ‧ 詞卡重組句子',
          prompt: '請依次點擊下方 5 張詞卡，排成通順的「那麼⋯⋯那麼⋯⋯」句子：',
          shuffledCards: ['那麼親切，', '令大家感到十分暖和。', '婆婆的笑容', '那麼和藹，', '總是'],
          validSentences: [
            '婆婆的笑容總是那麼和藹，那麼親切，令大家感到十分暖和。',
            '婆婆的笑容總是那麼親切，那麼和藹，令大家感到十分暖和。'
          ],
          correctDisplay: '婆婆的笑容總是那麼和藹，那麼親切，令大家感到十分暖和。',
          explanation: '先寫主語「婆婆的笑容總是」，再用「那麼和藹，那麼親切，」並列形容，最後說明感受「令大家感到十分暖和。」'
        },
        {
          type: 'creative',
          tag: '題目 4 ‧ 小小作家造句挑戰',
          prompt: '請你運用「那麼⋯⋯那麼⋯⋯」寫一句完整的句子（可點擊下方靈感主題參考）：',
          topics: [
            { name: '☀️ 校園的陽光', sample: '清晨校園的陽光那麼燦爛，那麼暖和，照得同學們精神奕奕。' },
            { name: '👩‍🏫 和藹的老師', sample: '陳老師的笑容那麼和藹，聲音那麼溫柔，大家都十分喜歡上她的課。' },
            { name: '🍰 美味的下午茶', sample: '這塊新鮮出爐的蛋糕那麼鬆軟，那麼香甜，讓人吃了一口還想再吃。' }
          ]
        }
      ];

      // 第三關：省略號（⋯⋯）兩種用法（6 題）
      var STAGE3_DATA = [
        {
          type: 'classify',
          tag: '題目 1 ‧ 用法分類',
          sentence: '媽媽到街市買了很多水果，有蘋果、橙、香蕉、雪梨⋯⋯',
          answer: 'examples',
          explanation: '句子列舉了數種水果後加上「⋯⋯」，表示還有很多其他水果沒有說完，屬於「例子未說完」。'
        },
        {
          type: 'classify',
          tag: '題目 2 ‧ 用法分類',
          sentence: '志豪跑得上氣不接下氣，喘着氣說：「老師⋯⋯我⋯⋯我終於跑完步了！」',
          answer: 'stutter',
          explanation: '志豪跑完步氣喘吁吁，用「⋯⋯」表現他喘着氣、說話一頓一頓的樣子，屬於「說話斷斷續續」。'
        },
        {
          type: 'classify',
          tag: '題目 3 ‧ 用法分類',
          sentence: '弟弟低着頭，吞吞吐吐地說：「對不起⋯⋯我不是故意⋯⋯弄壞你的玩具的⋯⋯」',
          answer: 'stutter',
          explanation: '弟弟內疚又緊張，吞吞吐吐地說話，用「⋯⋯」表現「說話斷斷續續」。'
        },
        {
          type: 'classify',
          tag: '題目 4 ‧ 用法分類',
          sentence: '圖書館裏有各種各樣的圖書，包括童話故事、科學百科、偵探小說、漫畫⋯⋯',
          answer: 'examples',
          explanation: '句子列舉了不同類別的圖書，用「⋯⋯」表示還有很多種類的書未列完，屬於「例子未說完」。'
        },
        {
          type: 'mcq',
          tag: '題目 5 ‧ 標點捉錯處',
          prompt: '以下哪一句的省略號運用完全正確？',
          options: [
            { label: 'A', text: '文具店售賣鉛筆、擦膠、間尺⋯⋯等等文具。', ok: false, fb: '小心常見陷阱！省略號與「等等」意思重複，不可以同時使用喔！' },
            { label: 'B', text: '公園裏開滿了鮮花，有玫瑰、鬱金香、向日葵⋯⋯', ok: true, fb: '完全正確！並列鮮花之間用頓號「、」，結尾用「⋯⋯」準確表示例子未說完，也沒有多餘的「等等」！' },
            { label: 'C', text: '妹妹緊張地說：「我……等等……我忘記帶功課了。」', ok: false, fb: '這句加上了多餘的「等等」，影響了原本緊張停頓的自然語氣喔！' }
          ],
          correctAnswer: 'B. 公園裏開滿了鮮花，有玫瑰、鬱金香、向日葵⋯⋯'
        },
        {
          type: 'slot',
          tag: '題目 6 ‧ 互動放省略號',
          prompt: '請點擊最適合放入省略號「⋯⋯」表示「例子未說完」的位置：',
          segments: ['暑假時我去了海洋公園', '迪士尼樂園', '香港濕地公園', '玩得樂而忘返。'],
          slotLabels: ['位置A', '位置B', '位置C'],
          correctSlot: 2,
          wrongHints: [
            '「位置A」在第一個和第二個景點之間，應該放頓號「、」，不是省略號喔！',
            '「位置B」在第二個和第三個景點之間，應該放頓號「、」，不是省略號喔！'
          ],
          explanation: '位置 A 和 B 應用頓號「、」分隔列舉項目，位置 C 放在所有列舉項目的末尾，才用「⋯⋯」表示例子未說完！'
        }
      ];

      /* ----------------------------------------------------------
         3. 遊戲狀態管理
      ---------------------------------------------------------- */
      var TOTAL_TIME_SEC = 8 * 60; // 480 秒
      var DEMO_URL = 'https://example.edu.hk/starlight-chinese-game.html';

      var state = {
        settings: {
          timerEnabled: true,
          hintsEnabled: true,
          shuffleStage1: false
        },
        studentName: '小探險家',
        stage: 1,
        index: 0,
        stage1Questions: [],
        score: 0,
        s1Correct: 0,
        s2Correct: 0,
        s3Correct: 0,
        s1ReviewList: [], // 第一關曾答錯或查看答案的詞語清單
        studentSentence: '',
        answered: false,
        usedWrongOnce: false,
        // 互動暫存
        pairSlots: [null, null],
        reorderIndices: [],
        // 計時器
        secondsLeft: TOTAL_TIME_SEC,
        overtimeSec: 0,
        isOvertime: false,
        timeUpNotified: false,
        timerId: null
      };

      /* ----------------------------------------------------------
         4. 畫面切換、計時器與 HUD 更新
      ---------------------------------------------------------- */
      function showScreen(screenId) {
        var ids = ['screen-welcome', 'screen-stage-intro', 'screen-game', 'screen-report'];
        for (var i = 0; i < ids.length; i++) {
          var el = byId(ids[i]);
          if (el) el.classList.add('hidden');
        }
        var target = byId(screenId);
        if (target) target.classList.remove('hidden');

        var hud = byId('game-hud');
        if (hud) {
          if (screenId === 'screen-game' || screenId === 'screen-stage-intro') {
            hud.classList.remove('hidden');
          } else {
            hud.classList.add('hidden');
          }
        }
        window.scrollTo(0, 0);
      }

      function formatTime(sec) {
        var m = Math.floor(sec / 60);
        var s = sec % 60;
        return (m < 10 ? '0' : '') + m + ':' + (s < 10 ? '0' : '') + s;
      }

      function stopTimer() {
        if (state.timerId !== null) {
          clearInterval(state.timerId);
          state.timerId = null;
        }
      }

      function updateTimerUI() {
        var timerEl = byId('hud-timer');
        var boxEl = byId('hud-timer-box');
        if (!timerEl || !boxEl) return;

        if (!state.settings.timerEnabled) {
          timerEl.textContent = '不限時';
          boxEl.classList.remove('urgent');
          return;
        }
        if (state.isOvertime) {
          timerEl.textContent = '+' + formatTime(state.overtimeSec);
          boxEl.classList.remove('urgent');
          return;
        }
        timerEl.textContent = formatTime(state.secondsLeft);
        if (state.secondsLeft <= 60 && state.secondsLeft > 0) {
          boxEl.classList.add('urgent');
        } else {
          boxEl.classList.remove('urgent');
        }
      }

      function startTimer() {
        stopTimer();
        updateTimerUI();
        if (!state.settings.timerEnabled) return;

        state.timerId = setInterval(function () {
          if (!state.isOvertime) {
            if (state.secondsLeft > 0) {
              state.secondsLeft--;
              updateTimerUI();
              if (state.secondsLeft === 0 && !state.timeUpNotified) {
                state.timeUpNotified = true;
                stopTimer();
                Sound.wrong();
                var m = byId('modal-timeup');
                if (m) m.classList.remove('hidden');
              }
            }
          } else {
            state.overtimeSec++;
            updateTimerUI();
          }
        }, 1000);
      }

      function updateHUD() {
        var stageLabel = byId('hud-stage-label');
        var progText = byId('hud-progress-text');
        var scoreEl = byId('hud-score');
        var fillEl = byId('hud-progress-fill');

        var stageTitles = {
          1: '⛰️ 第一關：神秘字詞谷',
          2: '🌉 第二關：魔法句式橋',
          3: '🔎 第三關：標點偵探社'
        };
        var stageTotals = { 1: 13, 2: 4, 3: 6 };
        var offsetBefore = { 1: 0, 2: 13, 3: 17 };

        var totalInStage = stageTotals[state.stage] || 13;
        var currentNum = Math.min(state.index + 1, totalInStage);
        var doneCount = offsetBefore[state.stage] + state.index;
        var pct = Math.max(4, Math.round((doneCount / 23) * 100));

        if (stageLabel) stageLabel.textContent = stageTitles[state.stage];
        if (progText) progText.textContent = '第 ' + currentNum + ' / ' + totalInStage + ' 題';
        if (scoreEl) scoreEl.textContent = String(state.score);
        if (fillEl) fillEl.style.width = pct + '%';
      }

      function setMascot(emoji, text) {
        var e = byId('mascot-emoji');
        var b = byId('mascot-bubble');
        if (e) e.textContent = emoji;
        if (b) b.textContent = text;
      }

      function toggleSound() {
        Sound.muted = !Sound.muted;
        var hudBtn = byId('hud-sound-btn');
        var welBtn = byId('welcome-sound-btn');
        if (hudBtn) hudBtn.textContent = Sound.muted ? '🔇' : '🔊';
        if (welBtn) welBtn.textContent = Sound.muted ? '🔇 音效：關' : '🔊 音效：開';
        if (!Sound.muted) Sound.click();
      }

      /* ----------------------------------------------------------
         5. 遊戲初始化與關卡過場
      ---------------------------------------------------------- */
      function resetGame(startStage) {
        var nameInput = byId('student-name-input');
        var val = nameInput ? nameInput.value.trim() : '';
        state.studentName = val || '小探險家';

        state.stage = startStage || 1;
        state.index = 0;
        state.score = 0;
        state.s1Correct = 0;
        state.s2Correct = 0;
        state.s3Correct = 0;
        state.s1ReviewList = [];
        state.studentSentence = '';
        state.secondsLeft = TOTAL_TIME_SEC;
        state.overtimeSec = 0;
        state.isOvertime = false;
        state.timeUpNotified = false;

        // 複製並依老師設定決定是否隨機排序第一關
        state.stage1Questions = STAGE1_DATA.slice();
        if (state.settings.shuffleStage1) {
          for (var i = state.stage1Questions.length - 1; i > 0; i--) {
            var j = Math.floor(Math.random() * (i + 1));
            var tmp = state.stage1Questions[i];
            state.stage1Questions[i] = state.stage1Questions[j];
            state.stage1Questions[j] = tmp;
          }
        }
      }

      function showStageIntro(stageNum) {
        state.stage = stageNum;
        state.index = 0;
        updateHUD();

        var configs = {
          1: {
            badge: '第一關 ‧ 共 13 題',
            badgeClass: 'badge badge-emerald',
            emoji: '⛰️',
            title: '神秘字詞谷：不供詞填充',
            desc: '這裏沒有詞庫提示，全靠你平時累積的中文詞彙實力！細心閱讀句子，寫出最準確的繁體字詞。',
            tips: '💡 過關秘訣：<br>1. 留意方格數目（1字、2字或4字），方便檢查字數。<br>2. 寫錯字時可按「再試一次」修改，想不起可善用「錦囊提示」。'
          },
          2: {
            badge: '第二關 ‧ 共 4 題',
            badgeClass: 'badge badge-violet',
            emoji: '🌉',
            title: '魔法句式橋：「那麼⋯⋯那麼⋯⋯」',
            desc: '太棒了！接下來要運用「那麼⋯⋯那麼⋯⋯」句式修好魔法橋，最後還有一道小小作家造句挑戰！',
            tips: '💡 過關秘訣：<br>1. 「那麼⋯⋯那麼⋯⋯」用來並列描寫同一事物的兩個相配特點。<br>2. 最後一題寫下的原創佳句，會完整印在你的榮譽證書上！'
          },
          3: {
            badge: '第三關 ‧ 共 6 題',
            badgeClass: 'badge badge-sky',
            emoji: '🔎',
            title: '標點偵探社：省略號（⋯⋯）大挑戰',
            desc: '最後衝刺！戴上偵探帽，分辨省略號「⋯⋯」的兩種用法，並且找出隱藏的標點陷阱！',
            tips: '💡 兩種學過的用法：<br>1. 🗣️ <strong>說話斷斷續續</strong>：表現氣喘、緊張、猶豫或虛弱的語氣。<br>2. 📚 <strong>例子未說完</strong>：列舉同類事物末尾加上「⋯⋯」（不可與「等等」同用）。'
          }
        };

        var cfg = configs[stageNum];
        var b = byId('intro-badge');
        if (b) {
          b.textContent = cfg.badge;
          b.className = cfg.badgeClass;
        }
        byId('intro-emoji').textContent = cfg.emoji;
        byId('intro-title').textContent = cfg.title;
        byId('intro-desc').textContent = cfg.desc;
        byId('intro-tips').innerHTML = cfg.tips;

        showScreen('screen-stage-intro');
      }

      function advanceQuestion() {
        Sound.click();
        state.index++;
        if (state.stage === 1 && state.index >= state.stage1Questions.length) {
          Sound.victory();
          showStageIntro(2);
        } else if (state.stage === 2 && state.index >= STAGE2_DATA.length) {
          Sound.victory();
          showStageIntro(3);
        } else if (state.stage === 3 && state.index >= STAGE3_DATA.length) {
          showReport();
        } else {
          renderQuestion();
        }
      }

      function renderQuestion() {
        state.answered = false;
        state.usedWrongOnce = false;
        state.pairSlots = [null, null];
        state.reorderIndices = [];
        updateHUD();

        if (state.stage === 1) renderStage1();
        else if (state.stage === 2) renderStage2();
        else renderStage3();
      }

      /* ----------------------------------------------------------
         6. 第一關：不供詞填充 (13 題)
      ---------------------------------------------------------- */
      function renderStage1() {
        var q = state.stage1Questions[state.index];
        var card = byId('question-card');
        if (!card || !q) return;

        setMascot('🦉', '第 ' + (state.index + 1) + ' 題：需要填 ' + q.len + ' 個字，細心讀句子喔！');

        var blankMarks = '';
        var boxesHtml = '';
        for (var i = 0; i < q.len; i++) {
          blankMarks += '＿';
          boxesHtml += '<div class="char-box" data-box="' + i + '"></div>';
        }

        var hintBtnHtml = state.settings.hintsEnabled
          ? '<button type="button" id="s1-hint-btn" class="btn btn-soft btn-sm">💡 錦囊提示</button>'
          : '';

        var nextText = state.index < state.stage1Questions.length - 1
          ? '下一題 ➡️'
          : '前往第二關：魔法句式橋 🌉';

        card.innerHTML =
          '<div class="q-header">' +
            '<span class="badge badge-emerald">⛰️ 不供詞填充 ‧ 填 ' + q.len + ' 個字</span>' +
            hintBtnHtml +
          '</div>' +
          '<div class="sentence-box sentence-box-s1">' +
            '<span>' + q.before + '</span>' +
            '<span id="s1-inline-blank" class="inline-blank">【' + blankMarks + '】</span>' +
            '<span>' + q.after + '</span>' +
          '</div>' +
          '<div id="s1-char-boxes" class="char-boxes" aria-hidden="true">' + boxesHtml + '</div>' +
          '<div class="input-row">' +
            '<input id="s1-input" class="text-input" type="text" placeholder="請輸入或手寫 ' + q.len + ' 個字" ' +
              'autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false" style="text-align:center;" />' +
            '<button type="button" id="s1-submit-btn" class="btn btn-emerald" style="white-space:nowrap;">提交答案 ✓</button>' +
          '</div>' +
          '<div id="s1-hint-box" class="hint-box hidden">💡 錦囊提示：' + q.hint + '</div>' +
          '<div id="s1-feedback" class="feedback-box hidden"></div>' +
          '<div id="s1-retry-row" class="action-row hidden">' +
            '<button type="button" id="s1-retry-btn" class="btn btn-sky">🔄 再試一次</button>' +
            '<button type="button" id="s1-reveal-btn" class="btn btn-soft">👀 查看答案並下一題</button>' +
          '</div>' +
          '<div id="s1-next-row" class="action-row hidden">' +
            '<button type="button" id="s1-next-btn" class="btn btn-gold">' + nextText + '</button>' +
          '</div>';

        var inputEl = byId('s1-input');
        var submitBtn = byId('s1-submit-btn');
        var hintBtn = byId('s1-hint-btn');
        var retryBtn = byId('s1-retry-btn');
        var revealBtn = byId('s1-reveal-btn');
        var nextBtn = byId('s1-next-btn');

        function syncBoxes() {
          var clean = inputEl.value.replace(/[\s\u3000]+/g, '');
          var chars = Array.from(clean);
          var boxes = card.querySelectorAll('.char-box');
          for (var k = 0; k < boxes.length; k++) {
            boxes[k].textContent = chars[k] || '';
            if (chars[k]) boxes[k].classList.add('filled');
            else boxes[k].classList.remove('filled');
          }
          var inline = byId('s1-inline-blank');
          if (inline && !state.answered) {
            inline.textContent = clean.length > 0 ? clean : '【' + blankMarks + '】';
          }
        }

        function recordStage1Review(userWord) {
          var already = false;
          for (var r = 0; r < state.s1ReviewList.length; r++) {
            if (state.s1ReviewList[r].answer === q.answer) {
              already = true;
              break;
            }
          }
          if (!already) {
            state.s1ReviewList.push({
              answer: q.answer,
              userAnswer: userWord || '（未填寫）',
              note: q.note
            });
          }
        }

        function handleStage1Submit() {
          if (state.answered) return;
          var raw = inputEl.value.replace(/[\s\u3000]+/g, '');
          var fb = byId('s1-feedback');
          var retryRow = byId('s1-retry-row');
          var nextRow = byId('s1-next-row');
          var inline = byId('s1-inline-blank');

          if (!raw) {
            Sound.wrong();
            fb.className = 'feedback-box fb-warn';
            fb.textContent = '✏️ 請先在輸入框寫下你的答案再提交喔！';
            fb.classList.remove('hidden');
            inputEl.focus();
            return;
          }

          // 特別機制 1：「扇」→ 溫馨提醒不扣分，讓學生改用提手旁「搧」
          if (q.nudgeInput && raw === q.nudgeInput) {
            Sound.hint();
            fb.className = 'feedback-box fb-warn';
            fb.textContent = '🖐️ ' + q.nudgeMsg;
            fb.classList.remove('hidden');
            retryRow.classList.add('hidden');
            setMascot('💡', '差一點點！留意左邊的部首，改好再按提交！');
            inputEl.focus();
            inputEl.select();
            return;
          }

          // 正確判定（含「飢餓」寬容計分並溫馨提醒課本寫法「饑餓」）
          var isExact = raw === q.answer;
          var isAlt = q.altAccept && raw === q.altAccept;
          if (isExact || isAlt) {
            state.answered = true;
            state.s1Correct++;
            var pts = state.usedWrongOnce ? 8 : 10;
            state.score += pts;
            updateHUD();
            Sound.correct();

            inputEl.disabled = true;
            submitBtn.disabled = true;
            retryRow.classList.add('hidden');

            if (inline) {
              inline.textContent = q.answer;
              inline.classList.add('solved');
            }

            var headline = isAlt ? q.altMsg : '答對了！寫得又快又準！';
            fb.className = 'feedback-box fb-ok';
            fb.innerHTML = '🎉 <strong>' + headline + '</strong>（+' + pts + ' 分）<div style="margin-top:6px; font-size:16px;">' + q.note + '</div>';
            fb.classList.remove('hidden');
            nextRow.classList.remove('hidden');
            setMascot('🌟', '太棒了！繼續保持這份好狀態！');
            return;
          }

          // 答錯：先不顯示答案，讓學生選擇「再試一次」或「查看答案並下一題」
          state.usedWrongOnce = true;
          Sound.wrong();
          var lenMsg = Array.from(raw).length !== q.len
            ? '（這題需要填 ' + q.len + ' 個字，你填了 ' + Array.from(raw).length + ' 個字）'
            : '';
          fb.className = 'feedback-box fb-err';
          fb.textContent = '🤔 這個答案還不太對喔！' + lenMsg + ' 你可以按「再試一次」修改，或查看正確答案。';
          fb.classList.remove('hidden');
          retryRow.classList.remove('hidden');
          setMascot('🦉', '沒關係，再細心讀一讀句子的線索！');
        }

        inputEl.addEventListener('input', syncBoxes);
        inputEl.addEventListener('keydown', function (e) {
          if (e.key === 'Enter' && !e.isComposing && e.keyCode !== 229) {
            e.preventDefault();
            if (!state.answered) handleStage1Submit();
            else advanceQuestion();
          }
        });

        submitBtn.addEventListener('click', handleStage1Submit);

        if (hintBtn) {
          hintBtn.addEventListener('click', function () {
            Sound.hint();
            var hBox = byId('s1-hint-box');
            if (hBox) hBox.classList.remove('hidden');
            hintBtn.disabled = true;
            setMascot('💡', '看看錦囊解釋，應該很快就能想起來！');
          });
        }

        retryBtn.addEventListener('click', function () {
          Sound.click();
          byId('s1-feedback').classList.add('hidden');
          byId('s1-retry-row').classList.add('hidden');
          inputEl.focus();
          inputEl.select();
        });

        revealBtn.addEventListener('click', function () {
          Sound.click();
          state.answered = true;
          var raw = inputEl.value.replace(/[\s\u3000]+/g, '');
          recordStage1Review(raw);

          inputEl.disabled = true;
          submitBtn.disabled = true;
          byId('s1-retry-row').classList.add('hidden');

          var inline = byId('s1-inline-blank');
          if (inline) {
            inline.textContent = q.answer;
            inline.classList.add('revealed');
          }

          var fb = byId('s1-feedback');
          fb.className = 'feedback-box fb-warn';
          fb.innerHTML = '📖 正確答案是：<strong>' + q.answer + '</strong><div style="margin-top:6px; font-size:16px;">' + q.note + '</div>';
          fb.classList.remove('hidden');
          byId('s1-next-row').classList.remove('hidden');
          setMascot('📖', '記住這個詞語，準備挑戰下一題吧！');
        });

        nextBtn.addEventListener('click', advanceQuestion);
      }

      /* ----------------------------------------------------------
         7. 第二關：「那麼⋯⋯那麼⋯⋯」句式運用 (4 題)
      ---------------------------------------------------------- */
      function renderStage2() {
        var q = STAGE2_DATA[state.index];
        var card = byId('question-card');
        if (!card || !q) return;

        var nextText = state.index < STAGE2_DATA.length - 1
          ? '下一題 ➡️'
          : '前往第三關：標點偵探社 🔎';

        // --- 題目 1：辨別正誤單選 ---
        if (q.type === 'mcq') {
          setMascot('🌉', '細心分辨哪一句正確使用「那麼⋯⋯那麼⋯⋯」並列描寫兩個特點！');
          var optsHtml = '';
          for (var i = 0; i < q.options.length; i++) {
            optsHtml +=
              '<button type="button" class="option-btn" data-idx="' + i + '">' +
                '<span class="opt-tag">' + q.options[i].label + '</span>' +
                '<span>' + q.options[i].text + '</span>' +
              '</button>';
          }

          card.innerHTML =
            '<div class="q-header"><span class="badge badge-violet">🌉 ' + q.tag + '</span></div>' +
            '<h3 style="margin:0 0 8px; font-size:22px; font-weight:900;">' + q.prompt + '</h3>' +
            '<div id="s2-opts" class="option-list">' + optsHtml + '</div>' +
            '<div id="s2-fb" class="feedback-box hidden"></div>' +
            '<div id="s2-next-row" class="action-row hidden">' +
              '<button type="button" id="s2-next-btn" class="btn btn-gold">' + nextText + '</button>' +
            '</div>';

          var btns = card.querySelectorAll('#s2-opts .option-btn');
          for (var b = 0; b < btns.length; b++) {
            btns[b].addEventListener('click', function () {
              if (state.answered) return;
              state.answered = true;
              var idx = parseInt(this.getAttribute('data-idx'), 10);
              var chosen = q.options[idx];
              var fb = byId('s2-fb');

              for (var k = 0; k < btns.length; k++) {
                btns[k].disabled = true;
                if (q.options[k].ok) btns[k].classList.add('opt-correct');
                else if (k === idx && !chosen.ok) btns[k].classList.add('opt-wrong');
              }

              if (chosen.ok) {
                state.s2Correct++;
                state.score += 15;
                updateHUD();
                Sound.correct();
                fb.className = 'feedback-box fb-ok';
                fb.innerHTML = '🎉 <strong>答對了！</strong>（+15 分）<div style="margin-top:6px;">' + chosen.fb + '</div>';
                setMascot('🌟', '好眼力！一下子就找出最通順的句子！');
              } else {
                Sound.wrong();
                fb.className = 'feedback-box fb-err';
                fb.innerHTML = '💡 <strong>這句不太合適喔！</strong><div style="margin-top:6px;">' + chosen.fb + '</div><div style="margin-top:8px; color:#065f46;">正確答案：' + q.correctAnswer + '</div>';
                setMascot('🦉', '記住這個重點，下一題繼續加油！');
              }
              fb.classList.remove('hidden');
              byId('s2-next-row').classList.remove('hidden');
            });
          }

          on('s2-next-btn', 'click', advanceQuestion);
          return;
        }

        // --- 題目 2：詞語配對點選填空 ---
        if (q.type === 'pair') {
          setMascot('🌉', '點擊下方詞語卡填入空位 ① 和 ②；點擊已填的空位可以取消重選！');
          var cardsHtml = '';
          for (var c = 0; c < q.cards.length; c++) {
            cardsHtml += '<button type="button" class="btn btn-soft" data-word="' + q.cards[c] + '">' + q.cards[c] + '</button>';
          }

          card.innerHTML =
            '<div class="q-header"><span class="badge badge-violet">🌉 ' + q.tag + '</span></div>' +
            '<h3 style="margin:0 0 14px; font-size:20px; font-weight:900;">' + q.prompt + '</h3>' +
            '<div class="sentence-box sentence-box-s2">' +
              '<span>' + q.parts[0] + '</span>' +
              '<button type="button" id="pair-slot-0" class="pair-slot-btn">①</button>' +
              '<span>' + q.parts[1] + '</span>' +
              '<button type="button" id="pair-slot-1" class="pair-slot-btn">②</button>' +
              '<span>' + q.parts[2] + '</span>' +
            '</div>' +
            '<div id="pair-cards" class="word-card-grid">' + cardsHtml + '</div>' +
            '<div class="action-row" style="justify-content:center; margin-top:20px;">' +
              '<button type="button" id="pair-submit-btn" class="btn btn-violet">提交檢查 ✓</button>' +
            '</div>' +
            '<div id="s2-fb" class="feedback-box hidden"></div>' +
            '<div id="s2-retry-row" class="action-row hidden">' +
              '<button type="button" id="pair-retry-btn" class="btn btn-sky">🔄 再試一次</button>' +
              '<button type="button" id="pair-reveal-btn" class="btn btn-soft">👀 查看答案並下一題</button>' +
            '</div>' +
            '<div id="s2-next-row" class="action-row hidden">' +
              '<button type="button" id="s2-next-btn" class="btn btn-gold">' + nextText + '</button>' +
            '</div>';

          function refreshPairUI() {
            for (var s = 0; s < 2; s++) {
              var slotBtn = byId('pair-slot-' + s);
              if (state.pairSlots[s]) {
                slotBtn.textContent = state.pairSlots[s];
                slotBtn.classList.add('filled');
              } else {
                slotBtn.textContent = s === 0 ? '①' : '②';
                slotBtn.classList.remove('filled');
              }
            }
            var poolBtns = card.querySelectorAll('#pair-cards button');
            for (var p = 0; p < poolBtns.length; p++) {
              var w = poolBtns[p].getAttribute('data-word');
              poolBtns[p].disabled = state.answered || state.pairSlots.indexOf(w) !== -1;
            }
          }

          var poolBtns = card.querySelectorAll('#pair-cards button');
          for (var p = 0; p < poolBtns.length; p++) {
            poolBtns[p].addEventListener('click', function () {
              if (state.answered) return;
              Sound.click();
              var word = this.getAttribute('data-word');
              if (!state.pairSlots[0]) state.pairSlots[0] = word;
              else if (!state.pairSlots[1]) state.pairSlots[1] = word;
              else state.pairSlots[1] = word;
              refreshPairUI();
            });
          }

          on('pair-slot-0', 'click', function () {
            if (state.answered || !state.pairSlots[0]) return;
            Sound.click();
            state.pairSlots[0] = null;
            refreshPairUI();
          });

          on('pair-slot-1', 'click', function () {
            if (state.answered || !state.pairSlots[1]) return;
            Sound.click();
            state.pairSlots[1] = null;
            refreshPairUI();
          });

          on('pair-submit-btn', 'click', function () {
            if (state.answered) return;
            var fb = byId('s2-fb');
            if (!state.pairSlots[0] || !state.pairSlots[1]) {
              Sound.wrong();
              fb.className = 'feedback-box fb-warn';
              fb.textContent = '✏️ 請先選好兩個詞語填滿 ① 和 ② 兩個空位喔！';
              fb.classList.remove('hidden');
              return;
            }
            if (state.pairSlots[0] === q.answerPair[0] && state.pairSlots[1] === q.answerPair[1]) {
              state.answered = true;
              state.s2Correct++;
              var pts = state.usedWrongOnce ? 10 : 15;
              state.score += pts;
              updateHUD();
              Sound.correct();
              byId('pair-submit-btn').classList.add('hidden');
              byId('s2-retry-row').classList.add('hidden');
              refreshPairUI();
              fb.className = 'feedback-box fb-ok';
              fb.innerHTML = '🎉 <strong>配對完全正確！</strong>（+' + pts + ' 分）<div style="margin-top:6px;">' + q.explanation + '</div>';
              fb.classList.remove('hidden');
              byId('s2-next-row').classList.remove('hidden');
              setMascot('🌟', '秋天的微風和白雲被你描寫得真美！');
            } else {
              state.usedWrongOnce = true;
              Sound.wrong();
              var swapped = state.pairSlots[0] === q.answerPair[1] && state.pairSlots[1] === q.answerPair[0];
              fb.className = 'feedback-box fb-err';
              fb.textContent = swapped
                ? '🤔 兩個詞語的位置對調了喔！想想「微風」配哪個詞，「白雲」配哪個詞？'
                : '🤔 再想想看：秋天的郊遊景色是舒適美麗的，應該選哪兩個正面詞語呢？';
              fb.classList.remove('hidden');
              byId('s2-retry-row').classList.remove('hidden');
            }
          });

          on('pair-retry-btn', 'click', function () {
            Sound.click();
            state.pairSlots = [null, null];
            refreshPairUI();
            byId('s2-fb').classList.add('hidden');
            byId('s2-retry-row').classList.add('hidden');
          });

          on('pair-reveal-btn', 'click', function () {
            Sound.click();
            state.answered = true;
            state.pairSlots = [q.answerPair[0], q.answerPair[1]];
            refreshPairUI();
            byId('pair-submit-btn').classList.add('hidden');
            byId('s2-retry-row').classList.add('hidden');
            var fb = byId('s2-fb');
            fb.className = 'feedback-box fb-warn';
            fb.innerHTML = '📖 正確答案：① <strong>涼爽</strong>、② <strong>潔白</strong><div style="margin-top:6px;">' + q.explanation + '</div>';
            fb.classList.remove('hidden');
            byId('s2-next-row').classList.remove('hidden');
          });

          on('s2-next-btn', 'click', advanceQuestion);
          return;
        }

        // --- 題目 3：點擊詞卡重組句子 ---
        if (q.type === 'reorder') {
          setMascot('🌉', '按順序點擊詞卡拼出通順句子！點上方已選詞卡可以放回下面。');
          var tilesHtml = '';
          for (var t = 0; t < q.shuffledCards.length; t++) {
            tilesHtml += '<button type="button" class="btn btn-soft" data-tile="' + t + '">' + q.shuffledCards[t] + '</button>';
          }

          card.innerHTML =
            '<div class="q-header"><span class="badge badge-violet">🌉 ' + q.tag + '</span></div>' +
            '<h3 style="margin:0 0 8px; font-size:20px; font-weight:900;">' + q.prompt + '</h3>' +
            '<div id="reorder-tray" class="reorder-tray">' +
              '<span style="color:#7c3aed; font-weight:700; font-size:16px;">點擊下方詞卡，句子會依序排在這裏⋯⋯</span>' +
            '</div>' +
            '<div id="reorder-pool" class="word-card-grid">' + tilesHtml + '</div>' +
            '<div id="reorder-ctrl" class="action-row" style="justify-content:center; margin-top:20px;">' +
              '<button type="button" id="reorder-reset-btn" class="btn btn-soft">↺ 重排</button>' +
              '<button type="button" id="reorder-submit-btn" class="btn btn-violet">檢查句子 ✓</button>' +
            '</div>' +
            '<div id="s2-fb" class="feedback-box hidden"></div>' +
            '<div id="s2-retry-row" class="action-row hidden">' +
              '<button type="button" id="reorder-retry-btn" class="btn btn-sky">🔄 再試一次</button>' +
              '<button type="button" id="reorder-reveal-btn" class="btn btn-soft">👀 查看答案並下一題</button>' +
            '</div>' +
            '<div id="s2-next-row" class="action-row hidden">' +
              '<button type="button" id="s2-next-btn" class="btn btn-gold">' + nextText + '</button>' +
            '</div>';

          function refreshReorderUI() {
            var tray = byId('reorder-tray');
            if (state.reorderIndices.length === 0) {
              tray.innerHTML = '<span style="color:#7c3aed; font-weight:700; font-size:16px;">點擊下方詞卡，句子會依序排在這裏⋯⋯</span>';
            } else {
              tray.innerHTML = '';
              for (var r = 0; r < state.reorderIndices.length; r++) {
                (function (pos, tileIdx) {
                  var btn = document.createElement('button');
                  btn.type = 'button';
                  btn.className = 'btn btn-violet btn-sm';
                  btn.textContent = q.shuffledCards[tileIdx];
                  btn.disabled = state.answered;
                  btn.addEventListener('click', function () {
                    if (state.answered) return;
                    Sound.click();
                    state.reorderIndices.splice(pos, 1);
                    refreshReorderUI();
                  });
                  tray.appendChild(btn);
                })(r, state.reorderIndices[r]);
              }
            }

            var poolBtns = card.querySelectorAll('#reorder-pool button');
            for (var p = 0; p < poolBtns.length; p++) {
              var idx = parseInt(poolBtns[p].getAttribute('data-tile'), 10);
              poolBtns[p].disabled = state.answered || state.reorderIndices.indexOf(idx) !== -1;
            }
          }

          var poolBtns = card.querySelectorAll('#reorder-pool button');
          for (var p = 0; p < poolBtns.length; p++) {
            poolBtns[p].addEventListener('click', function () {
              if (state.answered) return;
              Sound.click();
              var idx = parseInt(this.getAttribute('data-tile'), 10);
              if (state.reorderIndices.indexOf(idx) === -1) {
                state.reorderIndices.push(idx);
                refreshReorderUI();
              }
            });
          }

          on('reorder-reset-btn', 'click', function () {
            if (state.answered) return;
            Sound.click();
            state.reorderIndices = [];
            refreshReorderUI();
          });

          on('reorder-submit-btn', 'click', function () {
            if (state.answered) return;
            var fb = byId('s2-fb');
            if (state.reorderIndices.length < q.shuffledCards.length) {
              Sound.wrong();
              fb.className = 'feedback-box fb-warn';
              fb.textContent = '✏️ 還有詞卡未排上去喔，請把全部 5 張詞卡都排好！';
              fb.classList.remove('hidden');
              return;
            }
            var sentence = '';
            for (var i = 0; i < state.reorderIndices.length; i++) {
              sentence += q.shuffledCards[state.reorderIndices[i]];
            }
            if (q.validSentences.indexOf(sentence) !== -1) {
              state.answered = true;
              state.s2Correct++;
              var pts = state.usedWrongOnce ? 10 : 15;
              state.score += pts;
              updateHUD();
              Sound.correct();
              byId('reorder-ctrl').classList.add('hidden');
              byId('s2-retry-row').classList.add('hidden');
              refreshReorderUI();
              fb.className = 'feedback-box fb-ok';
              fb.innerHTML = '🎉 <strong>句子重組成功！</strong>（+' + pts + ' 分）<div style="margin-top:6px;">' + q.explanation + '</div>';
              fb.classList.remove('hidden');
              byId('s2-next-row').classList.remove('hidden');
              setMascot('🌟', '語感真出色！這句句子既通順又溫暖！');
            } else {
              state.usedWrongOnce = true;
              Sound.wrong();
              fb.className = 'feedback-box fb-err';
              fb.textContent = '🤔 排列次序還差一點點！先說「誰的笑容」→「總是」→「那麼……，那麼……，」→最後才是帶句號（。）的部分喔！';
              fb.classList.remove('hidden');
              byId('s2-retry-row').classList.remove('hidden');
            }
          });

          on('reorder-retry-btn', 'click', function () {
            Sound.click();
            state.reorderIndices = [];
            refreshReorderUI();
            byId('s2-fb').classList.add('hidden');
            byId('s2-retry-row').classList.add('hidden');
          });

          on('reorder-reveal-btn', 'click', function () {
            Sound.click();
            state.answered = true;
            byId('reorder-ctrl').classList.add('hidden');
            byId('s2-retry-row').classList.add('hidden');
            refreshReorderUI();
            var fb = byId('s2-fb');
            fb.className = 'feedback-box fb-warn';
            fb.innerHTML = '📖 正確順序：<strong>' + q.correctDisplay + '</strong><div style="margin-top:6px;">' + q.explanation + '</div>';
            fb.classList.remove('hidden');
            byId('s2-next-row').classList.remove('hidden');
          });

          on('s2-next-btn', 'click', advanceQuestion);
          return;
        }

        // --- 題目 4：小小作家造句挑戰 ---
        if (q.type === 'creative') {
          setMascot('✍️', '輪到你當小小作家！用「那麼⋯⋯那麼⋯⋯」寫一句精彩句子，會印在證書上喔！');
          var chipsHtml = '';
          for (var i = 0; i < q.topics.length; i++) {
            chipsHtml += '<button type="button" class="topic-chip" data-topic="' + i + '">' + q.topics[i].name + '</button>';
          }

          card.innerHTML =
            '<div class="q-header"><span class="badge badge-gold">✍️ ' + q.tag + '</span></div>' +
            '<h3 style="margin:0 0 8px; font-size:20px; font-weight:900;">' + q.prompt + '</h3>' +
            '<div class="topic-chips">' + chipsHtml + '</div>' +
            '<div id="topic-sample-box" class="hint-box hidden" style="margin:0 0 14px; font-size:16px;"></div>' +
            '<textarea id="creative-input" class="text-input" rows="3" ' +
              'placeholder="例如：校園的陽光那麼燦爛，那麼暖和，讓大家充滿活力。" ' +
              'autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false" ' +
              'style="min-height:110px; resize:vertical;"></textarea>' +
            '<div class="action-row" style="justify-content:center; margin-top:16px;">' +
              '<button type="button" id="creative-submit-btn" class="btn btn-violet">✨ 提交我的原創佳句</button>' +
            '</div>' +
            '<div id="s2-fb" class="feedback-box hidden"></div>' +
            '<div id="s2-next-row" class="action-row hidden">' +
              '<button type="button" id="s2-next-btn" class="btn btn-gold">' + nextText + '</button>' +
            '</div>';

          var chips = card.querySelectorAll('.topic-chip');
          for (var c = 0; c < chips.length; c++) {
            chips[c].addEventListener('click', function () {
              Sound.hint();
              var idx = parseInt(this.getAttribute('data-topic'), 10);
              var box = byId('topic-sample-box');
              box.innerHTML = '💡 靈感參考（' + q.topics[idx].name + '）：<br>「' + q.topics[idx].sample + '」<br><span style="font-size:14px;">（請用自己的想法改寫成獨一無二的句子喔！）</span>';
              box.classList.remove('hidden');
            });
          }

          on('creative-submit-btn', 'click', function () {
            if (state.answered) return;
            var ta = byId('creative-input');
            var fb = byId('s2-fb');
            var text = ta.value.trim();
            var compact = text.replace(/[\s\u3000]+/g, '');

            // 智能檢查：至少 2 個「那麼」、每個「那麼」後皆有內容、總字數 >= 10
            var parts = compact.split('那麼');
            var countNaMe = parts.length - 1;
            var afterFirst = countNaMe >= 1 ? parts[1].replace(/[，。！？、,.!?；;：:]/g, '') : '';
            var afterSecond = countNaMe >= 2 ? parts[2].replace(/[，。！？、,.!?；;：:]/g, '') : '';

            if (countNaMe < 2) {
              Sound.wrong();
              fb.className = 'feedback-box fb-warn';
              fb.textContent = '✏️ 句子裏需要包含至少兩個「那麼」喔！（例如：……那麼……，那麼……。）';
              fb.classList.remove('hidden');
              ta.focus();
              return;
            }
            if (!afterFirst || !afterSecond) {
              Sound.wrong();
              fb.className = 'feedback-box fb-warn';
              fb.textContent = '✏️ 每個「那麼」後面都要寫上描寫特點的詞語喔！';
              fb.classList.remove('hidden');
              ta.focus();
              return;
            }
            if (Array.from(compact).length < 10) {
              Sound.wrong();
              fb.className = 'feedback-box fb-warn';
              fb.textContent = '✏️ 句子太短了，請寫滿至少 10 個字，讓句子更豐富完整！';
              fb.classList.remove('hidden');
              ta.focus();
              return;
            }

            // 達標滿分！
            state.answered = true;
            state.s2Correct++;
            state.score += 15;
            state.studentSentence = text;
            updateHUD();
            Sound.correct();

            ta.disabled = true;
            byId('creative-submit-btn').classList.add('hidden');
            fb.className = 'feedback-box fb-ok';
            fb.innerHTML = '🌟 <strong>寫得太棒了！滿分鼓勵！</strong>（+15 分）<div style="margin-top:6px;">你的原創佳句已珍藏到最後的「榮譽探險證書」上，待會兒可以截圖給老師欣賞！</div>';
            fb.classList.remove('hidden');
            byId('s2-next-row').classList.remove('hidden');
            setMascot('🎉', '小小作家誕生啦！準備迎接最後一關吧！');
          });

          on('s2-next-btn', 'click', advanceQuestion);
        }
      }

      /* ----------------------------------------------------------
         8. 第三關：省略號（⋯⋯）兩種用法 (6 題)
      ---------------------------------------------------------- */
      function renderStage3() {
        var q = STAGE3_DATA[state.index];
        var card = byId('question-card');
        if (!card || !q) return;

        var isLast = state.index === STAGE3_DATA.length - 1;
        var nextText = isLast ? '🏆 完成挑戰！領取榮譽證書' : '下一題 ➡️';

        // --- 題目 1-4：兩種用法分類 ---
        if (q.type === 'classify') {
          setMascot('🔎', '讀一讀句子語氣，判斷省略號「⋯⋯」是「例子未說完」還是「說話斷斷續續」？');
          var highlighted = q.sentence.replace(/⋯⋯/g, '<span style="color:#0284c7; font-weight:900;">⋯⋯</span>');

          card.innerHTML =
            '<div class="q-header"><span class="badge badge-sky">🔎 ' + q.tag + '</span></div>' +
            '<h3 style="margin:0 0 12px; font-size:20px; font-weight:900;">下面句子中的省略號「⋯⋯」屬於哪一種用法？</h3>' +
            '<div class="sentence-box sentence-box-s3">' + highlighted + '</div>' +
            '<div id="s3-cls-grid" class="classify-grid">' +
              '<button type="button" class="classify-btn" data-val="examples">' +
                '<span style="font-size:32px;">📚</span>' +
                '<span style="font-size:21px; font-weight:900; color:#0f172a;">例子未說完</span>' +
                '<span style="font-size:14px; font-weight:700; color:#64748b;">列舉同類事物，還有很多</span>' +
              '</button>' +
              '<button type="button" class="classify-btn" data-val="stutter">' +
                '<span style="font-size:32px;">🗣️</span>' +
                '<span style="font-size:21px; font-weight:900; color:#0f172a;">說話斷斷續續</span>' +
                '<span style="font-size:14px; font-weight:700; color:#64748b;">表現喘氣、緊張或停頓</span>' +
              '</button>' +
            '</div>' +
            '<div id="s3-fb" class="feedback-box hidden"></div>' +
            '<div id="s3-next-row" class="action-row hidden">' +
              '<button type="button" id="s3-next-btn" class="btn btn-gold">' + nextText + '</button>' +
            '</div>';

          var clsBtns = card.querySelectorAll('#s3-cls-grid .classify-btn');
          for (var i = 0; i < clsBtns.length; i++) {
            clsBtns[i].addEventListener('click', function () {
              if (state.answered) return;
              state.answered = true;
              var val = this.getAttribute('data-val');
              var ok = val === q.answer;
              var fb = byId('s3-fb');

              for (var k = 0; k < clsBtns.length; k++) {
                clsBtns[k].disabled = true;
                var bVal = clsBtns[k].getAttribute('data-val');
                if (bVal === q.answer) clsBtns[k].classList.add('opt-correct');
                else if (bVal === val && !ok) clsBtns[k].classList.add('opt-wrong');
              }

              var ansLabel = q.answer === 'examples' ? '例子未說完' : '說話斷斷續續';
              if (ok) {
                state.s3Correct++;
                state.score += 15;
                updateHUD();
                Sound.correct();
                fb.className = 'feedback-box fb-ok';
                fb.innerHTML = '🎉 <strong>判斷正確！就是「' + ansLabel + '」！</strong>（+15 分）<div style="margin-top:6px;">' + q.explanation + '</div>';
                setMascot('🌟', '精明小偵探，一眼就看穿省略號的秘密！');
              } else {
                Sound.wrong();
                fb.className = 'feedback-box fb-err';
                fb.innerHTML = '💡 <strong>正確答案是：「' + ansLabel + '」</strong><div style="margin-top:6px;">' + q.explanation + '</div>';
                setMascot('🦉', '沒關係，看懂解析後下一題一定答對！');
              }
              fb.classList.remove('hidden');
              byId('s3-next-row').classList.remove('hidden');
            });
          }

          on('s3-next-btn', 'click', advanceQuestion);
          return;
        }

        // --- 題目 5：標點捉錯處單選 ---
        if (q.type === 'mcq') {
          setMascot('🔎', '小心「省略號＋等等」的常見陷阱喔！選出完全正確的一句！');
          var optsHtml = '';
          for (var i = 0; i < q.options.length; i++) {
            optsHtml +=
              '<button type="button" class="option-btn" data-idx="' + i + '">' +
                '<span class="opt-tag">' + q.options[i].label + '</span>' +
                '<span>' + q.options[i].text + '</span>' +
              '</button>';
          }

          card.innerHTML =
            '<div class="q-header"><span class="badge badge-sky">🔎 ' + q.tag + '</span></div>' +
            '<h3 style="margin:0 0 8px; font-size:22px; font-weight:900;">' + q.prompt + '</h3>' +
            '<div id="s3-opts" class="option-list">' + optsHtml + '</div>' +
            '<div id="s3-fb" class="feedback-box hidden"></div>' +
            '<div id="s3-next-row" class="action-row hidden">' +
              '<button type="button" id="s3-next-btn" class="btn btn-gold">' + nextText + '</button>' +
            '</div>';

          var btns = card.querySelectorAll('#s3-opts .option-btn');
          for (var b = 0; b < btns.length; b++) {
            btns[b].addEventListener('click', function () {
              if (state.answered) return;
              state.answered = true;
              var idx = parseInt(this.getAttribute('data-idx'), 10);
              var chosen = q.options[idx];
              var fb = byId('s3-fb');

              for (var k = 0; k < btns.length; k++) {
                btns[k].disabled = true;
                if (q.options[k].ok) btns[k].classList.add('opt-correct');
                else if (k === idx && !chosen.ok) btns[k].classList.add('opt-wrong');
              }

              if (chosen.ok) {
                state.s3Correct++;
                state.score += 15;
                updateHUD();
                Sound.correct();
                fb.className = 'feedback-box fb-ok';
                fb.innerHTML = '🎉 <strong>破案成功！</strong>（+15 分）<div style="margin-top:6px;">' + chosen.fb + '</div>';
                setMascot('🌟', '完全沒有掉進標點陷阱，太厲害啦！');
              } else {
                Sound.wrong();
                fb.className = 'feedback-box fb-err';
                fb.innerHTML = '🩺 <strong>標點小提醒：</strong><div style="margin-top:6px;">' + chosen.fb + '</div><div style="margin-top:8px; color:#065f46;">正確答案：' + q.correctAnswer + '</div>';
                setMascot('🦉', '記住喔：省略號不可以跟「等等」一起寫！');
              }
              fb.classList.remove('hidden');
              byId('s3-next-row').classList.remove('hidden');
            });
          }

          on('s3-next-btn', 'click', advanceQuestion);
          return;
        }

        // --- 題目 6：互動點擊放省略號 ---
        if (q.type === 'slot') {
          setMascot('🔎', '最後一題！點擊最合適的藍色位置按鈕，放上省略號「⋯⋯」！');
          card.innerHTML =
            '<div class="q-header"><span class="badge badge-sky">🔎 ' + q.tag + '</span></div>' +
            '<h3 style="margin:0 0 14px; font-size:20px; font-weight:900;">' + q.prompt + '</h3>' +
            '<div class="sentence-box sentence-box-s3" style="line-height:2.2;">' +
              '<span>' + q.segments[0] + '</span>' +
              '<button type="button" class="slot-pill-btn" data-slot="0">[位置A]</button>' +
              '<span>' + q.segments[1] + '</span>' +
              '<button type="button" class="slot-pill-btn" data-slot="1">[位置B]</button>' +
              '<span>' + q.segments[2] + '</span>' +
              '<button type="button" class="slot-pill-btn" data-slot="2">[位置C]</button>' +
              '<span>' + q.segments[3] + '</span>' +
            '</div>' +
            '<div id="s3-fb" class="feedback-box hidden"></div>' +
            '<div id="s3-next-row" class="action-row hidden">' +
              '<button type="button" id="s3-next-btn" class="btn btn-gold">' + nextText + '</button>' +
            '</div>';

          var slotBtns = card.querySelectorAll('.slot-pill-btn');
          for (var s = 0; s < slotBtns.length; s++) {
            slotBtns[s].addEventListener('click', function () {
              if (state.answered) return;
              var slotIdx = parseInt(this.getAttribute('data-slot'), 10);
              var fb = byId('s3-fb');

              if (slotIdx === q.correctSlot) {
                state.answered = true;
                state.s3Correct++;
                var pts = state.usedWrongOnce ? 10 : 15;
                state.score += pts;
                updateHUD();
                Sound.correct();

                for (var k = 0; k < slotBtns.length; k++) {
                  slotBtns[k].disabled = true;
                  if (k === q.correctSlot) {
                    slotBtns[k].textContent = '⋯⋯';
                    slotBtns[k].classList.add('slot-ok');
                  } else {
                    slotBtns[k].textContent = '、';
                    slotBtns[k].style.borderStyle = 'solid';
                    slotBtns[k].style.background = '#f1f5f9';
                    slotBtns[k].style.color = '#334155';
                  }
                }

                fb.className = 'feedback-box fb-ok';
                fb.innerHTML = '🎉 <strong>放得剛剛好！完美通關！</strong>（+' + pts + ' 分）<div style="margin-top:6px;">' + q.explanation + '</div>';
                fb.classList.remove('hidden');
                byId('s3-next-row').classList.remove('hidden');
                setMascot('🏆', '全部 23 題挑戰完成，快去領取你的榮譽證書吧！');
              } else {
                state.usedWrongOnce = true;
                Sound.wrong();
                this.classList.add('slot-bad');
                fb.className = 'feedback-box fb-err';
                fb.textContent = '🤔 ' + q.wrongHints[slotIdx] + ' 請再點選正確的位置！';
                fb.classList.remove('hidden');
                setMascot('🦉', '想想看，表示「例子未說完」的省略號放在哪裏才對？');
              }
            });
          }

          on('s3-next-btn', 'click', advanceQuestion);
        }
      }

      /* ----------------------------------------------------------
         9. 結算榮譽探險證書
      ---------------------------------------------------------- */
      function showReport() {
        stopTimer();
        Sound.victory();
        showScreen('screen-report');

        var totalCorrect = state.s1Correct + state.s2Correct + state.s3Correct;
        var ratio = totalCorrect / 23;
        var stars = ratio >= 0.85 ? '⭐⭐⭐' : (ratio >= 0.55 ? '⭐⭐' : '⭐');
        var rankTitle = ratio >= 0.85 ? '🏆 星光語文探險大師' : (ratio >= 0.55 ? '🌟 語文探險小博士' : '🌱 勤學探險小勇士');

        byId('report-stars').textContent = stars;
        byId('report-title').textContent = rankTitle;
        byId('report-student').textContent = '頒發予：' + state.studentName;
        byId('report-score').textContent = state.score + ' 分';

        var usedSec = (TOTAL_TIME_SEC - state.secondsLeft) + state.overtimeSec;
        var um = Math.floor(usedSec / 60);
        var us = usedSec % 60;
        byId('report-time').textContent = um + '分' + (us < 10 ? '0' : '') + us + '秒';
        byId('report-total').textContent = totalCorrect + ' / 23';

        byId('report-s1').textContent = state.s1Correct + ' / 13';
        byId('report-s2').textContent = state.s2Correct + ' / 4';
        byId('report-s3').textContent = state.s3Correct + ' / 6';

        byId('report-s1-bar').style.width = Math.round((state.s1Correct / 13) * 100) + '%';
        byId('report-s2-bar').style.width = Math.round((state.s2Correct / 4) * 100) + '%';
        byId('report-s3-bar').style.width = Math.round((state.s3Correct / 6) * 100) + '%';

        byId('report-sentence-text').textContent = state.studentSentence
          ? '「' + state.studentSentence + '」'
          : '（尚未完成第二關造句題）';

        // 溫故知新小清單
        var reviewArea = byId('report-review-area');
        if (state.s1Correct === 13 && state.s1ReviewList.length === 0) {
          reviewArea.innerHTML =
            '<div style="text-align:center; padding:8px 0;">' +
              '<div style="font-size:36px;">🏆</div>' +
              '<strong style="font-size:20px; color:#047857;">恭喜獲得「詞語滿分大師」勳章！</strong>' +
              '<p style="margin:6px 0 0; font-size:16px; color:#475569; font-weight:700;">第一關 13 個不供詞填充詞語全部答對，中文根基非常紮實！</p>' +
            '</div>';
        } else if (state.s1ReviewList.length === 0) {
          reviewArea.innerHTML =
            '<strong style="font-size:18px; color:#9a3412;">📘 溫故知新小清單</strong>' +
            '<p style="margin:8px 0 0; font-size:16px; color:#475569; font-weight:700;">本次沒有跳過或查看答案的詞語紀錄。歡迎再挑戰一次拿齊全部 13 個詞語滿分！</p>';
        } else {
          var listHtml = '<strong style="font-size:18px; color:#9a3412;">📘 溫故知新小清單（第一關需要重溫的詞語）</strong>';
          for (var i = 0; i < state.s1ReviewList.length; i++) {
            var item = state.s1ReviewList[i];
            listHtml +=
              '<div class="review-item">' +
                '<strong>' + (i + 1) + '. 正解：' + item.answer + '</strong>' +
                ' <span style="color:#b91c1c; font-size:14px;">（你曾輸入：' + item.userAnswer + '）</span>' +
                '<div style="font-size:15px; color:#475569; margin-top:4px;">' + item.note + '</div>' +
              '</div>';
          }
          reviewArea.innerHTML = listHtml;
        }
      }

      /* ----------------------------------------------------------
         10. 老師專區 & 超穩定 QR Code 載入（<img onerror> 雙重保障）
      ---------------------------------------------------------- */
      function normalizeUrl(raw) {
        var u = (raw || '').trim();
        if (!u) return '';
        if (!/^https?:\/\//i.test(u)) {
          u = 'https://' + u;
        }
        return u;
      }

      function setQrImage(imgEl, url) {
        if (!imgEl) return;
        var encoded = encodeURIComponent(url);
        var primary = 'https://api.qrserver.com/v1/create-qr-code/?size=320x320&margin=12&data=' + encoded;
        var fallback = 'https://quickchart.io/qr?size=320&margin=2&text=' + encoded;

        imgEl.dataset.fallbackTried = '0';
        imgEl.onerror = function () {
          if (imgEl.dataset.fallbackTried === '0') {
            imgEl.dataset.fallbackTried = '1';
            imgEl.src = fallback;
          }
        };
        imgEl.src = primary;
      }

      function initQrInputDefault() {
        var input = byId('qr-url-input');
        var notice = byId('qr-notice');
        if (!input) return;

        var href = '';
        try {
          href = window.location.href || '';
        } catch (e) {
          href = '';
        }

        var isPublicHttp =
          /^https?:\/\//i.test(href) &&
          href.indexOf('localhost') === -1 &&
          href.indexOf('127.0.0.1') === -1 &&
          href.indexOf('googleusercontent.com') === -1 &&
          href.indexOf('usercontent.goog') === -1;

        if (isPublicHttp) {
          input.value = href;
          if (notice) notice.classList.add('hidden');
        } else {
          input.value = DEMO_URL;
          if (notice) notice.classList.remove('hidden');
        }
        updateTeacherQr();
      }

      function updateTeacherQr() {
        var input = byId('qr-url-input');
        var display = byId('qr-url-display');
        var img = byId('qr-img');
        if (!input) return;

        var url = normalizeUrl(input.value) || DEMO_URL;
        input.value = url;
        if (display) display.textContent = url;
        setQrImage(img, url);
      }

      function buildAnswerKey() {
        var panel = byId('answers-panel');
        if (!panel) return;

        var rows = '';
        for (var i = 0; i < STAGE1_DATA.length; i++) {
          var q = STAGE1_DATA[i];
          rows += '<tr><td>' + (i + 1) + '</td><td><strong>' + q.answer + '</strong></td><td>' + q.before + '【' + q.answer + '】' + q.after + '</td></tr>';
        }

        panel.innerHTML =
          '<strong style="color:#047857;">⛰️ 第一關：不供詞填充（13 題）</strong>' +
          '<table class="ans-table"><thead><tr><th>題號</th><th>詞語</th><th>完整句子</th></tr></thead><tbody>' + rows + '</tbody></table>' +
          '<div style="margin-top:14px;"><strong style="color:#5b21b6;">🌉 第二關：「那麼⋯⋯那麼⋯⋯」（4 題）</strong>' +
          '<ol style="margin:6px 0 0; padding-left:20px; font-size:15px;">' +
            '<li>A. 夜空中的星星那麼閃爍，那麼迷人，教人看得入神。</li>' +
            '<li>① 涼爽、② 潔白</li>' +
            '<li>婆婆的笑容總是那麼和藹，那麼親切，令大家感到十分暖和。（「那麼和藹」「那麼親切」可互換）</li>' +
            '<li>自由造句：含至少 2 個「那麼」、每個「那麼」後有詞語且不少於 10 字。</li>' +
          '</ol></div>' +
          '<div style="margin-top:14px;"><strong style="color:#0369a1;">🔎 第三關：省略號兩種用法（6 題）</strong>' +
          '<ol style="margin:6px 0 0; padding-left:20px; font-size:15px;">' +
            '<li>例子未說完</li>' +
            '<li>說話斷斷續續</li>' +
            '<li>說話斷斷續續</li>' +
            '<li>例子未說完</li>' +
            '<li>B. 公園裏開滿了鮮花，有玫瑰、鬱金香、向日葵⋯⋯</li>' +
            '<li>[位置C]（位置 A、B 用頓號「、」，位置 C 放「⋯⋯」）</li>' +
          '</ol></div>';
      }

      /* ----------------------------------------------------------
         11. DOMContentLoaded：統一安全綁定所有按鈕事件
      ---------------------------------------------------------- */
      document.addEventListener('DOMContentLoaded', function () {
        buildAnswerKey();
        initQrInputDefault();

        // 音效開關
        on('welcome-sound-btn', 'click', toggleSound);
        on('hud-sound-btn', 'click', toggleSound);

        // 開始 8 分鐘挑戰
        on('start-game-btn', 'click', function () {
          Sound.click();
          resetGame(1);
          startTimer();
          showStageIntro(1);
        });

        // 關卡出發按鈕
        on('intro-start-btn', 'click', function () {
          Sound.click();
          showScreen('screen-game');
          renderQuestion();
        });

        // 頂部返回首頁按鈕 & 確認彈窗
        on('hud-home-btn', 'click', function () {
          Sound.click();
          byId('modal-exit').classList.remove('hidden');
        });
        on('exit-cancel-btn', 'click', function () {
          Sound.click();
          byId('modal-exit').classList.add('hidden');
        });
        on('exit-confirm-btn', 'click', function () {
          Sound.click();
          stopTimer();
          byId('modal-exit').classList.add('hidden');
          showScreen('screen-welcome');
        });

        // 時間到彈窗按鈕
        on('timeup-finish-btn', 'click', function () {
          Sound.click();
          byId('modal-timeup').classList.add('hidden');
          showReport();
        });
        on('timeup-continue-btn', 'click', function () {
          Sound.click();
          byId('modal-timeup').classList.add('hidden');
          state.isOvertime = true;
          startTimer();
        });

        // 證書頁按鈕
        on('report-retry-btn', 'click', function () {
          Sound.click();
          resetGame(1);
          startTimer();
          showStageIntro(1);
        });
        on('report-home-btn', 'click', function () {
          Sound.click();
          stopTimer();
          showScreen('screen-welcome');
        });

        // 老師專區開關
        on('open-teacher-btn', 'click', function () {
          Sound.click();
          byId('modal-teacher').classList.remove('hidden');
          updateTeacherQr();
        });
        on('close-teacher-btn', 'click', function () {
          Sound.click();
          byId('modal-teacher').classList.add('hidden');
        });

        // QR Code 控制按鈕
        on('qr-update-btn', 'click', function () {
          Sound.click();
          updateTeacherQr();
        });

        on('qr-copy-btn', 'click', function () {
          Sound.click();
          var input = byId('qr-url-input');
          var btn = byId('qr-copy-btn');
          if (!input) return;
          updateTeacherQr();
          try {
            input.select();
            input.setSelectionRange(0, 99999);
            document.execCommand('copy');
            btn.textContent = '✅ 已複製網址！';
            setTimeout(function () { btn.textContent = '📋 複製網址'; }, 1500);
          } catch (e) {
            btn.textContent = '請手動複製';
            setTimeout(function () { btn.textContent = '📋 複製網址'; }, 1500);
          }
        });

        on('qr-fullscreen-btn', 'click', function () {
          Sound.click();
          updateTeacherQr();
          var url = byId('qr-url-input').value;
          byId('qr-fullscreen-url').textContent = url;
          setQrImage(byId('qr-fullscreen-img'), url);
          byId('modal-qr-fullscreen').classList.remove('hidden');
        });

        on('close-qr-fullscreen-btn', 'click', function () {
          Sound.click();
          byId('modal-qr-fullscreen').classList.add('hidden');
        });

        // 課堂參數設定開關
        on('set-timer', 'change', function () {
          state.settings.timerEnabled = this.checked;
        });
        on('set-hints', 'change', function () {
          state.settings.hintsEnabled = this.checked;
        });
        on('set-shuffle', 'change', function () {
          state.settings.shuffleStage1 = this.checked;
        });

        // 快速跳關試玩按鈕
        function jumpToStage(stageNum) {
          Sound.click();
          byId('modal-teacher').classList.add('hidden');
          resetGame(stageNum);
          startTimer();
          showStageIntro(stageNum);
        }
        on('jump-s1', 'click', function () { jumpToStage(1); });
        on('jump-s2', 'click', function () { jumpToStage(2); });
        on('jump-s3', 'click', function () { jumpToStage(3); });
        on('jump-report', 'click', function () {
          Sound.click();
          byId('modal-teacher').classList.add('hidden');
          resetGame(1);
          state.studentName = '4A 12 示範同學';
          state.s1Correct = 12;
          state.s2Correct = 4;
          state.s3Correct = 6;
          state.score = 265;
          state.secondsLeft = 142;
          state.studentSentence = '清晨校園的陽光那麼燦爛，那麼暖和，讓同學們露出開朗的笑容。';
          state.s1ReviewList = [{
            answer: '搧',
            userAnswer: '扇',
            note: '「搧」是動詞，表示用手搖動扇子生風，所以用提手旁（扌）。'
          }];
          showReport();
        });

        // 折疊展開答案表
        on('toggle-answers-btn', 'click', function () {
          Sound.click();
          var panel = byId('answers-panel');
          var isHidden = panel.classList.contains('hidden');
          if (isHidden) {
            panel.classList.remove('hidden');
            this.textContent = '收起答案表 ▲';
          } else {
            panel.classList.add('hidden');
            this.textContent = '展開答案表 ▼';
          }
        });
      });
    })();
  </script>
</body>
</html>
