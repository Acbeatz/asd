[MH8-W-PLANE RUN CONTROLLER IFRAMV5.404.html.index.html](https://github.com/user-attachments/files/23894063/MH8-W-PLANE.RUN.CONTROLLER.IFRAMV5.404.html.index.html)

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>ACBEATZ.COM — MH8 W-FX W-PLANE Controller POF Demo</title>
  <meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
  <meta name="theme-color" content="#020617" />
  <meta name="mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;800&family=Inter:wght@400;600;800&display=swap" rel="stylesheet" />

  <style>
    :root {
      --bg-1: #020617;
      --bg-2: #020617;
      --bg-grad-1: #020617;
      --bg-grad-2: #02091f;
      --bg-grad-3: #01111f;

      --panel: #020617;
      --panel-soft: #050b16;
      --panel-alt: #020813;

      --border-subtle: rgba(148, 163, 184, 0.35);
      --border-strong: rgba(56, 189, 248, 0.9);

      --accent-blue: #38bdf8;
      --accent-blue-soft: rgba(56, 189, 248, 0.25);
      --accent-green: #22c55e;
      --accent-green-soft: rgba(34, 197, 94, 0.3);
      --accent-magenta: #a855f7;

      --text-main: #e5f0ff;
      --text-muted: #94a3b8;
      --text-soft: #64748b;

      --danger: #f97373;

      --radius: 18px;
      --shadow-soft: 0 18px 40px rgba(15, 23, 42, 0.85);
      --shadow-neon: 0 0 30px rgba(56, 189, 248, 0.6), 0 0 40px rgba(34, 197, 94, 0.45);
    }

    body.fx-neon {
      --panel: #020616;
      --panel-soft: #020919;
      --panel-alt: #000814;
      --border-subtle: rgba(56, 189, 248, 0.65);
      --bg-grad-1: #00010a;
      --bg-grad-2: #001b2f;
      --bg-grad-3: #00120b;
      --shadow-soft: 0 0 30px rgba(15, 23, 42, 0.95);
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Inter, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color: var(--text-main);
      background:
        radial-gradient(900px 600px at 10% 0%, rgba(56, 189, 248, 0.16), transparent 65%),
        radial-gradient(900px 600px at 90% 0%, rgba(34, 197, 94, 0.18), transparent 65%),
        radial-gradient(1000px 800px at 50% 100%, rgba(168, 85, 247, 0.2), transparent 75%),
        linear-gradient(160deg, var(--bg-grad-1), var(--bg-grad-2) 50%, var(--bg-grad-3));
      padding: calc(env(safe-area-inset-top, 0px) + 12px) 10px calc(env(safe-area-inset-bottom, 0px) + 16px);
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: -40%;
      background:
        radial-gradient(circle at 20% 20%, rgba(56, 189, 248, 0.16), transparent 55%),
        radial-gradient(circle at 80% 10%, rgba(34, 197, 94, 0.14), transparent 55%),
        radial-gradient(circle at 50% 90%, rgba(168, 85, 247, 0.12), transparent 60%);
      filter: blur(40px);
      opacity: 0.9;
      pointer-events: none;
      z-index: -1;
      animation: bgFloat 16s ease-in-out infinite alternate;
    }

    @keyframes bgFloat {
      0% {
        transform: translate3d(-2%, -2%, 0);
      }
      100% {
        transform: translate3d(2%, 3%, 0);
      }
    }

    .app-shell {
      max-width: 1120px;
      margin: 0 auto;
      border-radius: 24px;
      border: 1px solid rgba(148, 163, 184, 0.35);
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.98));
      box-shadow: var(--shadow-soft);
      padding: 14px 12px 18px;
      backdrop-filter: blur(12px);
    }

    @media (min-width: 720px) {
      .app-shell {
        padding: 18px 20px 20px;
      }
    }

    header.app-header {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
    }

    .brand-block {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .brand-logo {
      width: 36px;
      height: 36px;
      border-radius: 999px;
      background:
        conic-gradient(from 200deg, #0f172a, #22c55e, #38bdf8, #a855f7, #0f172a);
      padding: 2px;
      box-shadow: 0 0 16px rgba(56, 189, 248, 0.6), 0 0 28px rgba(34, 197, 94, 0.4);
      display: grid;
      place-items: center;
    }

    .brand-logo-inner {
      width: 100%;
      height: 100%;
      border-radius: inherit;
      background: radial-gradient(circle at 30% 15%, #f9fafb, #020617);
      display: grid;
      place-items: center;
      font-family: Orbitron, Inter, sans-serif;
      font-size: 16px;
      font-weight: 800;
      color: #0f172a;
      letter-spacing: 0.12em;
    }

    .brand-text-main {
      font-family: Orbitron, Inter, sans-serif;
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--text-main);
    }

    .brand-sub {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--text-soft);
    }

    .brand-text-wrap {
      display: flex;
      flex-direction: column;
      gap: 2px;
    }

    .header-pills {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      align-items: center;
      justify-content: flex-end;
      font-size: 11px;
    }

    .pill {
      border-radius: 999px;
      padding: 5px 9px;
      border: 1px solid rgba(148, 163, 184, 0.4);
      background: radial-gradient(circle at 10% 0%, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.98));
      color: var(--text-soft);
      display: inline-flex;
      align-items: center;
      gap: 5px;
      white-space: nowrap;
      text-decoration: none;
    }

    .pill-dot {
      width: 8px;
      height: 8px;
      border-radius: 999px;
      background: radial-gradient(circle, var(--accent-green), transparent 60%);
      box-shadow: 0 0 12px rgba(34, 197, 94, 0.9);
    }

    .pill-pill-blue {
      border-color: rgba(56, 189, 248, 0.6);
      color: var(--accent-blue);
    }

    .pill-pill-green {
      border-color: rgba(34, 197, 94, 0.6);
      color: var(--accent-green);
    }

    .app-title-block {
      margin-bottom: 12px;
      margin-top: 4px;
    }

    .app-title {
      font-family: Orbitron, Inter, sans-serif;
      font-size: clamp(18px, 3.3vw, 22px);
      letter-spacing: 0.18em;
      text-transform: uppercase;
      margin: 0 0 4px;
      color: var(--accent-blue);
      text-shadow: 0 0 14px rgba(56, 189, 248, 0.9), 0 0 30px rgba(34, 197, 94, 0.5);
    }

    .app-subtitle {
      margin: 0;
      font-size: 13px;
      color: var(--text-muted);
    }

    .app-subtitle strong {
      color: var(--accent-green);
      font-weight: 600;
    }

    .layout-grid {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr);
      gap: 10px;
    }

    @media (min-width: 900px) {
      .layout-grid {
        grid-template-columns: minmax(0, 1.05fr) minmax(0, 1.1fr);
        gap: 12px;
      }
    }

    .panel {
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.98));
      border-radius: var(--radius);
      border: 1px solid rgba(148, 163, 184, 0.5);
      padding: 10px 10px 12px;
      box-shadow: 0 10px 30px rgba(15, 23, 42, 0.75);
      position: relative;
      overflow: hidden;
    }

    .panel::before {
      content: "";
      position: absolute;
      inset: -35%;
      background:
        radial-gradient(circle at 8% 0%, rgba(56, 189, 248, 0.12), transparent 60%),
        radial-gradient(circle at 110% 10%, rgba(34, 197, 94, 0.18), transparent 60%);
      filter: blur(24px);
      opacity: 0.7;
      pointer-events: none;
      z-index: -1;
    }

    .panel-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 8px;
      margin-bottom: 8px;
    }

    .panel-title {
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--text-muted);
    }

    .panel-tag {
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      padding: 3px 7px;
      border-radius: 999px;
      border: 1px solid rgba(56, 189, 248, 0.6);
      color: var(--accent-blue);
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.98));
    }

    .panel-header-actions {
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .hud-row {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 8px;
    }

    .hud-card {
      flex: 1 1 100px;
      min-width: 0;
      padding: 8px 9px;
      border-radius: 12px;
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.98));
      border: 1px solid rgba(148, 163, 184, 0.5);
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .hud-label {
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--text-soft);
    }

    .hud-value {
      font-size: 15px;
      font-weight: 700;
      letter-spacing: 0.04em;
    }

    .hud-value.state-null {
      color: var(--accent-blue);
    }

    .hud-value.state-lag {
      color: var(--accent-magenta);
    }

    .hud-value.state-dart {
      color: var(--accent-green);
    }

    .hud-sub {
      font-size: 11px;
      color: var(--text-soft);
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }

    .controls-group {
      margin-top: 6px;
      border-radius: 14px;
      border: 1px solid rgba(148, 163, 184, 0.5);
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.94), rgba(15, 23, 42, 0.98));
      padding: 8px 9px;
      display: grid;
      gap: 8px;
    }

    .controls-grid {
      display: grid;
      grid-template-columns: minmax(0, 1fr);
      gap: 8px;
    }

    @media (min-width: 640px) {
      .controls-grid {
        grid-template-columns: minmax(0, 1.05fr) minmax(0, 1.1fr);
      }
    }

    .slider-block {
      display: grid;
      gap: 2px;
    }

    .slider-top {
      display: flex;
      justify-content: space-between;
      font-size: 11px;
      color: var(--text-soft);
    }

    .slider-top span.key {
      text-transform: uppercase;
      letter-spacing: 0.16em;
      font-size: 10px;
    }

    .slider-top span.value {
      font-weight: 600;
      color: var(--accent-blue);
    }

    input[type="range"] {
      width: 100%;
      -webkit-appearance: none;
      appearance: none;
      height: 4px;
      border-radius: 999px;
      background: radial-gradient(circle at 0% 0%, #020617, #020617);
      outline: none;
    }

    input[type="range"]::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 20%, #f9fafb, var(--accent-blue));
      border: 1px solid rgba(15, 23, 42, 0.9);
      box-shadow: 0 0 12px rgba(56, 189, 248, 0.7), 0 0 20px rgba(34, 197, 94, 0.55);
      cursor: pointer;
    }

    input[type="range"]::-moz-range-thumb {
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: radial-gradient(circle at 30% 20%, #f9fafb, var(--accent-blue));
      border: 1px solid rgba(15, 23, 42, 0.9);
      box-shadow: 0 0 12px rgba(56, 189, 248, 0.7), 0 0 20px rgba(34, 197, 94, 0.55);
      cursor: pointer;
    }

    input[type="range"]::-webkit-slider-runnable-track {
      height: 4px;
      border-radius: 999px;
      background: linear-gradient(90deg, var(--accent-green-soft), var(--accent-blue-soft));
    }

    input[type="range"]::-moz-range-track {
      height: 4px;
      border-radius: 999px;
      background: linear-gradient(90deg, var(--accent-green-soft), var(--accent-blue-soft));
    }

    /* LIVE URL DRIVER BLOCK */
    .live-url-block {
      margin-top: 4px;
      border-radius: 12px;
      border: 1px dashed rgba(148, 163, 184, 0.7);
      padding: 8px 9px 7px;
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.99));
      display: grid;
      gap: 4px;
    }

    .live-url-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      align-items: center;
    }

    .live-url-input {
      flex: 1 1 160px;
      min-width: 0;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.7);
      background: rgba(15, 23, 42, 0.96);
      color: var(--text-main);
      font-size: 11px;
      padding: 7px 10px;
      outline: none;
    }

    .live-url-input::placeholder {
      color: var(--text-soft);
    }

    .live-url-input:focus {
      border-color: rgba(56, 189, 248, 0.9);
      box-shadow: 0 0 0 1px rgba(56, 189, 248, 0.5);
    }

    .btn-row {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }

    .btn {
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.6);
      background: radial-gradient(circle at 0% 0%, #020617, #020617);
      color: var(--text-main);
      font-size: 11px;
      padding: 7px 11px;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      cursor: pointer;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      min-height: 28px;
      white-space: nowrap;
      touch-action: manipulation;
      transition: transform 0.14s ease, box-shadow 0.16s ease, border-color 0.16s ease, background 0.16s ease;
    }

    .btn span.emoji {
      font-size: 13px;
    }

    .btn-primary {
      border-color: rgba(56, 189, 248, 0.8);
      background: linear-gradient(90deg, rgba(34, 197, 94, 0.9), rgba(56, 189, 248, 0.9));
      color: #020617;
      box-shadow: 0 6px 22px rgba(0, 0, 0, 0.6), 0 0 24px rgba(56, 189, 248, 0.6);
    }

    .btn-ghost {
      border-style: dashed;
      color: var(--text-soft);
    }

    .btn-danger {
      border-color: rgba(248, 113, 113, 0.9);
      color: #fecaca;
    }

    .btn:hover {
      transform: translateY(-1px);
      box-shadow: 0 4px 16px rgba(15, 23, 42, 0.85);
    }

    .btn-primary:hover {
      box-shadow: var(--shadow-neon);
    }

    .btn:active {
      transform: translateY(0) scale(0.99);
      box-shadow: 0 2px 8px rgba(15, 23, 42, 0.8);
    }

    .icon-button {
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.6);
      background: radial-gradient(circle at 30% 20%, #020617, #020617);
      color: var(--text-soft);
      font-size: 10px;
      padding: 5px 9px;
      display: inline-flex;
      align-items: center;
      gap: 5px;
      cursor: pointer;
      text-transform: uppercase;
      letter-spacing: 0.16em;
    }

    .icon-button span.emoji {
      font-size: 13px;
    }

    .icon-button:hover {
      transform: translateY(-1px);
      box-shadow: 0 4px 18px rgba(15, 23, 42, 0.85);
      border-color: rgba(56, 189, 248, 0.85);
      color: var(--accent-blue);
    }

    .theory-note {
      margin-top: 4px;
      font-size: 11px;
      color: var(--text-soft);
    }

    .theory-note code {
      font-family: "Space Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      font-size: 11px;
      background: rgba(15, 23, 42, 0.9);
      padding: 2px 4px;
      border-radius: 6px;
      border: 1px solid rgba(15, 23, 42, 0.9);
      color: var(--accent-blue);
    }

    .viz-panel-content {
      display: grid;
      gap: 10px;
    }

    @media (min-width: 820px) {
      .viz-panel-content {
        grid-template-columns: minmax(0, 1.05fr) minmax(0, 1.1fr);
      }
    }

    .diagram-card {
      position: relative;
      border-radius: 14px;
      padding: 10px 10px 12px;
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.98));
      border: 1px solid rgba(148, 163, 184, 0.55);
      overflow: hidden;
    }

    .diagram-card::before {
      content: "";
      position: absolute;
      inset: -20%;
      background:
        radial-gradient(circle at 20% 20%, rgba(56, 189, 248, 0.25), transparent 65%),
        radial-gradient(circle at 80% 80%, rgba(34, 197, 94, 0.22), transparent 65%);
      filter: blur(24px);
      opacity: 0.8;
      pointer-events: none;
      z-index: -1;
    }

    .diagram-title {
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--text-muted);
      margin-bottom: 6px;
    }

    .diagram-sub {
      font-size: 11px;
      color: var(--text-soft);
      margin-bottom: 6px;
    }

    .state-diagram {
      position: relative;
      height: 220px;
      display: grid;
      place-items: center;
    }

    .diagram-orbit {
      position: absolute;
      width: 182px;
      height: 182px;
      border-radius: 50%;
      border: 1px dashed rgba(148, 163, 184, 0.6);
      box-shadow: 0 0 16px rgba(15, 23, 42, 0.95);
      animation: orbitPulse 16s ease-in-out infinite;
    }

    .diagram-orbit::after {
      content: "";
      position: absolute;
      top: 50%;
      left: 50%;
      width: 10px;
      height: 10px;
      border-radius: 999px;
      background: radial-gradient(circle at 30% 20%, #f9fafb, var(--accent-blue));
      box-shadow: 0 0 16px rgba(56, 189, 248, 0.9), 0 0 26px rgba(34, 197, 94, 0.7);
      transform-origin: -80px 0;
      animation: orbitDot 12s linear infinite;
    }

    @keyframes orbitPulse {
      0% {
        box-shadow: 0 0 14px rgba(15, 23, 42, 0.9);
        opacity: 0.9;
      }
      50% {
        box-shadow: 0 0 26px rgba(56, 189, 248, 0.7);
        opacity: 1;
      }
      100% {
        box-shadow: 0 0 14px rgba(15, 23, 42, 0.9);
        opacity: 0.9;
      }
    }

    @keyframes orbitDot {
      0% {
        transform: rotate(0deg) translateX(80px);
      }
      100% {
        transform: rotate(360deg) translateX(80px);
      }
    }

    .diagram-center {
      position: absolute;
      width: 40px;
      height: 40px;
      border-radius: 999px;
      display: grid;
      place-items: center;
      background: radial-gradient(circle at 30% 15%, #f9fafb, #020617);
      border: 1px solid rgba(56, 189, 248, 0.8);
      box-shadow: 0 0 20px rgba(56, 189, 248, 0.8), 0 0 30px rgba(34, 197, 94, 0.6);
      font-family: Orbitron, Inter, sans-serif;
      font-size: 11px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: #020617;
    }

    .state-node {
      position: absolute;
      width: 80px;
      height: 80px;
      border-radius: 999px;
      padding: 6px 8px;
      display: grid;
      place-items: center;
      text-align: center;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      background: radial-gradient(circle at 30% 15%, #0b1120, #020617);
      border: 1px solid rgba(148, 163, 184, 0.8);
      color: var(--text-soft);
      box-shadow: 0 0 12px rgba(15, 23, 42, 0.9);
      transition: transform 0.18s ease, box-shadow 0.18s ease, border-color 0.18s ease, color 0.18s ease;
    }

    .state-node span.label-main {
      display: block;
      font-weight: 700;
      color: var(--text-main);
      margin-bottom: 2px;
    }

    .state-node span.label-sub {
      font-size: 10px;
      text-transform: none;
      letter-spacing: 0.05em;
      color: var(--text-soft);
    }

    .state-node.idle {
      top: 8px;
      left: calc(50% - 40px);
    }

    .state-node.lag {
      bottom: 8px;
      left: 12px;
    }

    .state-node.dart {
      bottom: 8px;
      right: 12px;
    }

    .state-node.active {
      border-color: rgba(56, 189, 248, 0.9);
      color: var(--accent-blue);
      transform: translateY(-3px) scale(1.03);
      box-shadow: 0 0 24px rgba(56, 189, 248, 0.7), 0 0 34px rgba(34, 197, 94, 0.5);
    }

    .state-node.dart.active {
      border-color: rgba(34, 197, 94, 0.9);
      color: var(--accent-green);
    }

    .diagram-arrow {
      position: absolute;
      height: 2px;
      background: linear-gradient(90deg, rgba(148, 163, 184, 0.4), rgba(56, 189, 248, 0.8));
      transform-origin: center;
      opacity: 0.8;
    }

    .diagram-arrow::after {
      content: "";
      position: absolute;
      right: 0;
      top: 50%;
      width: 0;
      height: 0;
      border-top: 4px solid transparent;
      border-bottom: 4px solid transparent;
      border-left: 7px solid rgba(56, 189, 248, 0.9);
      transform: translateY(-50%);
    }

    .arrow-idle-lag {
      width: 92px;
      left: calc(50% - 46px);
      bottom: 60px;
      transform: rotate(225deg);
    }

    .arrow-lag-dart {
      width: 88px;
      bottom: 24px;
      left: calc(50% - 44px);
    }

    .arrow-dart-idle {
      width: 92px;
      left: calc(50% - 46px);
      top: 40px;
      transform: rotate(-45deg);
    }

    .mini-eq {
      margin-top: 6px;
      padding: 6px 8px;
      border-radius: 10px;
      background: rgba(15, 23, 42, 0.98);
      border: 1px dashed rgba(148, 163, 184, 0.7);
      font-size: 11px;
      color: var(--text-soft);
      font-family: "Space Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      overflow-x: auto;
      white-space: nowrap;
    }

    .mini-eq strong {
      color: var(--accent-blue);
    }

    .explain-card {
      border-radius: 14px;
      padding: 9px 10px;
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.98));
      border: 1px solid rgba(148, 163, 184, 0.55);
      font-size: 11px;
      color: var(--text-soft);
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .explain-card h3 {
      margin: 0 0 4px;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: var(--text-muted);
    }

    .viewer-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 6px;
    }

    .viewer-frame-wrap {
      margin-top: 4px;
      border-radius: 10px;
      background: rgba(15, 23, 42, 0.97);
      border: 1px solid rgba(15, 23, 42, 1);
      overflow: hidden;
      height: 190px;
      position: relative;
    }

    .viewer-frame-wrap iframe {
      width: 100%;
      height: 100%;
      border: none;
      display: block;
      background: #020617;
    }

    .viewer-footnote {
      margin-top: 4px;
      font-size: 10px;
      color: var(--text-soft);
    }

    .log-panel {
      margin-top: 10px;
    }

    .log-layout {
      display: grid;
      grid-template-columns: minmax(0, 1.2fr) minmax(0, 1.1fr);
      gap: 9px;
    }

    @media (max-width: 800px) {
      .log-layout {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    .log-box {
      border-radius: 14px;
      padding: 8px 8px 6px;
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.98));
      border: 1px solid rgba(148, 163, 184, 0.6);
      display: flex;
      flex-direction: column;
      gap: 4px;
      max-height: 230px;
    }

    .log-header-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
      font-size: 11px;
      color: var(--text-muted);
    }

    .log-header-row strong {
      letter-spacing: 0.16em;
      text-transform: uppercase;
      font-size: 11px;
    }

    .log-body {
      flex: 1 1 auto;
      border-radius: 10px;
      background: rgba(15, 23, 42, 0.95);
      border: 1px solid rgba(15, 23, 42, 1);
      padding: 6px 7px;
      font-size: 11px;
      overflow-y: auto;
      display: grid;
      gap: 3px;
      scroll-behavior: smooth;
    }

    .log-entry {
      display: flex;
      gap: 5px;
      align-items: flex-start;
      color: var(--text-soft);
      line-height: 1.3;
      word-break: break-word;
    }

    .log-entry span.ts {
      flex: 0 0 auto;
      font-size: 10px;
      color: var(--text-soft);
      opacity: 0.8;
    }

    .log-entry span.msg {
      flex: 1 1 auto;
    }

    .log-entry.info span.msg {
      color: var(--text-soft);
    }

    .log-entry.queue span.msg {
      color: var(--accent-blue);
    }

    .log-entry.dart span.msg {
      color: var(--accent-green);
    }

    .log-entry.commit span.msg {
      color: var(--accent-magenta);
    }

    .log-entry.warn span.msg {
      color: var(--danger);
    }

    .log-footer {
      font-size: 10px;
      color: var(--text-soft);
      display: flex;
      justify-content: space-between;
      gap: 6px;
      align-items: center;
    }

    .log-footer span {
      white-space: nowrap;
    }

    .pof-box {
      border-radius: 14px;
      padding: 8px 8px 6px;
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.96), rgba(15, 23, 42, 0.98));
      border: 1px solid rgba(56, 189, 248, 0.7);
      display: flex;
      flex-direction: column;
      gap: 4px;
    }

    .pof-header-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
      font-size: 11px;
    }

    .pof-header-row strong {
      letter-spacing: 0.16em;
      text-transform: uppercase;
      font-size: 11px;
      color: var(--accent-blue);
    }

    .pof-status-pill {
      padding: 2px 7px;
      border-radius: 999px;
      border: 1px solid rgba(34, 197, 94, 0.7);
      color: var(--accent-green);
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      white-space: nowrap;
    }

    .pof-status-pill.fail {
      border-color: rgba(248, 113, 113, 0.9);
      color: #fecaca;
    }

    .pof-body {
      flex: 1 1 auto;
      border-radius: 10px;
      background: rgba(15, 23, 42, 0.97);
      border: 1px solid rgba(15, 23, 42, 1);
      padding: 6px 7px;
      font-size: 11px;
      overflow-y: auto;
      max-height: 180px;
    }

    .pof-body pre {
      margin: 0;
      white-space: pre;
      font-family: "Space Mono", ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      font-size: 11px;
      color: var(--text-main);
    }

    .pof-footer {
      font-size: 10px;
      color: var(--text-soft);
      margin-top: 2px;
    }

    .fx-button {
      position: fixed;
      right: 14px;
      bottom: calc(env(safe-area-inset-bottom, 0px) + 16px);
      width: 54px;
      height: 54px;
      border-radius: 999px;
      border: none;
      display: grid;
      place-items: center;
      background: conic-gradient(from 200deg, #22c55e, #38bdf8, #22c55e);
      box-shadow: 0 0 26px rgba(56, 189, 248, 0.9), 0 0 36px rgba(34, 197, 94, 0.7);
      color: #020617;
      font-family: Orbitron, Inter, sans-serif;
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.2em;
      cursor: pointer;
      z-index: 20;
      overflow: hidden;
      touch-action: manipulation;
    }

    .fx-button span {
      transform: translateY(1px);
    }

    .fx-button::before {
      content: "";
      position: absolute;
      inset: 4px;
      border-radius: inherit;
      background: radial-gradient(circle at 30% 15%, #f9fafb, #22c55e);
    }

    .fx-button::after {
      content: "FX";
      position: relative;
      z-index: 1;
    }

    .fx-panel {
      position: fixed;
      right: 14px;
      bottom: calc(env(safe-area-inset-bottom, 0px) + 84px);
      width: 240px;
      max-width: calc(100vw - 40px);
      border-radius: 18px;
      background: radial-gradient(circle at 0% 0%, #020617, #020617);
      border: 1px solid rgba(56, 189, 248, 0.7);
      padding: 10px 10px 8px;
      box-shadow: var(--shadow-neon);
      transform-origin: 100% 100%;
      transform: scale(0.9) translateY(10px);
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.18s ease, transform 0.18s ease;
      z-index: 19;
    }

    .fx-panel.open {
      opacity: 1;
      pointer-events: auto;
      transform: scale(1) translateY(0);
    }

    .fx-panel-title {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--accent-blue);
      margin-bottom: 4px;
    }

    .fx-panel-sub {
      font-size: 10px;
      color: var(--text-soft);
      margin-bottom: 6px;
    }

    .fx-toggle-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 11px;
      color: var(--text-soft);
      margin-bottom: 4px;
    }

    .fx-toggle-row label {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      cursor: pointer;
    }

    .fx-toggle-row input[type="checkbox"] {
      width: 14px;
      height: 14px;
      border-radius: 4px;
      border: 1px solid rgba(148, 163, 184, 0.7);
      background: #020617;
      appearance: none;
      -webkit-appearance: none;
      outline: none;
      display: inline-block;
      position: relative;
    }

    .fx-toggle-row input[type="checkbox"]:checked {
      border-color: rgba(34, 197, 94, 0.9);
      background: radial-gradient(circle at 30% 15%, #bbf7d0, #22c55e);
      box-shadow: 0 0 12px rgba(34, 197, 94, 0.9);
    }

    .fx-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 4px;
      margin-top: 6px;
    }

    .fx-actions .btn {
      font-size: 9px;
      padding: 5px 8px;
      letter-spacing: 0.12em;
    }

    .toast {
      position: fixed;
      left: 50%;
      bottom: calc(env(safe-area-inset-bottom, 0px) + 78px);
      transform: translateX(-50%) translateY(12px);
      padding: 7px 10px;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.96);
      border: 1px solid rgba(56, 189, 248, 0.75);
      color: var(--text-main);
      font-size: 11px;
      white-space: nowrap;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.18s ease, transform 0.18s ease;
      z-index: 21;
    }

    .toast.show {
      opacity: 1;
      transform: translateX(-50%) translateY(0);
      box-shadow: 0 8px 26px rgba(0, 0, 0, 0.85);
    }

    .modal-backdrop {
      position: fixed;
      inset: 0;
      background: rgba(15, 23, 42, 0.85);
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 18;
      padding: 16px;
    }

    .modal-backdrop.open {
      display: flex;
    }

    .modal {
      width: 100%;
      max-width: 720px;
      border-radius: 18px;
      background: radial-gradient(circle at 0% 0%, rgba(15, 23, 42, 0.98), rgba(15, 23, 42, 1));
      border: 1px solid rgba(56, 189, 248, 0.75);
      box-shadow: var(--shadow-neon);
      padding: 10px 12px 12px;
    }

    .modal-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
      margin-bottom: 6px;
    }

    .modal-title {
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      color: var(--accent-blue);
    }

    .modal-sub {
      font-size: 11px;
      color: var(--text-soft);
      margin-bottom: 6px;
    }

    .modal-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-top: 6px;
    }

    .modal-close-btn {
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.7);
      background: radial-gradient(circle at 30% 20%, #020617, #020617);
      color: var(--text-soft);
      font-size: 10px;
      padding: 4px 9px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      cursor: pointer;
    }

    .modal-close-btn:hover {
      border-color: rgba(248, 113, 113, 0.9);
      color: #fecaca;
    }

    .modal canvas {
      width: 100%;
      max-width: 100%;
      border-radius: 12px;
      background: #020617;
      border: 1px solid rgba(15, 23, 42, 1);
      display: block;
    }

    @media (max-width: 600px) {
      .brand-sub {
        display: none;
      }

      .app-title {
        font-size: 16px;
      }

      .app-subtitle {
        font-size: 12px;
      }

      .panel {
        padding: 9px 8px 10px;
      }

      .log-box,
      .pof-box {
        max-height: 220px;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      * {
        scroll-behavior: auto !important;
        animation-duration: 0s !important;
        transition-duration: 0s !important;
      }
    }
  </style>
</head>

<body class="fx-neon">
  <div class="app-shell">
    <header class="app-header">
      <div class="brand-block">
        <div class="brand-logo">
          <div class="brand-logo-inner">8</div>
        </div>
        <div class="brand-text-wrap">
          <div class="brand-text-main">ACBEATZ.COM</div>
          <div class="brand-sub">MH8 W-FX W-PLANE CONTROLLER • ZERO-ENTROPY POF DEMO</div>
        </div>
      </div>
      <div class="header-pills">
        <div class="pill pill-pill-blue">
          <span class="pill-dot"></span>
          LIVE • W-PLANE RUNTIME
        </div>
        <a
          class="pill pill-pill-green"
          id="btnBrandLink"
          href="https://acbeatz.com"
          target="_blank"
          rel="noopener noreferrer"
        >
          🌐 ACBEATZ.COM
        </a>
      </div>
    </header>

    <div class="app-title-block">
      <h1 class="app-title">MH8 W-FX CONTROLLER — POF RUNTIME UI</h1>
      <p class="app-subtitle">
        3-state deterministic loop: <strong>IDLE / LAG / DART</strong>. Load-gated bursts, null-anchored recovery, human-visible metrics.
      </p>
    </div>

    <main class="layout-grid">
      <section class="panel">
        <div class="panel-header">
          <div class="panel-title">Runtime HUD</div>
          <div class="panel-tag">Controller • MH8-WFX-W-PLANE</div>
        </div>

        <div class="hud-row">
          <div class="hud-card">
            <div class="hud-label">Engine State</div>
            <div class="hud-value state-null" id="hudState">NULL / IDLE</div>
            <div class="hud-sub" id="hudStateDetail">Anchored at zero-point. Waiting for work.</div>
          </div>
          <div class="hud-card">
            <div class="hud-label">Queue Depth</div>
            <div class="hud-value" id="hudQueue">0</div>
            <div class="hud-sub" id="hudQueueDetail">Tasks waiting to be consumed.</div>
          </div>
          <div class="hud-card">
            <div class="hud-label">Cycles • Tasks</div>
            <div class="hud-value" id="hudCycles">0 • 0</div>
            <div class="hud-sub" id="hudCyclesDetail">Committed bursts • processed tasks.</div>
          </div>
          <div class="hud-card">
            <div class="hud-label">Last Entropy</div>
            <div class="hud-value" id="hudEntropy">≈ 0.0000</div>
            <div class="hud-sub" id="hudEntropyDetail">Target: keep this as close to 0.0 as possible.</div>
          </div>
        </div>

        <div class="controls-group">
          <div class="controls-grid">
            <div class="slider-block">
              <div class="slider-top">
                <span class="key">Burst Window (W)</span>
                <span class="value"><span id="labelBurstWindow">20</span>s</span>
              </div>
              <input type="range" id="sliderBurstWindow" min="5" max="60" value="20" />
              <div class="theory-note">
                Time gate: if no burst has fired in W seconds and the queue is non-zero, the controller forces a DART.
              </div>
            </div>
            <div class="slider-block">
              <div class="slider-top">
                <span class="key">Load Factor (L)</span>
                <span class="value"><span id="labelMaxLoad">100</span> tasks</span>
              </div>
              <input type="range" id="sliderMaxLoad" min="10" max="200" value="100" step="10" />
              <div class="theory-note">
                Load gate: if queue ≥ L, the controller DARTs immediately — regardless of time since last burst.
              </div>
            </div>
          </div>

          <div class="controls-grid" style="margin-top:4px;">
            <div>
              <div class="slider-top" style="margin-bottom:3px;">
                <span class="key">Inject Tasks</span>
                <span class="value">Human-driven spikes</span>
              </div>
              <div class="btn-row">
                <button class="btn btn-primary" id="btnAdd1" type="button">
                  <span class="emoji">📥</span> +1 TASK
                </button>
                <button class="btn btn-primary" id="btnAdd10" type="button">
                  <span class="emoji">📥</span> +10 TASKS
                </button>
                <button class="btn btn-ghost" id="btnAdd100" type="button">
                  <span class="emoji">📦</span> +100 BURST
                </button>
              </div>
            </div>
            <div>
              <div class="slider-top" style="margin-bottom:3px;">
                <span class="key">Scenario Demos</span>
                <span class="value">Proof-of-Function runs</span>
              </div>
              <div class="btn-row">
                <button class="btn btn-ghost" id="btnSparseDemo" type="button">
                  <span class="emoji">🌌</span> SPARSE LOAD POF
                </button>
                <button class="btn btn-ghost" id="btnBurstDemo" type="button">
                  <span class="emoji">⚡</span> HIGH LOAD POF
                </button>
                <button class="btn btn-danger" id="btnReset" type="button">
                  <span class="emoji">🧹</span> RESET
                </button>
              </div>
            </div>
          </div>

          <!-- LIVE URL DRIVER / BYPASS DEMO MODE -->
          <div class="live-url-block">
            <div class="slider-top">
              <span class="key">Live URL Driver</span>
              <span class="value" id="liveUrlLabel">Demo mode</span>
            </div>
            <div class="live-url-row">
              <input
                id="liveUrlInput"
                type="url"
                inputmode="url"
                class="live-url-input"
                placeholder="https://your-endpoint.example/live"
                autocomplete="off"
              />
              <button class="btn btn-primary" id="btnSetLiveUrl" type="button">
                <span class="emoji">🌐</span> ADD URL
              </button>
              <button class="btn btn-ghost" id="btnClearLiveUrl" type="button">
                <span class="emoji">🧯</span> DEMO MODE
              </button>
            </div>
            <div class="theory-note" id="liveUrlHelp">
              Paste any reachable HTTP(S) URL and tap <strong>ADD URL</strong> to bypass the canned demos.
              The controller will sample that URL in real time and drive queue load from live network timing.
            </div>
          </div>
        </div>

        <div class="theory-note">
          Controller view (math): <code>σ(t + Δt) = f(σ(t), queue(t), Δt; W, L)</code> — three visible regimes:
          <strong>IDLE / NULL</strong>, <strong>LAG / BUFFER</strong>, <strong>DART / BURST</strong>.
        </div>
      </section>

      <section class="panel">
        <div class="panel-header">
          <div class="panel-title">State Diagram • W-PLANE LOOP</div>
          <div class="panel-header-actions">
            <button class="icon-button" id="btnTargetLoop" type="button">
              <span class="emoji">🎯</span> VISUAL TARGET LOOP
            </button>
            <div class="panel-tag">Visual • ΔS-TARGET LOOP</div>
          </div>
        </div>

        <div class="viz-panel-content">
          <div class="diagram-card">
            <div class="diagram-title">W-PLANE RUNTIME LOOP</div>
            <div class="diagram-sub">
              The engine rests at the zero-point, builds tension in LAG, then DARTS — and always returns to NULL.
            </div>
            <div class="state-diagram">
              <div class="diagram-orbit"></div>
              <div class="diagram-center">W</div>

              <div class="state-node idle active" id="nodeIdle">
                <span class="label-main">NULL</span>
                <span class="label-sub">Idle / zero-point</span>
              </div>

              <div class="state-node lag" id="nodeLag">
                <span class="label-main">LAG</span>
                <span class="label-sub">Buffer / tension</span>
              </div>

              <div class="state-node dart" id="nodeDart">
                <span class="label-main">DART</span>
                <span class="label-sub">Burst / commit</span>
              </div>

              <div class="diagram-arrow arrow-idle-lag"></div>
              <div class="diagram-arrow arrow-lag-dart"></div>
              <div class="diagram-arrow arrow-dart-idle"></div>
            </div>
            <div class="mini-eq">
              <strong>ΔS ≈ 0 loop:</strong> NULL → LAG → DART → NULL<br />
              σ(t + Δt) = f(σ(t), queue(t), Δt; W, L)
            </div>
          </div>

          <!-- LIVE IFRAME VIEWER -->
          <div class="explain-card">
            <div class="viewer-top">
              <h3>Live W-Plane Viewer</h3>
              <span class="panel-tag">IFRAME • LIVE URL FEED</span>
            </div>
            <p class="diagram-sub" style="margin-bottom:4px;">
              This window mirrors the active <strong>Live URL Driver</strong> target. As the W-PLANE loop runs and cycles,
              you can refresh to inspect the latest post-processed feed — or pop it out into its own tab.
            </p>
            <div class="btn-row" style="margin-bottom:4px;">
              <button class="btn btn-ghost" id="btnViewerRefresh" type="button">
                <span class="emoji">🔁</span> REFRESH VIEW
              </button>
              <button class="btn btn-ghost" id="btnViewerOpen" type="button">
                <span class="emoji">🔗</span> OPEN IN TAB
              </button>
              <button class="btn btn-danger" id="btnViewerClear" type="button">
                <span class="emoji">🧯</span> CLEAR FRAME
              </button>
            </div>
            <div class="viewer-frame-wrap">
              <iframe
                id="liveUrlViewer"
                title="MH8 W-Plane Live URL Viewer"
                src="about:blank"
                sandbox="allow-same-origin allow-scripts allow-forms allow-popups"
              ></iframe>
            </div>
            <div class="viewer-footnote" id="viewerUrlDisplay">
              Demo mode: set a Live URL above to mirror it here after each W-PLANE cycle.
            </div>
          </div>
        </div>
      </section>
    </main>

    <section class="panel log-panel">
      <div class="log-layout">
        <div class="log-box">
          <div class="log-header-row">
            <strong>Runtime Event Log</strong>
            <span id="logStats">0 events</span>
          </div>
          <div class="log-body" id="logBody" aria-live="polite" aria-label="Runtime log"></div>
          <div class="log-footer">
            <span id="logHint">Hint: run SPARSE LOAD or HIGH LOAD to watch the loop breathe.</span>
            <span id="logUptime">uptime: 0.0s</span>
          </div>
          <div class="btn-row" style="margin-top:6px; justify-content:flex-end;">
            <button class="btn btn-ghost" id="btnSendRuntimePOF" type="button">
              <span class="emoji">🧵</span> POF R-T-L SEND
            </button>
          </div>
        </div>

        <div class="pof-box">
          <div class="pof-header-row">
            <strong>POF Receipt • MH8-WFX</strong>
            <span class="pof-status-pill" id="pofStatus">PENDING</span>
          </div>
          <div class="btn-row" style="margin:4px 0 3px;">
            <button class="btn btn-primary" id="btnGeneratePOF" type="button">
              <span class="emoji">🧾</span> GENERATE POF RECEIPT
            </button>
            <button class="btn btn-ghost" id="btnCopyPOF" type="button">
              <span class="emoji">📋</span> COPY JSON
            </button>
          </div>
          <div class="pof-body">
            <pre id="pofOutput">// Run one or more demos, then tap "Generate POF Receipt" to seal this controller's behavior.</pre>
          </div>
          <div class="pof-footer">
            Receipt fields: config (W, L), cycles, tasks, queue, entropy, timestamps, trigger mix,
            runtime log summary, and a SHA-256 hash of the canonical JSON payload. Use POF R-T-L SEND
            for a full runtime log payload.
          </div>
        </div>
      </div>
    </section>
  </div>

  <button class="fx-button" id="fxButton" type="button"></button>

  <div class="fx-panel" id="fxPanel">
    <div class="fx-panel-title">FX STACK • MH8-WFX</div>
    <div class="fx-panel-sub">
      Visual & runtime filters for the W-PLANE loop. Great for screenshots and POF runs.
    </div>
    <div class="fx-toggle-row">
      <label>
        <input type="checkbox" id="fxNeonToggle" checked />
        Neon Theme
      </label>
      <span>Electric blue + neon green shell</span>
    </div>
    <div class="fx-toggle-row">
      <label>
        <input type="checkbox" id="fxSlowToggle" />
        Slow-Mo Loop
      </label>
      <span>Slower ticks • more visible transitions</span>
    </div>
    <div class="fx-toggle-row">
      <label>
        <input type="checkbox" id="fxVerboseToggle" checked />
        Verbose Log
      </label>
      <span>Emit low-level debug events</span>
    </div>
    <div class="fx-actions">
      <button class="btn btn-ghost" id="fxPresetSparse" type="button">
        <span class="emoji">🌌</span> RUN SPARSE POF
      </button>
      <button class="btn btn-ghost" id="fxPresetBurst" type="button">
        <span class="emoji">⚡</span> RUN BURST POF
      </button>
      <button class="btn btn-danger" id="fxClear" type="button">
        <span class="emoji">🧼</span> CLEAR LOG
      </button>
    </div>
  </div>

  <div class="modal-backdrop" id="chartModal">
    <div class="modal" role="dialog" aria-modal="true" aria-labelledby="chartModalTitle">
      <div class="modal-header">
        <div class="modal-title" id="chartModalTitle">Visual Target Loop — Runtime Chart</div>
        <button class="modal-close-btn" id="btnCloseChart" type="button">CLOSE</button>
      </div>
      <div class="modal-sub">
        This graph shows how the queue size changes over time while the W-PLANE loop runs. Use it as a quick visual Proof-of-Function snapshot.
      </div>
      <canvas id="runtimeChart" width="720" height="260"></canvas>
      <div class="modal-actions">
        <button class="btn btn-ghost" id="btnChartPng" type="button">
          <span class="emoji">🖼️</span> DOWNLOAD PNG
        </button>
        <button class="btn btn-ghost" id="btnChartSvg" type="button">
          <span class="emoji">📄</span> COPY SVG PAYLOAD
        </button>
      </div>
    </div>
  </div>

  <div class="toast" id="toast"></div>

  <script>
    document.addEventListener("DOMContentLoaded", () => {
      const hudState = document.getElementById("hudState");
      const hudStateDetail = document.getElementById("hudStateDetail");
      const hudQueue = document.getElementById("hudQueue");
      const hudQueueDetail = document.getElementById("hudQueueDetail");
      const hudCycles = document.getElementById("hudCycles");
      const hudCyclesDetail = document.getElementById("hudCyclesDetail");
      const hudEntropy = document.getElementById("hudEntropy");
      const hudEntropyDetail = document.getElementById("hudEntropyDetail");

      const nodeIdle = document.getElementById("nodeIdle");
      const nodeLag = document.getElementById("nodeLag");
      const nodeDart = document.getElementById("nodeDart");

      const sliderBurstWindow = document.getElementById("sliderBurstWindow");
      const sliderMaxLoad = document.getElementById("sliderMaxLoad");
      const labelBurstWindow = document.getElementById("labelBurstWindow");
      const labelMaxLoad = document.getElementById("labelMaxLoad");

      const btnAdd1 = document.getElementById("btnAdd1");
      const btnAdd10 = document.getElementById("btnAdd10");
      const btnAdd100 = document.getElementById("btnAdd100");
      const btnSparseDemo = document.getElementById("btnSparseDemo");
      const btnBurstDemo = document.getElementById("btnBurstDemo");
      const btnReset = document.getElementById("btnReset");

      const logBody = document.getElementById("logBody");
      const logStats = document.getElementById("logStats");
      const logHint = document.getElementById("logHint");
      const logUptime = document.getElementById("logUptime");

      const btnGeneratePOF = document.getElementById("btnGeneratePOF");
      const btnCopyPOF = document.getElementById("btnCopyPOF");
      const pofOutput = document.getElementById("pofOutput");
      const pofStatus = document.getElementById("pofStatus");

      const fxButton = document.getElementById("fxButton");
      const fxPanel = document.getElementById("fxPanel");
      const fxNeonToggle = document.getElementById("fxNeonToggle");
      const fxSlowToggle = document.getElementById("fxSlowToggle");
      const fxVerboseToggle = document.getElementById("fxVerboseToggle");
      const fxPresetSparse = document.getElementById("fxPresetSparse");
      const fxPresetBurst = document.getElementById("fxPresetBurst");
      const fxClear = document.getElementById("fxClear");
      const toast = document.getElementById("toast");

      const btnSendRuntimePOF = document.getElementById("btnSendRuntimePOF");

      const chartModal = document.getElementById("chartModal");
      const chartCanvas = document.getElementById("runtimeChart");
      const btnCloseChart = document.getElementById("btnCloseChart");
      const btnChartPng = document.getElementById("btnChartPng");
      const btnChartSvg = document.getElementById("btnChartSvg");
      const btnTargetLoop = document.getElementById("btnTargetLoop");

      const liveUrlInput = document.getElementById("liveUrlInput");
      const btnSetLiveUrl = document.getElementById("btnSetLiveUrl");
      const btnClearLiveUrl = document.getElementById("btnClearLiveUrl");
      const liveUrlLabel = document.getElementById("liveUrlLabel");
      const liveUrlHelp = document.getElementById("liveUrlHelp");
      const liveUrlViewer = document.getElementById("liveUrlViewer");
      const btnViewerRefresh = document.getElementById("btnViewerRefresh");
      const btnViewerOpen = document.getElementById("btnViewerOpen");
      const btnViewerClear = document.getElementById("btnViewerClear");
      const viewerUrlDisplay = document.getElementById("viewerUrlDisplay");

      const state = {
        controllerId: "MH8-WFX-W-PLANE-DEMO",
        version: "1.0",
        engineState: "NULL", // NULL, LAG, DART
        queueSize: 0,
        cyclesCompleted: 0,
        totalTasksProcessed: 0,
        lastEntropy: 0.0,
        lastDartReason: null,
        lastDartAt: null,
        burstWindow: Number(sliderBurstWindow.value),
        maxLoad: Number(sliderMaxLoad.value),
        wakeCostMs: 50,
        tickIntervalMs: 180,
        timerId: null,
        startedAt: Date.now(),
        verboseLog: true,
        sparseDemoTimers: [],
        burstDemoTimers: [],
        hasEverDarted: false,
        runtimeLog: [],
        runtimeSamples: [],
        liveUrl: null,
        liveUrlTimerId: null,
        liveUrlSampleMs: 5000,
        viewerLastLoadAt: null
      };

      function showToast(message) {
        if (!toast) return;
        toast.textContent = message;
        toast.classList.add("show");
        clearTimeout(toast._hideTimer);
        toast._hideTimer = setTimeout(() => {
          toast.classList.remove("show");
        }, 1500);
      }

      function safeVibrate(ms) {
        try {
          if (navigator.vibrate) navigator.vibrate(ms);
        } catch (e) {
          /* ignore */
        }
      }

      function formatTime(ts) {
        const d = new Date(ts);
        const h = String(d.getHours()).padStart(2, "0");
        const m = String(d.getMinutes()).padStart(2, "0");
        const s = String(d.getSeconds()).padStart(2, "0");
        return h + ":" + m + ":" + s;
      }

      // --- NEW: Robust URL normalizer for iframe viewer (YouTube/Vimeo friendly) ---
      function normalizeViewerUrl(raw) {
        if (!raw) return "";
        let urlString = raw.trim();
        if (!/^https?:\/\//i.test(urlString)) {
          urlString = "https://" + urlString;
        }
        let u;
        try {
          u = new URL(urlString);
        } catch (e) {
          return urlString;
        }

        const host = u.hostname.toLowerCase();
        const path = u.pathname || "";

        // YouTube share URLs (youtu.be/VIDEO_ID)
        if (host === "youtu.be") {
          const id = path.replace(/^\/+/, "").split(/[?&]/)[0];
          if (id) {
            return "https://www.youtube.com/embed/" + id;
          }
        }

        // YouTube watch / shorts / generic
        if (host.endsWith("youtube.com")) {
          // /watch?v=VIDEO_ID
          if (path === "/watch" || path === "/") {
            const v = u.searchParams.get("v");
            if (v) {
              return "https://www.youtube.com/embed/" + v;
            }
          }
          // /shorts/VIDEO_ID
          if (path.startsWith("/shorts/")) {
            const parts = path.split("/");
            const id = parts[2];
            if (id) {
              return "https://www.youtube.com/embed/" + id;
            }
          }
          // Other YouTube paths (embed, playlist, etc.) — pass through
          return u.toString();
        }

        // Vimeo simple IDs (vimeo.com/123456789)
        if (host.endsWith("vimeo.com")) {
          const parts = path.split("/").filter(Boolean);
          const id = parts[0];
          if (id && /^[0-9]+$/.test(id)) {
            return "https://player.vimeo.com/video/" + id;
          }
        }

        return u.toString();
      }

      // --- NEW: Adjust iframe sandbox/allow for media hosts so players can run correctly ---
      function updateViewerSandboxForUrl(urlString) {
        if (!liveUrlViewer) return;
        if (!urlString) {
          liveUrlViewer.setAttribute(
            "sandbox",
            "allow-same-origin allow-scripts allow-forms allow-popups"
          );
          liveUrlViewer.removeAttribute("allow");
          liveUrlViewer.removeAttribute("allowfullscreen");
          return;
        }

        let host = "";
        try {
          const u = new URL(urlString);
          host = u.hostname.toLowerCase();
        } catch (e) {
          host = "";
        }

        const isMediaHost =
          host.endsWith("youtube.com") ||
          host === "youtu.be" ||
          host.endsWith("vimeo.com") ||
          host.endsWith("twitch.tv");

        if (isMediaHost) {
          // For rich media players (YouTube/Vimeo/Twitch), drop sandbox and grant playback permissions
          liveUrlViewer.removeAttribute("sandbox");
          liveUrlViewer.setAttribute(
            "allow",
            "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; fullscreen"
          );
          liveUrlViewer.setAttribute("allowfullscreen", "true");
        } else {
          // Default sandboxed mode for generic web endpoints
          liveUrlViewer.setAttribute(
            "sandbox",
            "allow-same-origin allow-scripts allow-forms allow-popups"
          );
          liveUrlViewer.removeAttribute("allowfullscreen");
          liveUrlViewer.removeAttribute("allow");
        }
      }

      function appendLog(message, kind = "info") {
        if (!logBody) return;
        const now = Date.now();
        const tsString = formatTime(now);
        const logItem = { ts: tsString, kind, message };
        state.runtimeLog.push(logItem);
        if (state.runtimeLog.length > 500) {
          state.runtimeLog.shift();
        }

        const entry = document.createElement("div");
        entry.className = "log-entry " + kind;

        const tsSpan = document.createElement("span");
        tsSpan.className = "ts";
        tsSpan.textContent = tsString;

        const msgSpan = document.createElement("span");
        msgSpan.className = "msg";
        msgSpan.textContent = message;

        entry.appendChild(tsSpan);
        entry.appendChild(msgSpan);
        logBody.appendChild(entry);

        while (logBody.children.length > 160) {
          logBody.removeChild(logBody.firstChild);
        }

        logBody.scrollTop = logBody.scrollHeight;
        logStats.textContent = logBody.children.length + " events";
      }

      function recordSample(elapsedSec) {
        const sample = {
          t: Number(elapsedSec.toFixed(2)),
          queue: state.queueSize,
          engineState: state.engineState
        };
        state.runtimeSamples.push(sample);
        if (state.runtimeSamples.length > 600) {
          state.runtimeSamples.shift();
        }
      }

      function updateHud() {
        const q = state.queueSize;
        const s = state.engineState;

        hudQueue.textContent = String(q);

        if (q === 0) {
          hudQueueDetail.textContent = "Queue is empty. Engine can rest at NULL.";
        } else if (q < state.maxLoad) {
          hudQueueDetail.textContent = "Buffering in LAG. Under load threshold L.";
        } else {
          hudQueueDetail.textContent = "Load ≥ L. Next tick will DART in burst mode.";
        }

        hudCycles.textContent =
          state.cyclesCompleted.toString() + " • " + state.totalTasksProcessed.toString();

        if (state.cyclesCompleted === 0) {
          hudCyclesDetail.textContent = "No bursts yet. Run a demo to prove the loop.";
        } else {
          hudCyclesDetail.textContent =
            "Committed bursts • processed tasks across this POF session.";
        }

        hudEntropy.textContent = "≈ " + state.lastEntropy.toFixed(4);
        if (state.cyclesCompleted === 0) {
          hudEntropyDetail.textContent =
            "Entropy will update after the first DART/COMMIT cycle.";
        } else if (state.lastEntropy <= 0.02) {
          hudEntropyDetail.textContent =
            "Low-drift cycle. ΔS is close to 0 — this is what we want.";
        } else {
          hudEntropyDetail.textContent =
            "Higher entropy this cycle. Adjust W and L to tighten the loop.";
        }

        hudState.classList.remove("state-null", "state-lag", "state-dart");
        nodeIdle.classList.remove("active");
        nodeLag.classList.remove("active");
        nodeDart.classList.remove("active");

        if (s === "NULL") {
          hudState.textContent = "NULL / IDLE";
          hudState.classList.add("state-null");
          hudStateDetail.textContent = "Anchored at the zero-point. Energy-saving mode.";
          nodeIdle.classList.add("active");
        } else if (s === "LAG") {
          hudState.textContent = "LAG / BUFFER";
          hudState.classList.add("state-lag");
          hudStateDetail.textContent =
            "Tasks are accumulating, but W and L haven’t forced a DART yet.";
          nodeLag.classList.add("active");
        } else if (s === "DART") {
          hudState.textContent = "DART / BURST";
          hudState.classList.add("state-dart");
          hudStateDetail.textContent =
            "Bursting through the queue. This is the high-efficiency compute phase.";
          nodeDart.classList.add("active");
        }

        const elapsedSec = (Date.now() - state.startedAt) / 1000;
        logUptime.textContent = "uptime: " + elapsedSec.toFixed(1) + "s";

        recordSample(elapsedSec);
      }

      function setEngineState(newState) {
        state.engineState = newState;
        updateHud();
      }

      function addTasks(count) {
        if (count <= 0) return;
        state.queueSize += count;
        appendLog(
          "📥 Task arrival: +" +
            count +
            " (queue = " +
            state.queueSize +
            "). State = " +
            state.engineState +
            ".",
          "queue"
        );
        logHint.textContent =
          "Watch for LAG (buffering) then DART when W or L thresholds are hit.";
        updateHud();
      }

      function clearAllScenarioTimers() {
        state.sparseDemoTimers.forEach((t) => clearTimeout(t));
        state.burstDemoTimers.forEach((t) => clearTimeout(t));
        state.sparseDemoTimers = [];
        state.burstDemoTimers = [];
      }

      function stopLiveUrlMode() {
        if (state.liveUrlTimerId) {
          clearInterval(state.liveUrlTimerId);
          state.liveUrlTimerId = null;
        }
      }

      function updateLiveUrlUi() {
        if (!liveUrlLabel || !liveUrlHelp) return;

        if (state.liveUrl) {
          try {
            const u = new URL(state.liveUrl);
            liveUrlLabel.textContent = "Live: " + (u.hostname || state.liveUrl);
          } catch (e) {
            liveUrlLabel.textContent = "Live: " + state.liveUrl;
          }

          liveUrlHelp.innerHTML =
            "Live mode ON. Queue load is being driven by sampling <strong>" +
            state.liveUrl +
            "</strong> in real time. Demo presets are bypassed.";

          if (viewerUrlDisplay) {
            viewerUrlDisplay.textContent = "Mirroring: " + state.liveUrl;
          }
        } else {
          liveUrlLabel.textContent = "Demo mode";
          liveUrlHelp.innerHTML =
            'Paste any reachable HTTP(S) URL and tap <strong>ADD URL</strong> to drive the queue from live network timing. In demo mode, use SPARSE / HIGH LOAD presets instead.';
          if (viewerUrlDisplay) {
            viewerUrlDisplay.textContent =
              "Demo mode: set a Live URL above to mirror it here after each W-PLANE cycle.";
          }
          if (liveUrlViewer) {
            liveUrlViewer.src = "about:blank";
            if (liveUrlViewer.dataset) {
              liveUrlViewer.dataset.src = "about:blank";
            }
            updateViewerSandboxForUrl(null);
          }
        }
      }

      function refreshViewerFromLiveUrl(forceReload) {
        if (!liveUrlViewer) return;

        if (!state.liveUrl) {
          liveUrlViewer.src = "about:blank";
          if (liveUrlViewer.dataset) {
            liveUrlViewer.dataset.src = "about:blank";
          }
          if (viewerUrlDisplay) {
            viewerUrlDisplay.textContent =
              "Demo mode: set a Live URL above to mirror it here after each W-PLANE cycle.";
          }
          updateViewerSandboxForUrl(null);
          return;
        }

        const viewerBase = normalizeViewerUrl(state.liveUrl);
        const nextSrc = viewerBase;
        const current = liveUrlViewer.dataset ? liveUrlViewer.dataset.src : null;

        if (!forceReload && current === nextSrc) {
          return;
        }

        if (liveUrlViewer.dataset) {
          liveUrlViewer.dataset.src = nextSrc;
        }

        updateViewerSandboxForUrl(nextSrc);
        liveUrlViewer.src = nextSrc;
        state.viewerLastLoadAt = Date.now();

        if (viewerUrlDisplay) {
          viewerUrlDisplay.textContent = "Mirroring: " + state.liveUrl;
        }
      }

      function startLiveUrlMode() {
        stopLiveUrlMode();
        if (!state.liveUrl) {
          updateLiveUrlUi();
          return;
        }

        clearAllScenarioTimers();
        appendLog(
          "🌐 Live URL driver enabled. Sampling " +
            state.liveUrl +
            " every " +
            (state.liveUrlSampleMs / 1000).toFixed(1) +
            "s.",
          "info"
        );
        logHint.textContent =
          "Live URL mode: queue load is being driven by real network timing, not canned demos.";

        updateLiveUrlUi();
        refreshViewerFromLiveUrl(true);

        state.liveUrlTimerId = setInterval(async () => {
          const url = state.liveUrl;
          if (!url) return;

          const t0 =
            window.performance && performance.now ? performance.now() : Date.now();

          try {
            const supportsAbort = typeof AbortController !== "undefined";
            let controller = null;
            let timeoutId = null;

            if (supportsAbort) {
              controller = new AbortController();
              timeoutId = setTimeout(() => controller.abort(), 7000);
            }

            await fetch(
              url,
              supportsAbort
                ? { mode: "no-cors", signal: controller.signal }
                : { mode: "no-cors" }
            );

            if (supportsAbort && timeoutId) clearTimeout(timeoutId);

            const t1 =
              window.performance && performance.now ? performance.now() : Date.now();
            const elapsed = t1 - t0;

            const tasks = Math.max(1, Math.min(200, Math.round(elapsed / 40)));
            addTasks(tasks);

            if (state.verboseLog) {
              appendLog(
                "🌐 Live URL sample OK (" +
                  elapsed.toFixed(0) +
                  "ms) → +" +
                  tasks +
                  " tasks from " +
                  url +
                  ".",
                "queue"
              );
            }
          } catch (err) {
            const t1 =
              window.performance && performance.now ? performance.now() : Date.now();
            const elapsed = t1 - t0;
            const fallbackTasks = Math.max(
              1,
              Math.min(50, Math.round(elapsed / 80))
            );
            addTasks(fallbackTasks);
            appendLog(
              "⚠️ Live URL sample error for " +
                url +
                " (elapsed ≈ " +
                elapsed.toFixed(0) +
                "ms). Injecting +" +
                fallbackTasks +
                " fallback tasks to keep loop live.",
              "warn"
            );
          }
        }, state.liveUrlSampleMs);
      }

      function processBurst(triggerReason) {
        if (state.queueSize <= 0) return;
        if (state.engineState === "DART") return;

        const now = Date.now();
        const batchSize = Math.min(state.queueSize, state.maxLoad * 2);

        state.engineState = "DART";
        state.lastDartReason = triggerReason;
        state.lastDartAt = now;
        state.hasEverDarted = true;

        appendLog(
          "⚡ /dart → Entering DART. Trigger = " +
            triggerReason.toUpperCase() +
            ", batch size = " +
            batchSize +
            ".",
          "dart"
        );
        updateHud();

        const base = 40;
        const perTask = 3;
        const durationMs = base + perTask * batchSize;

        setTimeout(() => {
          state.queueSize -= batchSize;
          if (state.queueSize < 0) state.queueSize = 0;

          const cycleSeconds = (durationMs + state.wakeCostMs) / 1000;
          const entropy = cycleSeconds * 0.01;

          state.cyclesCompleted += 1;
          state.totalTasksProcessed += batchSize;
          state.lastEntropy = entropy;

          appendLog(
            "✅ /commit → Cycle " +
              state.cyclesCompleted +
              " closed in " +
              cycleSeconds.toFixed(3) +
              "s, entropy ≈ " +
              entropy.toFixed(4) +
              ". Queue now = " +
              state.queueSize +
              ".",
            "commit"
          );

          state.engineState = state.queueSize > 0 ? "LAG" : "NULL";
          appendLog(
            "🌀 /knot → Returned to " + state.engineState + " after commit.",
            "info"
          );

          if (state.liveUrl) {
            // After each completed cycle, re-sync the viewer with the current live URL target
            refreshViewerFromLiveUrl(false);
          }

          updateHud();
        }, durationMs);
      }

      function schedulerTick() {
        const now = Date.now();
        if (state.engineState === "DART") {
          updateHud();
          return;
        }

        const lastDartTime = state.lastDartAt || state.startedAt;
        const timeSinceDartSec = (now - lastDartTime) / 1000;
        const q = state.queueSize;

        const shouldDartByLoad = q >= state.maxLoad;
        const shouldDartByTime = q > 0 && timeSinceDartSec >= state.burstWindow;

        if (shouldDartByLoad || shouldDartByTime) {
          const reason = shouldDartByLoad ? "load" : "time";
          processBurst(reason);
        } else {
          if (q === 0) {
            if (state.engineState !== "NULL" && state.verboseLog) {
              appendLog(
                "🌀 Maintaining NULL: no work available, queue = 0.",
                "info"
              );
            }
            state.engineState = "NULL";
          } else {
            if (state.engineState !== "LAG" && state.verboseLog) {
              appendLog(
                "⏳ Entering LAG: queue = " +
                  q +
                  ", waiting for W or L to justify a DART.",
                "info"
              );
            }
            state.engineState = "LAG";
          }
          updateHud();
        }
      }

      function startScheduler() {
        if (state.timerId) clearInterval(state.timerId);
        state.timerId = setInterval(schedulerTick, state.tickIntervalMs);
      }

      function resetController() {
        clearAllScenarioTimers();
        stopLiveUrlMode();
        if (state.timerId) clearInterval(state.timerId);

        state.engineState = "NULL";
        state.queueSize = 0;
        state.cyclesCompleted = 0;
        state.totalTasksProcessed = 0;
        state.lastEntropy = 0;
        state.lastDartReason = null;
        state.lastDartAt = null;
        state.startedAt = Date.now();
        state.hasEverDarted = false;
        state.tickIntervalMs = fxSlowToggle.checked ? 450 : 180;
        state.runtimeLog = [];
        state.runtimeSamples = [];
        state.liveUrl = null;
        state.viewerLastLoadAt = null;

        logBody.innerHTML = "";
        logStats.textContent = "0 events";
        logHint.textContent =
          "Hint: run SPARSE LOAD or HIGH LOAD to watch the loop breathe.";

        pofOutput.textContent =
          '// Run one or more demos, then tap "Generate POF Receipt" to seal this controller\'s behavior.';
        pofStatus.textContent = "PENDING";
        pofStatus.classList.remove("fail");

        updateLiveUrlUi();

        appendLog(
          "MH8-WFX W-PLANE controller reset. Zero-point re-established at NULL.",
          "info"
        );
        updateHud();
        startScheduler();
      }

      async function sha256Hex(str) {
        try {
          if (!window.crypto || !crypto.subtle || !window.TextEncoder) return null;
          const data = new TextEncoder().encode(str);
          const hashBuffer = await crypto.subtle.digest("SHA-256", data);
          const hashArray = Array.from(new Uint8Array(hashBuffer));
          return hashArray.map((b) => b.toString(16).padStart(2, "0")).join("");
        } catch (e) {
          console.warn("SHA-256 digest failed:", e);
          return null;
        }
      }

      function buildRuntimeLogSummary() {
        const total = state.runtimeLog.length;
        const tail = total > 0 ? state.runtimeLog.slice(-5) : [];
        return {
          total_events: total,
          sample_tail: tail
        };
      }

      async function generatePOFReceipt(includeRuntimeLog = false) {
        const nowIso = new Date().toISOString();
        const elapsedSec = (Date.now() - state.startedAt) / 1000;
        const runtimeSummary = buildRuntimeLogSummary();

        const receipt = {
          controller_id: state.controllerId,
          version: state.version,
          timestamp: nowIso,
          runtime_seconds: Number(elapsedSec.toFixed(3)),
          config: {
            burst_window_W_seconds: state.burstWindow,
            max_task_load_L: state.maxLoad,
            wake_return_cost_seconds: state.wakeCostMs / 1000
          },
          metrics: {
            cycles_completed: state.cyclesCompleted,
            total_tasks_processed: state.totalTasksProcessed,
            queue_size_final: state.queueSize,
            last_entropy_cycle: Number(state.lastEntropy.toFixed(6)),
            has_ever_darted: state.hasEverDarted,
            last_dart_reason: state.lastDartReason || "none"
          },
          constraints: {
            idle_when_queue_zero:
              state.queueSize === 0 && state.engineState === "NULL",
            bounded_queue: state.totalTasksProcessed >= state.queueSize,
            three_state_loop: ["NULL", "LAG", "DART"].includes(state.engineState)
          },
          fx_profile: {
            neon_theme: fxNeonToggle.checked,
            slow_motion: fxSlowToggle.checked,
            verbose_log: fxVerboseToggle.checked
          },
          runtime_log_summary: runtimeSummary,
          note:
            "POF demo only — this JSON is sealable and replayable as a human-visible proof-of-function for MH8-WFX W-PLANE runtime."
        };

        if (includeRuntimeLog) {
          receipt.runtime_log_full = state.runtimeLog.slice();
        }

        const payloadCanonical = JSON.stringify(receipt, null, 2);
        const hash = await sha256Hex(payloadCanonical);
        if (hash) {
          receipt.pof_sha256 = hash;
        }

        const finalPayload = JSON.stringify(receipt, null, 2);
        pofOutput.textContent = finalPayload;

        const pass =
          state.hasEverDarted &&
          state.cyclesCompleted > 0 &&
          state.totalTasksProcessed > 0 &&
          state.queueSize === 0;

        if (pass) {
          pofStatus.textContent = "PASS • ΔS LOOP CLOSED";
          pofStatus.classList.remove("fail");
          appendLog(
            "🧾 POF PASS: controller completed at least one burst, drained queue to 0, and returned to NULL.",
            "info"
          );
        } else {
          pofStatus.textContent = "CHECK • LOOP PARTIAL";
          pofStatus.classList.add("fail");
          appendLog(
            "🧾 POF CHECK: controller has not fully closed the loop yet. Run sparse/burst demos until queue drains.",
            "warn"
          );
        }

        showToast(
          includeRuntimeLog
            ? "Runtime log POF payload generated."
            : "POF receipt generated."
        );
      }

      async function copyPOFToClipboard() {
        const text = pofOutput.textContent || "";
        if (!text.trim()) {
          showToast("Nothing to copy yet.");
          return;
        }
        try {
          if (navigator.clipboard && navigator.clipboard.writeText) {
            await navigator.clipboard.writeText(text);
          } else {
            const ta = document.createElement("textarea");
            ta.value = text;
            ta.style.position = "fixed";
            ta.style.left = "-9999px";
            document.body.appendChild(ta);
            ta.focus();
            ta.select();
            document.execCommand("copy");
            document.body.removeChild(ta);
          }
          showToast("POF JSON copied to clipboard.");
          safeVibrate(10);
        } catch (e) {
          console.error("Copy failed:", e);
          showToast("Copy failed. Try manual select + copy.");
        }
      }

      function drawRuntimeChart() {
        if (!chartCanvas || !chartCanvas.getContext) return;
        const ctx = chartCanvas.getContext("2d");
        const samples =
          state.runtimeSamples && state.runtimeSamples.length
            ? state.runtimeSamples
            : [];
        const w = chartCanvas.width;
        const h = chartCanvas.height;

        ctx.clearRect(0, 0, w, h);
        ctx.fillStyle = "#020617";
        ctx.fillRect(0, 0, w, h);

        ctx.font = "11px Inter, system-ui, sans-serif";
        ctx.fillStyle = "#94a3b8";

        if (!samples.length) {
          ctx.fillText(
            "Run a POF demo to see queue vs. time here.",
            24,
            h / 2
          );
          return;
        }

        const marginLeft = 40;
        const marginRight = 10;
        const marginTop = 15;
        const marginBottom = 24;

        const tMin = samples[0].t;
        const tMax = samples[samples.length - 1].t;
        const qMax =
          samples.reduce((max, s) => (s.queue > max ? s.queue : max), 0) || 1;

        const plotW = w - marginLeft - marginRight;
        const plotH = h - marginTop - marginBottom;

        ctx.strokeStyle = "#64748b";
        ctx.lineWidth = 1;
        ctx.beginPath();
        ctx.moveTo(marginLeft, marginTop);
        ctx.lineTo(marginLeft, h - marginBottom);
        ctx.lineTo(w - marginRight, h - marginBottom);
        ctx.stroke();

        ctx.fillText("Queue size", 6, marginTop + 4);
        ctx.fillText("Time (s)", w - 80, h - 8);
        ctx.fillText(String(qMax), 6, marginTop + 4);

        ctx.beginPath();
        samples.forEach((s, idx) => {
          const x =
            marginLeft +
            ((s.t - tMin) / (tMax - tMin || 1)) * plotW;
          const y =
            h - marginBottom - (s.queue / qMax) * plotH;
          if (idx === 0) {
            ctx.moveTo(x, y);
          } else {
            ctx.lineTo(x, y);
          }
        });

        ctx.strokeStyle = "#38bdf8";
        ctx.lineWidth = 1.4;
        ctx.stroke();

        ctx.lineTo(marginLeft + plotW, h - marginBottom);
        ctx.lineTo(marginLeft, h - marginBottom);
        ctx.closePath();
        ctx.globalAlpha = 0.12;
        ctx.fillStyle = "#22c55e";
        ctx.fill();
        ctx.globalAlpha = 1;

        const label =
          "samples: " +
          samples.length +
          " • t: " +
          tMin.toFixed(1) +
          "–" +
          tMax.toFixed(1) +
          "s";
        ctx.fillStyle = "#94a3b8";
        ctx.fillText(label, marginLeft + 4, marginTop + 14);
      }

      function buildRuntimeSvg() {
        const samples =
          state.runtimeSamples && state.runtimeSamples.length
            ? state.runtimeSamples
            : [];
        const w = 800;
        const h = 320;

        const marginLeft = 40;
        const marginRight = 20;
        const marginTop = 20;
        const marginBottom = 30;

        const plotW = w - marginLeft - marginRight;
        const plotH = h - marginTop - marginBottom;

        let svg =
          '<svg xmlns="http://www.w3.org/2000/svg" width="' +
          w +
          '" height="' +
          h +
          '" viewBox="0 0 ' +
          w +
          " " +
          h +
          '" fill="none">';
        svg +=
          '<rect width="' +
          w +
          '" height="' +
          h +
          '" fill="#020617"/>';
        svg += '<g stroke="#64748b" stroke-width="1">';
        svg +=
          '<line x1="' +
          marginLeft +
          '" y1="' +
          marginTop +
          '" x2="' +
          marginLeft +
          '" y2="' +
          (h - marginBottom) +
          '"/>';
        svg +=
          '<line x1="' +
          marginLeft +
          '" y1="' +
          (h - marginBottom) +
          '" x2="' +
          (w - marginRight) +
          '" y2="' +
          (h - marginBottom) +
          '"/>';
        svg += "</g>";

        if (!samples.length) {
          svg +=
            '<text x="24" y="' +
            h / 2 +
            '" fill="#94a3b8" font-size="12">Run a POF demo to see queue vs. time.</text>';
          svg += "</svg>";
          return svg;
        }

        const tMin = samples[0].t;
        const tMax = samples[samples.length - 1].t;
        const qMax =
          samples.reduce((max, s) => (s.queue > max ? s.queue : max), 0) || 1;

        let points = "";
        samples.forEach((s) => {
          const x =
            marginLeft +
            ((s.t - tMin) / (tMax - tMin || 1)) * plotW;
          const y =
            h - marginBottom - (s.queue / qMax) * plotH;
          points += x.toFixed(2) + "," + y.toFixed(2) + " ";
        });

        svg +=
          '<polyline points="' +
          points.trim() +
          '" fill="none" stroke="#38bdf8" stroke-width="1.5"/>';
        svg += "</svg>";

        return svg;
      }

      function openChartModal() {
        if (!chartModal) return;
        chartModal.classList.add("open");
        drawRuntimeChart();
      }

      function closeChartModal() {
        if (!chartModal) return;
        chartModal.classList.remove("open");
      }

      // === EVENT WIRING ===
      sliderBurstWindow.addEventListener("input", () => {
        state.burstWindow = Number(sliderBurstWindow.value);
        labelBurstWindow.textContent = state.burstWindow.toString();
        appendLog(
          "Config updated: Burst Window W = " + state.burstWindow + " seconds.",
          "info"
        );
        updateHud();
      });

      sliderMaxLoad.addEventListener("input", () => {
        state.maxLoad = Number(sliderMaxLoad.value);
        labelMaxLoad.textContent = state.maxLoad.toString();
        appendLog(
          "Config updated: Load Factor L = " + state.maxLoad + " tasks.",
          "info"
        );
        updateHud();
      });

      btnAdd1.addEventListener("click", () => {
        addTasks(1);
        safeVibrate(8);
      });

      btnAdd10.addEventListener("click", () => {
        addTasks(10);
        safeVibrate(10);
      });

      btnAdd100.addEventListener("click", () => {
        addTasks(100);
        safeVibrate(14);
      });

      btnSparseDemo.addEventListener("click", () => {
        stopLiveUrlMode();
        state.liveUrl = null;
        updateLiveUrlUi();

        clearAllScenarioTimers();
        appendLog(
          "🌌 Starting SPARSE LOAD POF: low-frequency arrivals to showcase NULL / LAG / DART visibility.",
          "info"
        );

        const bursts = [1, 1, 2, 1];
        let delay = 500;
        bursts.forEach((count) => {
          const t = setTimeout(() => addTasks(count), delay);
          state.sparseDemoTimers.push(t);
          delay += 4000 + Math.random() * 3000;
        });
        safeVibrate(14);
      });

      btnBurstDemo.addEventListener("click", () => {
        stopLiveUrlMode();
        state.liveUrl = null;
        updateLiveUrlUi();

        clearAllScenarioTimers();
        appendLog(
          "⚡ Starting HIGH LOAD POF: injecting 150 tasks to force a load-driven DART sequence.",
          "info"
        );
        const t1 = setTimeout(() => addTasks(80), 600);
        const t2 = setTimeout(() => addTasks(70), 2200);
        state.burstDemoTimers.push(t1, t2);
        safeVibrate(16);
      });

      btnReset.addEventListener("click", () => {
        resetController();
        safeVibrate(12);
      });

      btnGeneratePOF.addEventListener("click", () => {
        generatePOFReceipt(false);
        safeVibrate(10);
      });

      btnCopyPOF.addEventListener("click", () => {
        copyPOFToClipboard();
      });

      btnSendRuntimePOF.addEventListener("click", () => {
        generatePOFReceipt(true);
        appendLog(
          "🧵 POF R-T-L SEND: full runtime event log sealed into receipt payload.",
          "info"
        );
        safeVibrate(12);
      });

      fxButton.addEventListener("click", () => {
        fxPanel.classList.toggle("open");
        safeVibrate(8);
      });

      fxNeonToggle.addEventListener("change", () => {
        if (fxNeonToggle.checked) {
          document.body.classList.add("fx-neon");
          appendLog("FX: Neon shell enabled.", "info");
        } else {
          document.body.classList.remove("fx-neon");
          appendLog("FX: Neon shell disabled (clean mode).", "info");
        }
      });

      fxSlowToggle.addEventListener("change", () => {
        state.tickIntervalMs = fxSlowToggle.checked ? 450 : 180;
        appendLog(
          "FX: Slow-Mo " +
            (fxSlowToggle.checked ? "ON (slower ticks)." : "OFF (normal ticks)."),
          "info"
        );
        startScheduler();
      });

      fxVerboseToggle.addEventListener("change", () => {
        state.verboseLog = fxVerboseToggle.checked;
        appendLog(
          "FX: Verbose log " +
            (fxVerboseToggle.checked ? "enabled." : "muted for steady-state only."),
          "info"
        );
      });

      fxPresetSparse.addEventListener("click", () => {
        btnSparseDemo.click();
        showToast("Sparse load POF demo triggered.");
      });

      fxPresetBurst.addEventListener("click", () => {
        btnBurstDemo.click();
        showToast("High load POF demo triggered.");
      });

      fxClear.addEventListener("click", () => {
        logBody.innerHTML = "";
        logStats.textContent = "0 events";
        state.runtimeLog = [];
        appendLog("Log cleared via FX stack.", "info");
        safeVibrate(8);
      });

      document.addEventListener("click", (e) => {
        if (
          fxPanel &&
          !fxPanel.contains(e.target) &&
          e.target !== fxButton &&
          fxPanel.classList.contains("open")
        ) {
          fxPanel.classList.remove("open");
        }
      });

      btnTargetLoop.addEventListener("click", () => {
        openChartModal();
        showToast("Runtime chart opened.");
        safeVibrate(10);
      });

      btnCloseChart.addEventListener("click", () => {
        closeChartModal();
        safeVibrate(8);
      });

      chartModal.addEventListener("click", (e) => {
        if (e.target === chartModal) {
          closeChartModal();
        }
      });

      btnChartPng.addEventListener("click", () => {
        if (!chartCanvas) return;
        drawRuntimeChart();
        const url = chartCanvas.toDataURL("image/png");
        const link = document.createElement("a");
        link.href = url;
        link.download = "mh8-wfx-w-plane-runtime-chart.png";
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
        showToast("Runtime chart PNG downloaded.");
        safeVibrate(10);
      });

      btnChartSvg.addEventListener("click", async () => {
        const svg = buildRuntimeSvg();
        try {
          if (navigator.clipboard && navigator.clipboard.writeText) {
            await navigator.clipboard.writeText(svg);
          } else {
            const ta = document.createElement("textarea");
            ta.value = svg;
            ta.style.position = "fixed";
            ta.style.left = "-9999px";
            document.body.appendChild(ta);
            ta.focus();
            ta.select();
            document.execCommand("copy");
            document.body.removeChild(ta);
          }
          showToast("Runtime chart SVG payload copied.");
          safeVibrate(10);
        } catch (e) {
          console.error("SVG copy failed:", e);
          showToast("Copy failed. Try manual select + copy.");
        }
      });

      // LIVE URL DRIVER BUTTONS
      btnSetLiveUrl.addEventListener("click", () => {
        if (!liveUrlInput) return;
        const raw = (liveUrlInput.value || "").trim();
        if (!raw) {
          showToast("Paste a valid http(s) URL first.");
          return;
        }
        let url = raw;
        if (!/^https?:\/\//i.test(url)) {
          url = "https://" + url;
        }
        try {
          const u = new URL(url);
          state.liveUrl = u.toString();
          startLiveUrlMode();
          showToast("Live URL driver armed.");
          safeVibrate(14);
        } catch (e) {
          showToast("Invalid URL. Please check and try again.");
        }
      });

      btnClearLiveUrl.addEventListener("click", () => {
        state.liveUrl = null;
        stopLiveUrlMode();
        updateLiveUrlUi();
        appendLog(
          "🌐 Live URL driver disabled. Controller back in demo mode.",
          "info"
        );
        showToast("Live URL cleared. Demo mode active.");
        safeVibrate(8);
      });

      if (btnViewerRefresh) {
        btnViewerRefresh.addEventListener("click", () => {
          if (!state.liveUrl) {
            showToast("Set a Live URL first.");
            return;
          }
          refreshViewerFromLiveUrl(true);
          showToast("Viewer refreshed from Live URL.");
          safeVibrate(10);
        });
      }

      if (btnViewerOpen) {
        btnViewerOpen.addEventListener("click", () => {
          if (!state.liveUrl) {
            showToast("Set a Live URL first.");
            return;
          }
          try {
            window.open(state.liveUrl, "_blank", "noopener,noreferrer");
            safeVibrate(10);
          } catch (e) {
            showToast("Unable to open tab, please allow popups.");
          }
        });
      }

      if (btnViewerClear) {
        btnViewerClear.addEventListener("click", () => {
          if (liveUrlViewer) {
            liveUrlViewer.src = "about:blank";
            if (liveUrlViewer.dataset) {
              liveUrlViewer.dataset.src = "about:blank";
            }
            updateViewerSandboxForUrl(null);
          }
          if (viewerUrlDisplay) {
            viewerUrlDisplay.textContent =
              "Frame cleared. Live URL driver state is unchanged.";
          }
          safeVibrate(8);
        });
      }

      appendLog(
        "MH8-WFX W-PLANE controller POF demo ready. Configure W & L, inject tasks, then generate a POF receipt.",
        "info"
      );

      updateLiveUrlUi();
      startScheduler();
      updateHud();
    });
  </script>
</body>
</html>
