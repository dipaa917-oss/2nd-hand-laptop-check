<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Second-Hand Laptop Inspection Checklist</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-color: #0b0f19;
            --card-bg: rgba(17, 24, 39, 0.65);
            --card-border: rgba(255, 255, 255, 0.08);
            --accent-color: #10b981;
            --accent-hover: #059669;
            --text-main: #f3f4f6;
            --text-muted: #9ca3af;
            --glass-glow: rgba(16, 185, 129, 0.15);
            --code-bg: rgba(0, 0, 0, 0.4);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            overflow-x: hidden;
            background-image: 
                radial-gradient(at 0% 0%, rgba(16, 185, 129, 0.05) 0px, transparent 50%),
                radial-gradient(at 100% 100%, rgba(16, 185, 129, 0.03) 0px, transparent 50%);
            background-attachment: fixed;
            padding-bottom: 6rem;
        }

        /* Glassmorphism Styles */
        .glass {
            background: var(--card-bg);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border: 1px solid var(--card-border);
            border-radius: 12px;
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.4);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .glass:hover {
            border-color: rgba(16, 185, 129, 0.25);
            box-shadow: 0 12px 40px 0 var(--glass-glow);
        }

        /* Hero Section */
        header {
            min-height: 65vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 3rem 1.5rem;
            position: relative;
        }

        header h1 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 1.25rem;
            letter-spacing: -0.04em;
            background: linear-gradient(to right, #ffffff 40%, var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        header p {
            font-size: 1.25rem;
            color: var(--text-muted);
            max-width: 650px;
            margin-bottom: 2.5rem;
            line-height: 1.6;
        }

        .btn-primary {
            background-color: var(--accent-color);
            color: #060911;
            font-weight: 600;
            padding: 0.9rem 2.25rem;
            border-radius: 8px;
            text-decoration: none;
            border: none;
            cursor: pointer;
            font-size: 1.05rem;
            display: inline-flex;
            align-items: center;
            gap: 0.6rem;
            transition: all 0.2s ease;
            box-shadow: 0 4px 14px rgba(16, 185, 129, 0.3);
        }

        .btn-primary:hover {
            background-color: var(--accent-hover);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(16, 185, 129, 0.4);
        }

        /* Sticky Navigation */
        nav {
            position: sticky;
            top: 0;
            z-index: 100;
            background: rgba(11, 15, 25, 0.8);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid var(--card-border);
            padding: 1rem 2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 1.5rem;
        }

        .nav-brand {
            font-weight: 700;
            font-size: 1.15rem;
            color: var(--accent-color);
            display: flex;
            align-items: center;
            gap: 0.6rem;
            letter-spacing: 0.05em;
        }

        .search-container {
            position: relative;
            width: 350px;
        }

        .search-container input {
            width: 100%;
            padding: 0.6rem 1rem 0.6rem 2.6rem;
            border-radius: 30px;
            border: 1px solid var(--card-border);
            background: rgba(255, 255, 255, 0.04);
            color: var(--text-main);
            font-size: 0.9rem;
            outline: none;
            transition: all 0.2s ease;
        }

        .search-container input:focus {
            border-color: var(--accent-color);
            background: rgba(255, 255, 255, 0.08);
            box-shadow: 0 0 0 3px rgba(16, 185, 129, 0.15);
        }

        .search-container i {
            position: absolute;
            left: 1rem;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
        }

        .nav-actions {
            display: flex;
            gap: 0.75rem;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.04);
            border: 1px solid var(--card-border);
            color: var(--text-main);
            padding: 0.55rem 1.1rem;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.9rem;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.2s ease;
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.09);
            border-color: var(--accent-color);
        }

        /* Main Context Structure */
        main {
            max-width: 1100px;
            margin: 3rem auto;
            padding: 0 1.5rem;
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .section-card {
            padding: 2.25rem;
        }

        .section-card h2 {
            font-size: 1.35rem;
            margin-bottom: 1.5rem;
            display: flex;
            align-items: center;
            gap: 0.75rem;
            color: #ffffff;
            border-left: 4px solid var(--accent-color);
            padding-left: 0.85rem;
        }

        /* Form Specs Matrix Fields */
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.25rem;
            margin-bottom: 1.5rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.4rem;
        }

        .form-group label {
            font-size: 0.8rem;
            color: var(--text-muted);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.02em;
        }

        .form-group input {
            background: rgba(0, 0, 0, 0.2);
            border: 1px solid var(--card-border);
            padding: 0.65rem 0.85rem;
            border-radius: 6px;
            color: #fff;
            font-size: 0.95rem;
            outline: none;
            transition: border-color 0.2s;
        }

        .form-group input:focus {
            border-color: var(--accent-color);
        }

        /* Commands Blocks styles */
        .command-wrap {
            margin-bottom: 1rem;
        }
        
        .command-title {
            font-size: 0.8rem;
            color: var(--text-muted);
            margin-bottom: 0.35rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.4rem;
        }

        .command-box {
            background: var(--code-bg);
            border: 1px solid var(--card-border);
            border-radius: 8px;
            padding: 0.75rem 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-family: 'Consolas', 'Courier New', Courier, monospace;
        }

        .command-text {
            color: #34d399;
            font-size: 0.95rem;
            white-space: nowrap;
            overflow-x: auto;
            padding-right: 1rem;
        }

        .btn-copy {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid var(--card-border);
            color: var(--text-muted);
            cursor: pointer;
            padding: 0.35rem 0.7rem;
            border-radius: 5px;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.35rem;
            transition: all 0.2s;
            flex-shrink: 0;
        }

        .btn-copy:hover {
            color: var(--accent-color);
            background: rgba(16, 185, 129, 0.08);
            border-color: rgba(16, 185, 129, 0.3);
        }

        /* Checklists Structural Maps */
        .checklist {
            list-style: none;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 0.85rem;
            margin-top: 1.25rem;
        }

        .checklist-item {
            display: flex;
            align-items: flex-start;
            gap: 0.8rem;
            background: rgba(255, 255, 255, 0.015);
            padding: 0.85rem;
            border-radius: 8px;
            border: 1px solid transparent;
            cursor: pointer;
            user-select: none;
            transition: all 0.2s ease;
        }

        .checklist-item:hover {
            background: rgba(255, 255, 255, 0.03);
            border-color: rgba(255, 255, 255, 0.05);
        }

        .checklist-item input[type="checkbox"] {
            appearance: none;
            -webkit-appearance: none;
            width: 19px;
            height: 19px;
            border: 2px solid var(--text-muted);
            border-radius: 5px;
            outline: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 1px;
            flex-shrink: 0;
            transition: all 0.2s;
        }

        .checklist-item input[type="checkbox"]:checked {
            background-color: var(--accent-color);
            border-color: var(--accent-color);
        }

        .checklist-item input[type="checkbox"]:checked::after {
            content: "\f00c";
            font-family: "Font Awesome 6 Free";
            font-weight: 900;
            color: #0b0f19;
            font-size: 11px;
        }

        .checklist-item.checked-style {
            color: var(--text-muted);
            opacity: 0.7;
            background: rgba(16, 185, 129, 0.02);
            border-color: rgba(16, 185, 129, 0.05);
        }

        /* Recommendation blocks context link boxes */
        .recommendation-box {
            background: rgba(16, 185, 129, 0.04);
            border: 1px solid rgba(16, 185, 129, 0.15);
            border-radius: 8px;
            padding: 1.1rem 1.25rem;
            margin-bottom: 1.25rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .recommendation-details h4 {
            font-size: 0.95rem;
            color: #fff;
            margin-bottom: 0.2rem;
        }

        .recommendation-details p {
            font-size: 0.85rem;
            color: var(--text-muted);
        }

        .btn-small {
            padding: 0.5rem 1rem;
            font-size: 0.85rem;
            border-radius: 6px;
        }

        /* Screen Color Panels triggers maps */
        .interactive-row {
            display: flex;
            flex-wrap: wrap;
            gap: 0.75rem;
            margin: 1rem 0;
        }

        .screen-trigger {
            padding: 0.55rem 1.1rem;
            border-radius: 6px;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.85rem;
            border: 1px solid var(--card-border);
            transition: transform 0.2s;
        }

        .screen-trigger:hover {
            transform: translateY(-1px);
        }

        /* Fullscreen Screen Tester canvas utility rules */
        #screen-tester {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 99999;
            cursor: pointer;
        }

        #screen-tester .close-tip {
            position: absolute;
            top: 1.5rem;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(0,0,0,0.75);
            color: #fff;
            padding: 0.5rem 1.25rem;
            border-radius: 30px;
            font-size: 0.85rem;
            letter-spacing: 0.02em;
            pointer-events: none;
            border: 1px solid rgba(255,255,255,0.1);
        }

        /* Large Verification Index Score / Gauge Graphics mapping */
        .verdict-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            gap: 1.5rem;
            padding: 1rem 0;
        }

        .meter-container {
            position: relative;
            width: 180px;
            height: 180px;
            background: radial-gradient(rgba(0,0,0,0.3) 60%, transparent 61%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: inset 0 0 20px rgba(0,0,0,0.6), 0 0 0 4px rgba(255,255,255,0.03);
        }

        .score-inner {
            text-align: center;
        }

        .score-num {
            font-size: 3.25rem;
            font-weight: 800;
            color: var(--accent-color);
            line-height: 1;
        }

        .score-label {
            font-size: 0.75rem;
            color: var(--text-muted);
            margin-top: 0.35rem;
            text-transform: uppercase;
            letter-spacing: 0.08em;
            font-weight: 700;
        }

        .verdict-badge {
            font-size: 1.2rem;
            font-weight: 700;
            padding: 0.6rem 2.25rem;
            border-radius: 40px;
            letter-spacing: 0.02em;
            text-transform: uppercase;
        }

        .verdict-badge.avoid { color: #ef4444; border: 1px solid #ef4444; background: rgba(239, 68, 68, 0.08); }
        .verdict-badge.average { color: #f59e0b; border: 1px solid #f59e0b; background: rgba(245, 158, 11, 0.08); }
        .verdict-badge.good { color: #3b82f6; border: 1px solid #3b82f6; background: rgba(59, 130, 246, 0.08); }
        .verdict-badge.excellent { color: #10b981; border: 1px solid #10b981; background: rgba(16, 185, 129, 0.08); }

        /* FAQs Content Grids layout configurations */
        .faq-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem;
        }

        .faq-item h3 {
            font-size: 1.05rem;
            margin-bottom: 0.5rem;
            color: #ffffff;
        }

        .faq-item p {
            font-size: 0.9rem;
            color: var(--text-muted);
            line-height: 1.6;
        }

        /* Sticky Bottom Progress Widget panel structure maps */
        .dashboard-sticky {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            z-index: 1000;
            width: 320px;
            padding: 1.25rem;
            box-shadow: 0 12px 40px rgba(0,0,0,0.5);
        }

        .progress-header {
            display: flex;
            justify-content: space-between;
            font-size: 0.8rem;
            margin-bottom: 0.6rem;
            font-weight: 700;
            letter-spacing: 0.04em;
        }

        .progress-bar-bg {
            background: rgba(255, 255, 255, 0.08);
            height: 8px;
            border-radius: 10px;
            overflow: hidden;
        }

        .progress-bar-fill {
            background: linear-gradient(to right, #10b981, #34d399);
            height: 100%;
            width: 0%;
            transition: width 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 0 8px rgba(16, 185, 129, 0.5);
        }

        footer {
            text-align: center;
            padding: 4rem 1rem;
            color: var(--text-muted);
            font-size: 0.85rem;
            border-top: 1px solid var(--card-border);
            margin-top: 4rem;
        }

        /* Responsive Mobile Layout Adaptations */
        @media (max-width: 850px) {
            header h1 { font-size: 2.5rem; }
            nav { flex-direction: column; padding: 1.25rem 1rem; gap: 1rem; }
            .search-container { width: 100%; }
            .nav-actions { width: 100%; justify-content: space-between; }
            .nav-actions button { flex: 1; justify-content: center; }
            .faq-grid { grid-template-columns: 1fr; }
            .dashboard-sticky { bottom: 0; right: 0; left: 0; width: 100%; border-radius: 12px 12px 0 0; border-bottom: none; }
            body { padding-bottom: 8rem; }
        }

        /* Clean High-Contrast Vector System Layout rules for Print context */
        @media print {
            body { background: #ffffff !important; color: #000000 !important; padding: 0; }
            .glass, .command-box, .checklist-item { border: 1px solid #aaa !important; background: #ffffff !important; color: #000000 !important; box-shadow: none !important; backdrop-filter: none !important; }
            nav, header, .dashboard-sticky, .btn-copy, .btn-primary, .recommendation-box, .screen-trigger, .btn-secondary { display: none !important; }
            main { max-width: 100%; margin: 0; padding: 0; }
            .section-card { page-break-inside: avoid; border: none !important; padding: 1.5rem 0; }
            .command-text { color: #111827 !important; }
            .form-group input { border: none !important; border-bottom: 1px dashed #000 !important; background: transparent !important; color: #000 !important; }
            .checklist { grid-template-columns: 1fr 1fr; }
            h2 { color: #000000 !important; border-left-color: #000000 !important; }
        }
    </style>
</head>
<body>

    <header id="hero-layout">
        <h1 class="animate-title">Second-Hand Laptop Buying Checklist</h1>
        <p>Never get scammed again. Audit internal hardware modules, pull deployment log parameters, and verify structural conditions using deep technician diagnostic workflows.</p>
        <button class="btn-primary" onclick="scrollToNav()"><i class="fas fa-list-check"></i> Start Inspection</button>
    </header>

    <nav id="sticky-control-nav">
        <div class="nav-brand">
            <i class="fas fa-laptop-medical"></i> INSPECTION RUNTIME
        </div>
        <div class="search-container">
            <i class="fas fa-search"></i>
            <input type="text" id="component-search-bar" placeholder="Filter diagnostics or commands..." onkeyup="filterChecks()">
        </div>
        <div class="nav-actions">
            <button class="btn-secondary" onclick="window.print()"><i class="fas fa-file-pdf"></i> Export / Print PDF</button>
            <button class="btn-secondary" onclick="resetAllElements()"><i class="fas fa-arrows-rotate"></i> Reset</button>
        </div>
    </nav>

    <main id="inspection-matrix-root">
        
        <section class="section-card glass search-item" data-search-keys="laptop information brand model serial number cpu ram storage gpu battery health bios date manufacture year msinfo32 systeminfo wmic csproduct wmic bios">
            <h2><i class="fas fa-id-card"></i> 2. Laptop Metadata Information</h2>
            <div class="info-grid">
                <div class="form-group"><label>Brand</label><input type="text" id="meta-brand" placeholder="e.g. HP, Dell"></div>
                <div class="form-group"><label>Model</label><input type="text" id="meta-model" placeholder="e.g. EliteBook 835 G7"></div>
                <div class="form-group"><label>Serial Number</label><input type="text" id="meta-serial" placeholder="Verify matching sticker"></div>
                <div class="form-group"><label>CPU Core</label><input type="text" id="meta-cpu" placeholder="e.g. Ryzen 5 PRO 4650U"></div>
                <div class="form-group"><label>RAM Spec</label><input type="text" id="meta-ram" placeholder="e.g. 16GB DDR4"></div>
                <div class="form-group"><label>Storage Volume</label><input type="text" id="meta-storage" placeholder="e.g. 256GB NVMe SSD"></div>
                <div class="form-group"><label>GPU Graphic Architecture</label><input type="text" id="meta-gpu" placeholder="e.g. Radeon Graphics"></div>
                <div class="form-group"><label>Battery Health (%)</label><input type="text" id="meta-battery" placeholder="e.g. 85%"></div>
                <div class="form-group"><label>BIOS Date stamp</label><input type="text" id="meta-bios" placeholder="MM/DD/YYYY"></div>
                <div class="form-group"><label>Manufacture Year</label><input type="text" id="meta-year" placeholder="YYYY"></div>
            </div>

            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-window-restore"></i> System Information Panel GUI</div>
                <div class="command-box">
                    <span class="command-text">msinfo32</span>
                    <button class="btn-copy" onclick="copyBuffer('msinfo32', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Command Prompt Comprehensive Dump</div>
                <div class="command-box">
                    <span class="command-text">systeminfo</span>
                    <button class="btn-copy" onclick="copyBuffer('systeminfo', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Extract Exact Chassis Product Model</div>
                <div class="command-box">
                    <span class="command-text">wmic csproduct get name</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic csproduct get name', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Extract Internal Hardware Serial Number (Match to bottom shell)</div>
                <div class="command-box">
                    <span class="command-text">wmic bios get serialnumber</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic bios get serialnumber', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Extract SMBIOS Version</div>
                <div class="command-box">
                    <span class="command-text">wmic bios get smbiosbiosversion</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic bios get smbiosbiosversion', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Extract System Bios Manufacturer</div>
                <div class="command-box">
                    <span class="command-text">wmic bios get manufacturer</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic bios get manufacturer', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="processor check cpu architecture wmic cpu get name generation speed clock">
            <h2><i class="fas fa-microchip"></i> 3. Processor Architecture Check</h2>
            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Get Processor CPU String</div>
                <div class="command-box">
                    <span class="command-text">wmic cpu get name</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic cpu get name', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; CPU matches seller structural description completely</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Architecture generation matches expected release specs</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Core Base Clock Speed aligns with original specifications</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="ram check memory configuration modules speed capacity capacity,speed memorychip systeminfo">
            <h2><i class="fas fa-memory"></i> 4. Operating RAM Memory Check</h2>
            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Extract RAM Module Volume Capacities & Frequency Speeds</div>
                <div class="command-box">
                    <span class="command-text">wmic MEMORYCHIP get capacity,speed</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic MEMORYCHIP get capacity,speed', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Total operating RAM capacity fully registers (e.g. 16GB verified)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Channel speeds run at proper supported operational configuration</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="storage check diskdrive ssd hdd powershell get-physicaldisk model size">
            <h2><i class="fas fa-database"></i> 5. Physical Storage Volume Check</h2>
            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Extract Drive Storage Interface Array Details</div>
                <div class="command-box">
                    <span class="command-text">wmic diskdrive get model,size,status</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic diskdrive get model,size,status', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Advanced Hardware Media Diagnostics (PowerShell command)</div>
                <div class="command-box">
                    <span class="command-text">Get-PhysicalDisk</span>
                    <button class="btn-copy" onclick="copyBuffer('Get-PhysicalDisk', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Drive protocol verified (Solid State Drive (SSD) is preferred over spinning HDD)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Drive space match advertising profiles accurately</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="ssd health smart diagnostics crystaldiskinfo sectors remaining life wear level hours temperature">
            <h2><i class="fas fa-heartbeat"></i> 6. Solid-State Drive (SSD) Telemetry Health</h2>
            <div class="recommendation-box">
                <div class="recommendation-details">
                    <h4>Recommended SMART Telemetry Reader: CrystalDiskInfo</h4>
                    <p>Technician industry standard tool for reviewing solid-state silicon chip wear index indicators.</p>
                </div>
                <a href="https://crystalmark.info/en/software/crystaldiskinfo/" target="_blank" class="btn-primary btn-small"><i class="fas fa-download"></i> Get CrystalDiskInfo</a>
            </div>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Global SMART Health status reads "Good" (Preferably 90%+ Remaining life)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Total Power On Hours evaluated to gauge lifetime read/write duty</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Critical Bad sectors/reallocated sectors allocation counter is zero</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Operating temperature markers sit inside target safe cooling levels</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Remaining life metrics match expected safe wear profiles</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="battery health report cell wear capacity cycle count powercfg /batteryreport">
            <h2><i class="fas fa-battery-three-quarters"></i> 7. Battery Infrastructure Evaluation</h2>
            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Generate Local OS Battery Performance Log (Run Command Prompt as Admin)</div>
                <div class="command-box">
                    <span class="command-text">powercfg /batteryreport</span>
                    <button class="btn-copy" onclick="copyBuffer('powercfg /batteryreport', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
            <p style="font-size: 0.85rem; color: var(--text-muted); margin: -0.25rem 0 1.25rem 0;">
                <i class="fas fa-file-code"></i> Report Output Destination: Navigate directly to <code>C:\Users\[CURRENT_USERNAME]\battery-report.html</code> to check configuration parameters.
            </p>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Full Charge Capacity retains at least 80% of original Design Capacity</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Total cycle counts checked (Preferably below 300–500 cycles)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Wear metrics inspected to rule out cell degradation or physical swelling</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="display test colors monitor lcd sub-pixel dead pixel pressure marks backlight bleed white black red green blue">
            <h2><i class="fas fa-desktop"></i> 8. Display Sub-Pixel Panel Diagnostics</h2>
            <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 1rem;">Click structural target color maps to projection test the screen panel for subpixel anomalies. Press Escape or click target space to close full canvas layer view mode.</p>
            <div class="interactive-row">
                <button class="screen-trigger" style="background:#ffffff; color:#000000; font-weight:700;" onclick="triggerScreenTest('#ffffff')">White Screen</button>
                <button class="screen-trigger" style="background:#000000; color:#ffffff; border-color:rgba(255,255,255,0.2);" onclick="triggerScreenTest('#000000')">Black Screen</button>
                <button class="screen-trigger" style="background:#ef4444; color:#ffffff; border:none;" onclick="triggerScreenTest('#ef4444')">Red Matrix</button>
                <button class="screen-trigger" style="background:#22c55e; color:#ffffff; border:none;" onclick="triggerScreenTest('#22c55e')">Green Matrix</button>
                <button class="screen-trigger" style="background:#3b82f6; color:#ffffff; border:none;" onclick="triggerScreenTest('#3b82f6')">Blue Matrix</button>
            </div>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Clean Dead Pixel validation passed (No permanently stuck or missing sub-pixels)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Display layers are clear of tracking shadow pressure marks or internal bright spots</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; LCD backlight bleed is kept to minimal operational parameters under dark mapping</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="keyboard test keys input matrix key-test backlight">
            <h2><i class="fas fa-keyboard"></i> 9. Input Keyboard Matrix Verification</h2>
            <div class="recommendation-box">
                <div class="recommendation-details">
                    <h4>Online Matrix Input Diagnostic Canvas</h4>
                    <p>Launches external specialized key map trace systems to test keyboard tracking states.</p>
                </div>
                <a href="https://en.key-test.ru/" target="_blank" class="btn-primary btn-small"><i class="fas fa-arrow-up-right-from-square"></i> Launch Keyboard Tester Website</a>
            </div>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Every key functions properly (including all operational modifiers, Control, Shift, and top Function commands)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Internal keys backlight illumination elements operate evenly without blackout areas</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="touchpad clicks tracking gestures scrolling multi-touch left right click">
            <h2><i class="fas fa-arrow-pointer"></i> 10. Touchpad Tracking & Gesture Unit</h2>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Physical Left Click hardware trigger provides crisp feedback and registers properly</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Physical Right Click hardware triggers respond normally across surface boundaries</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; OS Multi-touch finger gesture processing tracks multiple inputs smoothly</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Navigation vertical / horizontal scrolling motions are uniform and responsive</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="speaker test sound audio headphones jack frequency crackle split channel">
            <h2><i class="fas fa-volume-high"></i> 11. Speaker & Integrated Audio Drivers</h2>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Left Audio Channel produces clean sound up to full volume without mechanical vibration crackle</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Right Audio Channel produces clean sound up to full volume without tone distortions</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; External Headphone Audio Jack grounds cleanly and transfers proper split signal outputs</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="camera microphone webcam capture voice recorder lenses array">
            <h2><i class="fas fa-video"></i> 12. Digital Camera & Audio Microphone Array</h2>
            <div class="recommendation-box">
                <div class="recommendation-details">
                    <h4>Initialize Built-In Capture Pipeline</h4>
                    <p>Trigger integrated native system apps directly via the Windows platform interface environment.</p>
                </div>
                <button class="btn-primary btn-small" onclick="alert('Open your Windows Start Menu and launch the built-in system application tools: Type \'Camera\' and \'Voice Recorder\' to test audio/video capture quality directly.')"><i class="fas fa-circle-info"></i> View App Launch Guide</button>
            </div>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Video capture clarity is high, and glass lenses elements are free of dust inclusions</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Integrated Audio Microphone registers and captures sample loops cleanly without line background noise</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="wifi bluetooth wireless networking card infrastructure connection adapter">
            <h2><i class="fas fa-wifi"></i> 13. Wireless WiFi & Bluetooth Radios</h2>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Wireless card discovers local network pools and registers connection handshakes cleanly</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Bluetooth module initializes connection states with external test peripherals successfully</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="ports connectivity usb a type-c hdmi ethernet audio sd charging port pins">
            <h2><i class="fas fa-circle-nodes"></i> 14. Integrated Physical Connectivity Ports</h2>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; USB Type-A data ports register hot-swappable external tracking hardware immediately</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; USB Type-C high speed controllers conduct power profiles and protocol transfers smoothly</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; HDMI port routes pure display outputs outward to standard testing screens smoothly</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; RJ-45 Ethernet physical ports route wire network structures stably</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Analog Audio Aux Port seats inputs tightly without interface crackles</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; SD / MicroSD card logic reader channels mount external storage maps predictably</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Main Power Input pin safely conducts electrical currents without losing connection when wiggled</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="gpu check graphics dxdiag video path win32_videocontroller video controller core">
            <h2><i class="fas fa-clone"></i> 15. Graphics Processor (GPU) Core Mapping</h2>
            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-terminal"></i> Query GPU Engine Model String</div>
                <div class="command-box">
                    <span class="command-text">wmic path win32_VideoController get name</span>
                    <button class="btn-copy" onclick="copyBuffer('wmic path win32_VideoController get name', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
            <div class="command-wrap">
                <div class="command-title"><i class="fas fa-window-restore"></i> Alternative DirectX Evaluation Dashboard Panel GUI</div>
                <div class="command-box">
                    <span class="command-text">dxdiag</span>
                    <button class="btn-copy" onclick="copyBuffer('dxdiag', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="windows activation version directx disk health system file check license diagnostics slmgr /xpr winver dxdiag chkdsk sfc /scannow slmgr /dli integration">
            <h2><i class="fas fa-shield-halved"></i> 16-21. OS Licensing & File System Integration Suite</h2>
            
            <div class="command-wrap">
                <div class="command-title">16. Windows Software License Expiry Parameters Check</div>
                <div class="command-box">
                    <span class="command-text">slmgr /xpr</span>
                    <button class="btn-copy" onclick="copyBuffer('slmgr /xpr', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title">17. Identify Exact OS Kernel Build Parameters</div>
                <div class="command-box">
                    <span class="command-text">winver</span>
                    <button class="btn-copy" onclick="copyBuffer('winver', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title">18. DirectX Interface Driver Suite Matrix</div>
                <div class="command-box">
                    <span class="command-text">dxdiag</span>
                    <button class="btn-copy" onclick="copyBuffer('dxdiag', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title">19. Check Disk Logical Integrity Run Tool</div>
                <div class="command-box">
                    <span class="command-text">chkdsk</span>
                    <button class="btn-copy" onclick="copyBuffer('chkdsk', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title">20. System File Checker Integrity Integrity Check (Run Command Prompt as Admin)</div>
                <div class="command-box">
                    <span class="command-text">sfc /scannow</span>
                    <button class="btn-copy" onclick="copyBuffer('sfc /scannow', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>

            <div class="command-wrap">
                <div class="command-title">21. Comprehensive Licensing Channel Diagnostics (Retail vs OEM identification)</div>
                <div class="command-box">
                    <span class="command-text">slmgr /dli</span>
                    <button class="btn-copy" onclick="copyBuffer('slmgr /dli', this)"><i class="far fa-copy"></i> Copy</button>
                </div>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="stress test stability load testing cinebench occt furmark crystaldiskmark memtest86 benchmark runtime thermal tracking blue screen crashing">
            <h2><i class="fas fa-bolt"></i> 22. High-Load Component Stability Benchmarking</h2>
            <p style="font-size: 0.85rem; color: var(--text-muted); margin-bottom: 1.25rem;">Execute these technical utility stress suites sequentially to run high thermal workloads and screen for background operational crashes, overheating issues, or Blue Screen of Death (BSOD) system traps.</p>
            <div class="info-grid" style="grid-template-columns: repeat(auto-fill, minmax(170px, 1fr));">
                <div class="command-box" style="margin:0;"><span class="command-text" style="color:#f3f4f6;">Cinebench (CPU)</span></div>
                <div class="command-box" style="margin:0;"><span class="command-text" style="color:#f3f4f6;">OCCT (System)</span></div>
                <div class="command-box" style="margin:0;"><span class="command-text" style="color:#f3f4f6;">FurMark (GPU)</span></div>
                <div class="command-box" style="margin:0;"><span class="command-text" style="color:#f3f4f6;">CrystalDiskMark</span></div>
                <div class="command-box" style="margin:0;"><span class="command-text" style="color:#f3f4f6;">MemTest86 (RAM)</span></div>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="physical inspection chassis hinges screen body keyboard touchpad webcam charger rubber feet screws fan noise overheating smell liquid damage cracks missing parts structure damage seal">
            <h2><i class="fas fa-magnifying-glass"></i> 23. Comprehensive Structural Physical Checklist</h2>
            <div class="checklist">
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Hinges (Rigid screen retention, smooth quiet structural adjustment travel)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Screen Finish (Free of layer scratches, anti-glare damage, or coating wear)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; External Chassis Body (No sharp corner structural drops or buckling damage)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Keyboard Plate (Lays completely flat, no warped tracking surface elements)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Touchpad Tracking Alignment (Flush orientation tracking, no loose internal gaps)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Webcam Protection Elements (Integrated security slides or lens glass scratch-free)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Power Charger Block (Original manufacturer structural accessory or safety compliant setup)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Base Structural Rubber Feet (All feet elements present to allow proper fan cooling air spaces)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Bottom Case Assembly Screws (No stripped thread holes or evidence of clumsy custom modifications)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Thermal Cooling Fan Profile (Quiet high speed air channels, no bearing rattling or grinding)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Operating Thermal Profiles (The chassis stays free from excessive heating during basic operations)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Olfactory Electronic Verification (No burnt silicon smells or sweet hazardous capacitor vapor smells)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Liquid Damage Audit (Inspect connectivity ports for copper corrosion patterns or residues)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Structural Shell Fractures / Cracks (Examine plastic seams, exhaust vent blades, and port walls)</label>
                <label class="checklist-item"><input type="checkbox" onchange="runMatrixMath()">&nbsp; Complete Internal Assembly Parts (No missing dummy expansion drive blanks or structural component caps)</label>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="final verdict dynamic index analysis calculations summary evaluation metric status ranking score">
            <h2><i class="fas fa-square-poll-horizontal"></i> 24. Runtime Inspection Security Evaluation Index</h2>
            <div class="verdict-container">
                <div class="meter-container">
                    <div class="score-inner">
                        <div class="score-num" id="dynamic-score-display">0%</div>
                        <div class="score-label">Integrity Index</div>
                    </div>
                </div>
                <div>
                    <div class="verdict-badge avoid" id="dynamic-badge-render">AVOID (&lt;60% System checks completed)</div>
                </div>
                <p style="font-size: 0.9rem; color: var(--text-muted); max-width: 550px;">
                    This dynamic diagnostic threshold calculation cross-references every manual metric parameter completed above. Ensure all fundamental system items pass validation checks before purchasing the laptop asset.
                </p>
            </div>
        </section>

        <section class="section-card glass search-item" data-search-keys="faqs frequently asked questions information details office work hdd ssd mistakes business testing repairs costs">
            <h2><i class="fas fa-circle-question"></i> System FAQs & Procurement Guidelines</h2>
            <div class="faq-grid">
                <div class="faq-item">
                    <h3>1. Is it safe to buy a used laptop for office work?</h3>
                    <p>Yes, but only after proper testing. An improperly checked laptop may cause performance and security problems later.</p>
                </div>
                <div class="faq-item">
                    <h3>2. Should I buy HDD or SSD laptops?</h3>
                    <p>SSD laptops are usually better because they provide faster speed and smoother performance.</p>
                </div>
                <div class="faq-item">
                    <h3>3. What is the biggest mistake people make while buying used laptops?</h3>
                    <p>Many buyers ignore battery condition and internal performance testing. This often leads to expensive repairs later.</p>
                </div>
                <div class="faq-item">
                    <h3>4. Can businesses use second-hand laptops safely?</h3>
                    <p>Yes. Many businesses use tested second-hand laptops to manage technology costs more efficiently.</p>
                </div>
            </div>
        </section>

    </main>

    <div class="dashboard-sticky glass">
        <div class="progress-header">
            <span>DIAGNOSTIC METRIC COVERAGE</span>
            <span id="sticky-percentage-read">0%</span>
        </div>
        <div class="progress-bar-bg">
            <div class="progress-bar-fill" id="sticky-progress-fluid"></div>
        </div>
    </div>

    <div id="screen-tester" onclick="closeScreenTest()">
        <div class="close-tip">Click space or press Esc to restore normal application view mode</div>
    </div>

    <footer>
        <p>&copy; 2026 Laptop Inspect Engineering Framework. Local machine environment runtime validation engine.</p>
    </footer>

    <script>
        // System Copy Interface Buffer Operations Mapping
        function copyBuffer(textPayload, buttonElement) {
            navigator.clipboard.writeText(textPayload).then(() => {
                const legacyHTML = buttonElement.innerHTML;
                buttonElement.innerHTML = '<i class="fas fa-circle-check"></i> Copied!';
                buttonElement.style.color = '#10b981';
                setTimeout(() => {
                    buttonElement.innerHTML = legacyHTML;
                    buttonElement.style.color = '';
                }, 2000);
            }).catch(error => {
                console.error('System failed clipboard channel export write actions: ', error);
            });
        }

        // Smooth Viewport Scrolling Navigation adjustments
        function scrollToNav() {
            document.getElementById('sticky-control-nav').scrollIntoView({ behavior: 'smooth' });
        }

        // Checklist Performance Multi-Calculation Optimization Core engine
        function runMatrixMath() {
            const checklistCheckboxes = document.querySelectorAll('.checklist-item input[type="checkbox"]');
            let checksCompletedCounter = 0;

            checklistCheckboxes.forEach(box => {
                const trackingLabelContainer = box.closest('.checklist-item');
                if (box.checked) {
                    checksCompletedCounter++;
                    if (trackingLabelContainer) trackingLabelContainer.classList.add('checked-style');
                } else {
                    if (trackingLabelContainer) trackingLabelContainer.classList.remove('checked-style');
                }
            });

            const overallAuditPercentage = checklistCheckboxes.length > 0 
                ? Math.round((checksCompletedCounter / checklistCheckboxes.length) * 100) 
                : 0;

            // Render numeric metrics directly to display items
            document.getElementById('sticky-percentage-read').innerText = overallAuditPercentage + '%';
            document.getElementById('sticky-progress-fluid').style.width = overallAuditPercentage + '%';
            
            const matrixScoreDisplay = document.getElementById('dynamic-score-display');
            matrixScoreDisplay.innerText = overallAuditPercentage + '%';

            // Grade Matrix Classifications Mapping Rules
            const dynamicBadgeElement = document.getElementById('dynamic-badge-render');
            dynamicBadgeElement.className = 'verdict-badge'; // wipe structural mapping
            
            if (overallAuditPercentage >= 90) {
                dynamicBadgeElement.innerText = 'EXCELLENT (90-100% Core Metrics Audited)';
                dynamicBadgeElement.classList.add('excellent');
                matrixScoreDisplay.style.color = '#10b981';
            } else if (overallAuditPercentage >= 75) {
                dynamicBadgeElement.innerText = 'GOOD (75-89% Integrity Verified)';
                dynamicBadgeElement.classList.add('good');
                matrixScoreDisplay.style.color = '#3b82f6';
            } else if (overallAuditPercentage >= 60) {
                dynamicBadgeElement.innerText = 'AVERAGE (60-74% Check Complete)';
                dynamicBadgeElement.classList.add('average');
                matrixScoreDisplay.style.color = '#f59e0b';
            } else {
                dynamicBadgeElement.innerText = 'AVOID (<60% Progress Context Loaded)';
                dynamicBadgeElement.classList.add('avoid');
                matrixScoreDisplay.style.color = '#ef4444';
            }

            // Sync structural snapshots downwards into localStorage payload models
            saveStateToDisk();
        }

        // Dynamic Filtering Array System for Search Engine Tasks
        function filterChecks() {
            const queryRawString = document.getElementById('component-search-bar').value.toLowerCase();
            const searchCardsArray = document.querySelectorAll('.search-item');

            searchCardsArray.forEach(cardItem => {
                const indexedTitleTags = cardItem.getAttribute('data-search-keys').toLowerCase();
                if (indexedTitleTags.includes(queryRawString)) {
                    cardItem.style.display = 'block';
                } else {
                    cardItem.style.display = 'none';
                }
            });
        }

        // Hardware Screen Testing Display Canvas Engine Management
        function triggerScreenTest(colorHexCode) {
            const fullscreenLayerOverlay = document.getElementById('screen-tester');
            fullscreenLayerOverlay.style.backgroundColor = colorHexCode;
            fullscreenLayerOverlay.style.display = 'block';
        }

        function closeScreenTest() {
            document.getElementById('screen-tester').style.display = 'none';
        }

        // Handle physical keyboard interrupt signals to close full screen modal layers cleanly
        window.addEventListener('keydown', function(keyboardEvent) {
            if (keyboardEvent.key === 'Escape') {
                closeScreenTest();
            }
        });

        // HTML5 LocalStorage Persistence Strategy Engine Modules
        function saveStateToDisk() {
            const checkboxStatesStorageMap = [];
            document.querySelectorAll('.checklist-item input[type="checkbox"]').forEach((box, itemIndex) => {
                checkboxStatesStorageMap.push({ index: itemIndex, checked: box.checked });
            });

            const inputsTextDataStorageMap = [];
            document.querySelectorAll('.info-grid input').forEach((textInputBlock) => {
                inputsTextDataStorageMap.push({ id: textInputBlock.id, value: textInputBlock.value });
            });

            const comprehensiveStatePayload = {
                checkboxes: checkboxStatesStorageMap,
                textInputs: inputsTextDataStorageMap
            };

            localStorage.setItem('premium_laptop_audit_payload_v2', JSON.stringify(comprehensiveStatePayload));
        }

        function restoreStateFromDisk() {
            try {
                const serializedDiskDataString = localStorage.getItem('premium_laptop_audit_payload_v2');
                if (!serializedDiskDataString) return;

                const parsedDataModel = JSON.parse(serializedDiskDataString);

                if (parsedDataModel.textInputs) {
                    parsedDataModel.textInputs.forEach(savedInputField => {
                        const directFormElement = document.getElementById(savedInputField.id);
                        if (directFormElement) directFormElement.value = savedInputField.value;
                    });
                }

                if (parsedDataModel.checkboxes) {
                    const checkboxesNodeListArray = document.querySelectorAll('.checklist-item input[type="checkbox"]');
                    parsedDataModel.checkboxes.forEach(savedBoxItem => {
                        if (checkboxesNodeListArray[savedBoxItem.index]) {
                            checkboxesNodeListArray[savedBoxItem.index].checked = savedBoxItem.checked;
                        }
                    });
                }
                runMatrixMath();
            } catch (storageExceptionError) {
                console.error("Local data structural parse/restoral execution error: ", storageExceptionError);
            }
        }

        // Bind input mutation channels on all text inputs within metadata parameters
        document.querySelectorAll('.info-grid input').forEach(formInputField => {
            formInputField.addEventListener('input', saveStateToDisk);
        });

        // Full Interactive Global Reset Sub-System routine
        function resetAllElements() {
            if (confirm("Warning: This action will permanently clear all currently tracked metadata specs and checklist parameters. Proceed?")) {
                localStorage.removeItem('premium_laptop_audit_payload_v2');
                document.querySelectorAll('.checklist-item input[type="checkbox"]').forEach(boxItem => boxItem.checked = false);
                document.querySelectorAll('.info-grid input').forEach(textInputFieldItem => textInputFieldItem.value = '');
                runMatrixMath();
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }
        }

        // Bootstrap Core Event Initializers upon layout component loading states
        window.onload = function() {
            restoreStateFromDisk();
        };
    </script>
</body>
</html>

```
