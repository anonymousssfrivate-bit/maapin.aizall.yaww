<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>🤍 Maapinn Aizal, Niaaaaa 🤍</title>
    <style>
        /* ===== RESET & GLOBAL ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Poppins', system-ui, sans-serif;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #0a0a0a;
            overflow: hidden;
            position: relative;
        }

        /* ===== BACKGROUND IMAGE (transparan) ===== */
        .bg-image {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            background-image: url('https://files.catbox.moe/y1dmb7.jpg');
            background-size: cover;
            background-position: center;
            opacity: 0.35;
            filter: blur(2px) brightness(0.7);
            transition: opacity 0.5s ease;
        }

        /* ===== ANIMATED BACKGROUND OVERLAY ===== */
        .bg-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            background: radial-gradient(ellipse at 20% 50%, rgba(40, 10, 30, 0.6) 0%, rgba(10, 10, 10, 0.7) 70%);
            overflow: hidden;
            pointer-events: none;
        }

        .bg-canvas::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle at 30% 40%, rgba(255, 105, 180, 0.06) 0%, transparent 50%),
                radial-gradient(circle at 70% 60%, rgba(255, 20, 147, 0.04) 0%, transparent 40%);
            animation: bgPulse 12s ease-in-out infinite alternate;
        }

        @keyframes bgPulse {
            0% {
                transform: scale(1) rotate(0deg);
            }
            100% {
                transform: scale(1.2) rotate(5deg);
            }
        }

        /* ===== FLOATING CODE PARTICLES ===== */
        .code-particle {
            position: fixed;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            color: rgba(255, 255, 255, 0.04);
            pointer-events: none;
            z-index: 1;
            white-space: nowrap;
            animation: floatParticle linear infinite;
        }

        @keyframes floatParticle {
            0% {
                transform: translateY(110vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) rotate(720deg);
                opacity: 0;
            }
        }

        /* ===== HEART RAIN ===== */
        .heart-rain {
            position: fixed;
            top: -20px;
            font-size: 18px;
            opacity: 0.10;
            pointer-events: none;
            z-index: 1;
            animation: rain linear infinite;
        }

        @keyframes rain {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 0.10;
            }
            100% {
                transform: translateY(110vh) rotate(720deg);
                opacity: 0;
            }
        }

        /* ===== MAIN CARD ===== */
        .card {
            position: relative;
            z-index: 2;
            width: 90%;
            max-width: 580px;
            background: rgba(10, 10, 10, 0.88);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-radius: 32px;
            padding: 40px 36px 48px;
            border: 2px solid rgba(255, 105, 180, 0.25);
            box-shadow: 0 30px 80px rgba(255, 105, 180, 0.15),
                0 0 60px rgba(255, 20, 147, 0.05),
                inset 0 1px 0 rgba(255, 255, 255, 0.05);
            text-align: center;
            transition: all 0.3s ease;
        }

        .card:hover {
            border-color: rgba(255, 105, 180, 0.45);
            box-shadow: 0 40px 100px rgba(255, 105, 180, 0.2),
                0 0 80px rgba(255, 20, 147, 0.08);
        }

        /* ===== TERMINAL HEADER ===== */
        .terminal-bar {
            display: flex;
            align-items: center;
            gap: 10px;
            padding-bottom: 20px;
            margin-bottom: 24px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.06);
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            transition: all 0.3s ease;
        }
        .dot-red {
            background: #ff5f56;
        }
        .dot-yellow {
            background: #ffbd2e;
        }
        .dot-green {
            background: #27c93f;
        }

        .terminal-title {
            font-family: 'Courier New', monospace;
            font-size: 13px;
            color: rgba(255, 255, 255, 0.35);
            margin-left: 6px;
            letter-spacing: 0.5px;
        }
        .terminal-title span {
            color: rgba(255, 105, 180, 0.6);
        }

        /* ===== AVATAR ===== */
        .avatar-wrap {
            position: relative;
            width: 90px;
            height: 90px;
            margin: 0 auto 18px;
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            background: linear-gradient(135deg, #ff6b9d, #c44dff);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 42px;
            box-shadow: 0 8px 32px rgba(255, 105, 180, 0.3);
            animation: avatarGlow 3s ease-in-out infinite alternate;
            position: relative;
            color: white;
        }

        @keyframes avatarGlow {
            0% {
                box-shadow: 0 8px 32px rgba(255, 105, 180, 0.25);
            }
            100% {
                box-shadow: 0 8px 48px rgba(255, 105, 180, 0.5), 0 0 80px rgba(255, 20, 147, 0.15);
            }
        }

        .avatar-ring {
            position: absolute;
            inset: -4px;
            border-radius: 50%;
            border: 2px solid rgba(255, 105, 180, 0.3);
            animation: ringSpin 8s linear infinite;
        }

        @keyframes ringSpin {
            0% {
                transform: rotate(0deg);
                border-color: rgba(255, 105, 180, 0.2);
            }
            50% {
                border-color: rgba(255, 255, 255, 0.5);
            }
            100% {
                transform: rotate(360deg);
                border-color: rgba(255, 105, 180, 0.2);
            }
        }

        /* ===== NAMA ===== */
        .name {
            font-size: 44px;
            font-weight: 800;
            background: linear-gradient(135deg, #ff6b9d, #ff1493, #c44dff);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientMove 4s ease-in-out infinite alternate;
            letter-spacing: 2px;
            line-height: 1.2;
            margin-bottom: 4px;
        }

        @keyframes gradientMove {
            0% {
                background-position: 0% 50%;
            }
            100% {
                background-position: 100% 50%;
            }
        }

        .name-sub {
            font-size: 15px;
            color: rgba(255, 255, 255, 0.4);
            font-weight: 400;
            letter-spacing: 3px;
            margin-top: -2px;
            margin-bottom: 16px;
        }
        .name-sub span {
            color: #ff6b9d;
            font-weight: 600;
        }

        /* ===== MESSAGE BOX ===== */
        .message-box {
            background: rgba(0, 0, 0, 0.5);
            border-radius: 16px;
            padding: 20px 24px;
            margin: 16px 0 24px;
            border-left: 3px solid #ff6b9d;
            text-align: left;
            min-height: 80px;
            position: relative;
        }

        .message-box .prompt {
            color: rgba(255, 105, 180, 0.6);
            font-family: 'Courier New', monospace;
            font-size: 13px;
            margin-bottom: 6px;
        }
        .message-box .prompt span {
            color: #27c93f;
        }

        .typewriter-text {
            font-family: 'Courier New', monospace;
            font-size: 16px;
            line-height: 1.7;
            color: rgba(255, 255, 255, 0.9);
            min-height: 60px;
            white-space: pre-wrap;
            word-break: break-word;
        }

        .typewriter-text .cursor {
            display: inline-block;
            width: 2px;
            height: 18px;
            background: #ff6b9d;
            margin-left: 2px;
            vertical-align: text-bottom;
            animation: blink 0.8s step-end infinite;
        }

        @keyframes blink {
            0%,
            100% {
                opacity: 1;
            }
            50% {
                opacity: 0;
            }
        }

        .typewriter-text .highlight {
            color: #ff6b9d;
            font-weight: 700;
        }
        .typewriter-text .highlight-name {
            background: linear-gradient(135deg, #ff6b9d, #c44dff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 800;
        }

        /* ===== COMMIT LINE ===== */
        .commit-line {
            font-family: 'Courier New', monospace;
            font-size: 13px;
            color: rgba(255, 255, 255, 0.25);
            background: rgba(255, 255, 255, 0.04);
            border-radius: 8px;
            padding: 8px 14px;
            margin: 6px 0 14px;
            display: inline-block;
            letter-spacing: 0.3px;
        }
        .commit-line .hash {
            color: #ff6b9d;
        }
        .commit-line .branch {
            color: #27c93f;
        }

        /* ===== BUTTONS ===== */
        .actions {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            justify-content: center;
            margin-top: 24px;
        }

        .btn {
            padding: 14px 36px;
            border: none;
            border-radius: 60px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
            display: inline-flex;
            align-items: center;
            gap: 10px;
            font-family: inherit;
            letter-spacing: 0.5px;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: linear-gradient(135deg, #ff6b9d, #e83a7a);
            color: #fff;
            box-shadow: 0 6px 30px rgba(255, 105, 180, 0.3);
        }
        .btn-primary:hover {
            transform: scale(1.05) translateY(-2px);
            box-shadow: 0 10px 40px rgba(255, 105, 180, 0.45);
        }
        .btn-primary:active {
            transform: scale(0.97);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.06);
            color: rgba(255, 255, 255, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.12);
            color: #fff;
            transform: scale(1.02);
        }

        .btn .heart-icon {
            display: inline-block;
            transition: transform 0.3s ease;
        }
        .btn-primary:hover .heart-icon {
            transform: scale(1.3) rotate(-5deg);
        }

        /* ===== FORGIVEN STATE ===== */
        .forgiven-state {
            display: none;
            margin-top: 20px;
            padding: 16px;
            border-radius: 16px;
            background: rgba(255, 105, 180, 0.08);
            border: 1px solid rgba(255, 105, 180, 0.25);
            animation: popIn 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
        }
        .forgiven-state.show {
            display: block;
        }

        @keyframes popIn {
            0% {
                transform: scale(0.8);
                opacity: 0;
            }
            100% {
                transform: scale(1);
                opacity: 1;
            }
        }

        .forgiven-state .big-text {
            font-size: 28px;
            font-weight: 700;
            color: #ff6b9d;
            margin-bottom: 4px;
        }
        .forgiven-state .sub-text {
            color: rgba(255, 255, 255, 0.5);
            font-size: 14px;
        }

        /* ===== FLOATING HEARTS ===== */
        .floating-heart {
            position: fixed;
            pointer-events: none;
            font-size: 24px;
            z-index: 100;
            animation: heartFloat 2s ease-out forwards;
        }
        @keyframes heartFloat {
            0% {
                transform: translate(0, 0) scale(0.5) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translate(var(--tx), var(--ty)) scale(1.5) rotate(40deg);
                opacity: 0;
            }
        }

        /* ===== CONFETTI ===== */
        .confetti-piece {
            position: fixed;
            width: 10px;
            height: 10px;
            pointer-events: none;
            z-index: 99;
            animation: confettiFall linear forwards;
        }
        @keyframes confettiFall {
            0% {
                transform: translateY(-10vh) rotate(0deg) scale(0.5);
                opacity: 1;
            }
            100% {
                transform: translateY(110vh) rotate(720deg) scale(1);
                opacity: 0;
            }
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 500px) {
            .card {
                padding: 28px 20px 36px;
                border-radius: 24px;
            }
            .name {
                font-size: 32px;
            }
            .typewriter-text {
                font-size: 14px;
            }
            .message-box {
                padding: 14px 16px;
            }
            .btn {
                padding: 12px 24px;
                font-size: 14px;
                width: 100%;
                justify-content: center;
            }
            .actions {
                flex-direction: column;
            }
            .avatar-wrap {
                width: 70px;
                height: 70px;
            }
            .avatar {
                font-size: 32px;
            }
        }

        @media (max-width: 380px) {
            .name {
                font-size: 26px;
            }
            .card {
                padding: 20px 14px 28px;
            }
            .typewriter-text {
                font-size: 12px;
            }
        }

        ::-webkit-scrollbar {
            width: 4px;
        }
        ::-webkit-scrollbar-track {
            background: transparent;
        }
        ::-webkit-scrollbar-thumb {
            background: #ff6b9d;
            border-radius: 10px;
        }
    </style>
</head>
<body>

    <!-- ===== BACKGROUND IMAGE (transparan) ===== -->
    <div class="bg-image" id="bgImage"></div>

    <!-- ===== ANIMATED BACKGROUND OVERLAY ===== -->
    <div class="bg-canvas" id="bgCanvas"></div>

    <!-- ===== MAIN CARD ===== -->
    <div class="card" id="mainCard">

        <!-- Terminal Bar -->
        <div class="terminal-bar">
            <div class="dot dot-red"></div>
            <div class="dot dot-yellow"></div>
            <div class="dot dot-green"></div>
            <span class="terminal-title">bash — <span>apology.sh</span></span>
        </div>

        <!-- Avatar -->
        <div class="avatar-wrap">
            <div class="avatar">🤍</div>
            <div class="avatar-ring"></div>
        </div>

        <!-- Nama -->
        <div class="name">Niaaaaa</div>
        <div class="name-sub">🤍 dari <span>Aizal</span> 🤍</div>

        <!-- Commit Line -->
        <div class="commit-line">
            <span class="branch">⎇ main</span> &nbsp;
            <span class="hash">commit</span> &nbsp;
            <span style="color:rgba(255,255,255,0.3)">—</span> &nbsp;
            "aizalll cintaaaa niaaaaa 🤍"
        </div>

        <!-- Message Box -->
        <div class="message-box">
            <div class="prompt">
                <span>➜</span> ~/apology &nbsp; <span style="color:#ff6b9d;">✗</span>
            </div>
            <div class="typewriter-text" id="typewriter">
                <span id="typedContent"></span>
                <span class="cursor" id="cursorEl"></span>
            </div>
        </div>

        <!-- Actions -->
        <div class="actions">
            <button class="btn btn-primary" id="forgiveBtn">
                <span class="heart-icon">🤍</span>
                Maappinn aizall yaww, Nia
            </button>
            <button class="btn btn-secondary" id="resetBtn">
                <span>↻</span> Ulangi
            </button>
        </div>

        <!-- Forgiven State -->
        <div class="forgiven-state" id="forgivenState">
            <div class="big-text">✨ Niaaaaa maapinn! ✨</div>
            <div class="sub-text">Niaaaaa 🤍 Aizal, cinta niaaaa selamanya 🤍</div>
        </div>

    </div>

    <!-- ============================================================ -->
    <!-- ===== JAVASCRIPT ===== -->
    <script>
        (function() {
            'use strict';

            // ─── CONFIG ───
            const APOLOGY_LINES = [
                'Hai <span class="highlight-name">Niaaaaa</span>...',
                'Aku <span class="highlight">Aizal</span>,',
                'aizall cumann belcanda aja kok maapinnn yawwww sayanggggggg cuuu. 🤍',
                '',
                'Aku tau aku salah.',
                'Aku tau aku bikin kamu kecewa.',
                '',
                'Dari lubuk hati yang paling dalam,',
                'aku minta maaf sebesar-besarnya.',
                '',
                'Kamu adalah <span class="highlight">#1</span> di hidupku.',
                'Tanpa kamu, kodeku error,',
                'semangatku <span class="highlight">null</span>,',
                'dan hariku <span class="highlight">undefined</span>.',
                '',
                'Please, <span class="highlight-name">Niaaaaa</span>...',
                'maafin aku ya? 🙏',
                '',
                '— <span class="highlight">Aizal</span> 🤍'
            ];

            const HEART_EMOJIS = ['🤍', '💕', '💗', '💖', '💘', '💝', '✨', '🌸', '🌺', '💫', '🤍'];
            const COLORS = ['#ff6b9d', '#ff1493', '#c44dff', '#ff9a56', '#ffd93d', '#ff4d94'];

            // ─── DOM REFS ───
            const typedContent = document.getElementById('typedContent');
            const cursorEl = document.getElementById('cursorEl');
            const forgiveBtn = document.getElementById('forgiveBtn');
            const resetBtn = document.getElementById('resetBtn');
            const forgivenState = document.getElementById('forgivenState');
            const bgCanvas = document.getElementById('bgCanvas');

            let isTyping = false;
            let isForgiven = false;
            let typeInterval = null;
            let currentLine = 0;
            let currentChar = 0;
            let isDeleting = false;

            // ─── TYPEWRITER ───
            function startTypewriter() {
                if (typeInterval) {
                    clearInterval(typeInterval);
                    typeInterval = null;
                }
                isTyping = true;
                currentLine = 0;
                currentChar = 0;
                isDeleting = false;
                typedContent.innerHTML = '';
                typeInterval = setInterval(typeStep, 45);
            }

            function typeStep() {
                if (isDeleting) {
                    const html = typedContent.innerHTML;
                    if (html.length > 0) {
                        typedContent.innerHTML = html.slice(0, -1);
                    } else {
                        isDeleting = false;
                        currentLine++;
                        if (currentLine >= APOLOGY_LINES.length) {
                            clearInterval(typeInterval);
                            typeInterval = null;
                            isTyping = false;
                            cursorEl.style.display = 'none';
                            return;
                        }
                    }
                    return;
                }

                const line = APOLOGY_LINES[currentLine];
                if (!line) {
                    clearInterval(typeInterval);
                    typeInterval = null;
                    isTyping = false;
                    cursorEl.style.display = 'none';
                    forgiveBtn.disabled = false;
                    forgiveBtn.style.opacity = '1';
                    forgiveBtn.style.cursor = 'pointer';
                    return;
                }

                if (line === '') {
                    typedContent.innerHTML += '<br>';
                    currentLine++;
                    return;
                }

                const plainText = line.replace(/<[^>]+>/g, '');
                const fullHtml = line;

                if (currentChar < plainText.length) {
                    let built = '';
                    let plainIndex = 0;
                    let inTag = false;
                    let tagBuffer = '';

                    for (let i = 0; i < fullHtml.length; i++) {
                        const ch = fullHtml[i];
                        if (ch === '<') {
                            inTag = true;
                            tagBuffer = '<';
                            continue;
                        }
                        if (inTag) {
                            tagBuffer += ch;
                            if (ch === '>') {
                                built += tagBuffer;
                                inTag = false;
                                tagBuffer = '';
                            }
                            continue;
                        }
                        if (plainIndex < currentChar + 1) {
                            built += ch;
                            plainIndex++;
                        } else {
                            break;
                        }
                    }
                    if (inTag) {
                        built += '>';
                    }

                    typedContent.innerHTML = built;
                    currentChar++;
                } else {
                    typedContent.innerHTML = fullHtml;
                    currentLine++;
                    currentChar = 0;
                    if (currentLine < APOLOGY_LINES.length) {
                        typedContent.innerHTML += '<br>';
                    } else {
                        clearInterval(typeInterval);
                        typeInterval = null;
                        isTyping = false;
                        cursorEl.style.display = 'none';
                        forgiveBtn.disabled = false;
                        forgiveBtn.style.opacity = '1';
                        forgiveBtn.style.cursor = 'pointer';
                        return;
                    }
                }
            }

            // ─── BACKGROUND PARTICLES ───
            function createCodeParticles() {
                const codeSnippets = [
                    'console.log("sorry");',
                    'git commit -m "maaf"',
                    'function forgive() { return true; }',
                    'const love = "Niaaaaa";',
                    'if (you.sad) { me.apologize(); }',
                    '🤍 → 🤍',
                    'npm install apology',
                    '--fix-broken-heart',
                    'merge request: forgive',
                    'deploy: love',
                    'Aizal 🤍 Nia'
                ];

                for (let i = 0; i < 18; i++) {
                    const el = document.createElement('div');
                    el.className = 'code-particle';
                    el.textContent = codeSnippets[Math.floor(Math.random() * codeSnippets.length)];
                    el.style.left = Math.random() * 100 + '%';
                    el.style.fontSize = (12 + Math.random() * 10) + 'px';
                    el.style.opacity = 0.03 + Math.random() * 0.04;
                    el.style.animationDuration = (20 + Math.random() * 40) + 's';
                    el.style.animationDelay = (Math.random() * 30) + 's';
                    bgCanvas.appendChild(el);
                }
            }

            function createHeartRain() {
                for (let i = 0; i < 20; i++) {
                    const el = document.createElement('div');
                    el.className = 'heart-rain';
                    el.textContent = ['🤍', '💕', '💗', '💖', '🤍'][Math.floor(Math.random() * 5)];
                    el.style.left = Math.random() * 100 + '%';
                    el.style.fontSize = (12 + Math.random() * 18) + 'px';
                    el.style.opacity = 0.04 + Math.random() * 0.08;
                    el.style.animationDuration = (15 + Math.random() * 30) + 's';
                    el.style.animationDelay = (Math.random() * 20) + 's';
                    bgCanvas.appendChild(el);
                }
            }

            // ─── FLOATING HEARTS ───
            function burstHearts(count = 40) {
                const container = document.body;
                for (let i = 0; i < count; i++) {
                    const el = document.createElement('div');
                    el.className = 'floating-heart';
                    el.textContent = HEART_EMOJIS[Math.floor(Math.random() * HEART_EMOJIS.length)];
                    const startX = 50 + (Math.random() - 0.5) * 60;
                    const startY = 50 + (Math.random() - 0.5) * 30;
                    const tx = (Math.random() - 0.5) * 600;
                    const ty = -300 - Math.random() * 500;
                    el.style.left = startX + '%';
                    el.style.top = startY + '%';
                    el.style.setProperty('--tx', tx + 'px');
                    el.style.setProperty('--ty', ty + 'px');
                    el.style.fontSize = (18 + Math.random() * 28) + 'px';
                    el.style.animationDuration = (1.5 + Math.random() * 1.5) + 's';
                    el.style.animationDelay = (Math.random() * 0.4) + 's';
                    container.appendChild(el);
                    setTimeout(() => el.remove(), 3000);
                }
            }

            // ─── CONFETTI ───
            function burstConfetti(count = 60) {
                const container = document.body;
                for (let i = 0; i < count; i++) {
                    const el = document.createElement('div');
                    el.className = 'confetti-piece';
                    const size = 6 + Math.random() * 10;
                    el.style.width = size + 'px';
                    el.style.height = size * 0.6 + 'px';
                    el.style.background = COLORS[Math.floor(Math.random() * COLORS.length)];
                    el.style.borderRadius = Math.random() > 0.5 ? '50%' : '2px';
                    el.style.left = (20 + Math.random() * 60) + '%';
                    el.style.top = (10 + Math.random() * 30) + '%';
                    el.style.transform = `rotate(${Math.random() * 360}deg)`;
                    el.style.animationDuration = (2 + Math.random() * 3) + 's';
                    el.style.animationDelay = (Math.random() * 0.8) + 's';
                    container.appendChild(el);
                    setTimeout(() => el.remove(), 5000);
                }
            }

            // ─── FORGIVE ───
            function handleForgive() {
                if (isForgiven || isTyping) return;

                isForgiven = true;
                forgivenState.classList.add('show');

                const avatar = document.querySelector('.avatar');
                avatar.textContent = '🤍';

                forgiveBtn.disabled = true;
                forgiveBtn.style.opacity = '0.5';
                forgiveBtn.style.cursor = 'default';

                burstHearts(50);
                burstConfetti(70);

                typedContent.innerHTML =
                    'Yeay! <span class="highlight-name">Niaaaaa</span> mau maafin <span class="highlight">Aizal</span>! 😭🤍<br>' +
                    'Cinta niaaa selamanya <span class="highlight">🤍</span>';

                cursorEl.style.display = 'none';

                setTimeout(() => burstHearts(30), 800);
                setTimeout(() => burstConfetti(40), 1200);
                setTimeout(() => burstHearts(25), 2000);

                forgiveBtn.innerHTML = '✅ Sudah niaaaaa maapinnn 🤍';
            }

            // ─── RESET ───
            function handleReset() {
                if (isTyping) return;

                isForgiven = false;
                forgivenState.classList.remove('show');

                document.querySelector('.avatar').textContent = '🤍';

                forgiveBtn.disabled = false;
                forgiveBtn.style.opacity = '1';
                forgiveBtn.style.cursor = 'pointer';
                forgiveBtn.innerHTML = '<span class="heart-icon">🤍</span> Maafin aizall yaww, Nia';

                cursorEl.style.display = 'inline-block';
                startTypewriter();
            }

            // ─── INIT ───
            function init() {
                createCodeParticles();
                createHeartRain();

                setTimeout(startTypewriter, 600);

                forgiveBtn.addEventListener('click', handleForgive);
                resetBtn.addEventListener('click', handleReset);

                document.addEventListener('keydown', (e) => {
                    if (e.key === 'Enter' && !isForgiven && !isTyping) {
                        handleForgive();
                    }
                    if (e.key === 'r' && isForgiven) {
                        handleReset();
                    }
                });

                forgiveBtn.disabled = true;
                forgiveBtn.style.opacity = '0.5';
                forgiveBtn.style.cursor = 'default';
            }

            if (document.readyState === 'loading') {
                document.addEventListener('DOMContentLoaded', init);
            } else {
                init();
            }

        })();
    </script>

</body>
</html>
