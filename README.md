<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>कर्मवीर (KARAMVEER) - खेती का हर काम, एक ही जगह</title>
    <link href="https://fonts.googleapis.com/css2?family=Mukta:wght@400;500;600;700;800&family=Noto+Sans+Devanagari:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1B5E20;
            --primary-light: #2E7D32;
            --primary-container: #E8F5E9;
            --secondary: #F9A825;
            --secondary-container: #FFF9C4;
            --accent: #0288D1;
            --background: #F4F7F4;
            --surface: #FFFFFF;
            --text-dark: #1C261C;
            --text-muted: #556B55;
            --border: #D7E2D7;
            --danger: #D32F2F;
            --success: #2E7D32;
            --warning: #F57C00;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Mukta', 'Noto Sans Devanagari', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--background);
            color: var(--text-dark);
            display: flex;
            justify-content: center;
            min-height: 100vh;
        }

        /* App Container (Mobile Framed / Responsive) */
        .app-container {
            width: 100%;
            max-width: 480px;
            background: var(--surface);
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            position: relative;
            box-shadow: 0 4px 20px rgba(0,0,0,0.08);
        }

        /* Top Bar */
        header {
            background: linear-gradient(135deg, var(--primary), var(--primary-light));
            color: white;
            padding: 14px 16px;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,0.15);
        }

        .header-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand-logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            width: 36px;
            height: 36px;
            background: var(--secondary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
        }

        .brand-title {
            font-size: 20px;
            font-weight: 800;
            line-height: 1.1;
            letter-spacing: 0.5px;
        }

        .brand-tagline {
            font-size: 11px;
            color: var(--secondary-container);
            font-weight: 500;
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .btn-lang {
            background: rgba(255,255,255,0.2);
            color: white;
            border: none;
            padding: 4px 10px;
            border-radius: 14px;
            font-size: 12px;
            font-weight: 700;
            cursor: pointer;
        }

        .role-chip {
            background: var(--secondary);
            color: #332000;
            padding: 4px 10px;
            border-radius: 16px;
            font-size: 12px;
            font-weight: 700;
            cursor: pointer;
            border: none;
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .user-subbar {
            margin-top: 8px;
            font-size: 11px;
            color: rgba(255,255,255,0.9);
            display: flex;
            align-items: center;
            gap: 5px;
        }

        /* Main View Container */
        main {
            flex: 1;
            padding: 14px 16px 85px 16px;
            overflow-y: auto;
        }

        /* Search & Hero */
        .search-box {
            background: white;
            border: 2px solid var(--border);
            border-radius: 24px;
            padding: 8px 14px;
            display: flex;
            align-items: center;
            gap: 8px;
            margin-bottom: 12px;
            box-shadow: 0 2px 6px rgba(0,0,0,0.03);
        }

        .search-box input {
            border: none;
            outline: none;
            width: 100%;
            font-size: 14px;
        }

        /* Chips Horizontal Scroll */
        .chip-scroll {
            display: flex;
            gap: 8px;
            overflow-x: auto;
            padding-bottom: 8px;
            margin-bottom: 12px;
            scrollbar-width: none;
        }
        .chip-scroll::-webkit-scrollbar { display: none; }

        .chip {
            padding: 6px 14px;
            border-radius: 18px;
            background: var(--background);
            border: 1px solid var(--border);
            font-size: 12px;
            font-weight: 600;
            white-space: nowrap;
            cursor: pointer;
        }

        .chip.active {
            background: var(--primary);
            color: white;
            border-color: var(--primary);
        }

        /* Machine Cards */
        .card {
            background: white;
            border: 1px solid var(--border);
            border-radius: 16px;
            padding: 14px;
            margin-bottom: 14px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.03);
            transition: transform 0.15s;
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 6px;
        }

        .badge-cat {
            background: var(--secondary-container);
            color: var(--HarvestOnGoldColor, #7A4E00);
            font-size: 11px;
            font-weight: 700;
            padding: 3px 8px;
            border-radius: 6px;
        }

        .badge-status {
            font-size: 11px;
            font-weight: 700;
            padding: 3px 8px;
            border-radius: 10px;
        }
        .status-available { background: #E8F5E9; color: var(--success); }
        .status-busy { background: #FFEBEE; color: var(--danger); }
        .status-progress { background: #E0F2F1; color: var(--accent); }

        .machine-title {
            font-size: 16px;
            font-weight: 700;
            color: var(--text-dark);
        }

        .machine-meta {
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 8px;
        }

        .price-strip {
            background: var(--primary-container);
            border-radius: 8px;
            padding: 8px 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin: 8px 0;
        }

        .price-val {
            font-size: 18px;
            font-weight: 800;
            color: var(--primary);
        }

        .card-actions {
            display: flex;
            gap: 10px;
            margin-top: 12px;
        }

        .btn {
            flex: 1;
            padding: 10px 12px;
            border-radius: 10px;
            border: none;
            font-size: 13px;
            font-weight: 700;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
            text-decoration: none;
        }

        .btn-outline {
            background: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
        }

        .btn-primary {
            background: var(--primary);
            color: white;
        }

        .btn-gold {
            background: var(--secondary);
            color: #332000;
        }

        /* Bottom Nav */
        nav.bottom-nav {
            position: fixed;
            bottom: 0;
            width: 100%;
            max-width: 480px;
            background: white;
            border-top: 1px solid var(--border);
            display: flex;
            justify-content: space-around;
            padding: 8px 0 10px 0;
            z-index: 100;
        }

        .nav-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            background: none;
            border: none;
            color: var(--text-muted);
            font-size: 11px;
            font-weight: 600;
            cursor: pointer;
            gap: 2px;
        }

        .nav-item.active {
            color: var(--primary);
            font-weight: 800;
        }

        .nav-icon {
            font-size: 20px;
        }

        /* Modal Styles */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 16px;
        }

        .modal-card {
            background: white;
            width: 100%;
            max-width: 420px;
            border-radius: 20px;
            padding: 20px;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .modal-title {
            font-size: 18px;
            font-weight: 800;
            margin-bottom: 12px;
            color: var(--primary);
        }

        .form-group {
            margin-bottom: 12px;
        }

        .form-group label {
            display: block;
            font-size: 12px;
            font-weight: 700;
            margin-bottom: 4px;
            color: var(--text-dark);
        }

        .form-control {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border);
            border-radius: 8px;
            font-size: 13px;
            outline: none;
        }

        .bill-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 12px;
            margin: 10px 0;
        }

        .bill-table td, .bill-table th {
            padding: 6px 0;
        }

        .bill-table tr.total-row {
            font-size: 14px;
            font-weight: 800;
            border-top: 2px solid var(--border);
            border-bottom: 2px solid var(--border);
        }

        /* Map Canvas */
        .map-canvas-container {
            width: 100%;
            height: 180px;
            background: #E8F5E9;
            border-radius: 12px;
            position: relative;
            overflow: hidden;
            margin: 10px 0;
            border: 1px solid var(--border);
        }

        canvas#liveMapCanvas {
            width: 100%;
            height: 100%;
        }

        .toast {
            position: fixed;
            bottom: 75px;
            left: 50%;
            transform: translateX(-50%);
            background: #2E3B2E;
            color: white;
            padding: 10px 20px;
            border-radius: 24px;
            font-size: 12px;
            font-weight: 600;
            z-index: 2000;
            display: none;
            box-shadow: 0 4px 12px rgba(0,0,0,0.2);
        }
    </style>
</head>
<body>

<div class="app-container">
    <!-- Header -->
    <header>
        <div class="header-top">
            <div class="brand-logo">
                <div class="logo-icon">🚜</div>
                <div>
                    <div class="brand-title" id="txtBrandTitle">कर्मवीर</div>
                    <div class="brand-tagline" id="txtBrandTagline">खेती का हर काम, एक ही जगह</div>
                </div>
            </div>
            <div class="header-actions">
                <button class="btn-lang" onclick="toggleLanguage()">ENG</button>
                <button class="role-chip" onclick="openRoleModal()">
                    <span id="txtRoleLabel">किसान</span> ▾
                </button>
            </div>
        </div>
        <div class="user-subbar">
            <span>📍 <span id="txtUserVillage">दिलीप निषाद • उतई, दुर्ग (Chhattisgarh)</span></span>
        </div>
    </header>

    <!-- Main Content Tab Views -->
    <main id="mainContainer">
        <!-- Rendered dynamically by JS -->
    </main>

    <!-- Bottom Navigation -->
    <nav class="bottom-nav" id="bottomNav">
        <!-- Dynamic per role -->
    </nav>
</div>

<!-- Toast Notice -->
<div class="toast" id="toastNotice"></div>

<!-- 1. Role Picker Modal -->
<div class="modal-overlay" id="modalRole">
    <div class="modal-card">
        <h3 class="modal-title">प्रोफ़ाइल एवं रोल चुनें</h3>
        <p style="font-size:12px; color:var(--text-muted); margin-bottom:12px;">आप सीधे किसी भी पंजीकृत प्रोफाइल में स्विच कर सकते हैं:</p>
        <div id="roleUserList"></div>
        <div style="margin-top:16px; display:flex; gap:10px;">
            <button class="btn btn-outline" onclick="resetDemoData()">डेटा रीसेट करें</button>
            <button class="btn btn-primary" onclick="closeModal('modalRole')">बंद करें</button>
        </div>
    </div>
</div>

<!-- 2. Booking Modal -->
<div class="modal-overlay" id="modalBooking">
    <div class="modal-card">
        <h3 class="modal-title" id="bmTitle">मशीन बुकिंग अनुरोध</h3>
        <p id="bmSub" style="font-size:12px; color:var(--text-muted); margin-bottom:10px;"></p>
        
        <div class="price-strip">
            <div>
                <span style="font-size:11px;">दर:</span>
                <div class="price-val" id="bmRate">₹2200 / एकड़</div>
            </div>
            <div style="text-align:right;">
                <span style="font-size:11px;">अनुमानित कुल:</span>
                <div class="price-val" id="bmTotal" style="color:var(--primary);">₹8800</div>
            </div>
        </div>
        <p style="font-size:10px; color:#A06000; margin-bottom:10px;">⚠️ अंतिम दर कार्य स्थल की स्थिति अनुसार मशीन मालिक से सहमति उपरांत मान्य होगी।</p>

        <div class="form-group">
            <label>जमीन का क्षेत्रफल (एकड़ में):</label>
            <input type="number" id="bmAcres" class="form-control" value="4.0" oninput="recalcBookingEstimate()">
        </div>
        <div class="form-group">
            <label>खेत का पता / लैंडमार्क:</label>
            <input type="text" id="bmLocation" class="form-control" value="उतई नहर पुलिया के पास, खसरा 102">
        </div>
        <div class="form-group">
            <label>आवश्यकता दिनांक:</label>
            <input type="date" id="bmDate" class="form-control">
        </div>
        <div class="form-group">
            <label>पसंदीदा समय (Slot):</label>
            <select id="bmSlot" class="form-control">
                <option value="सुबह (Morning)">सुबह (Morning)</option>
                <option value="दोपहर (Afternoon)">दोपहर (Afternoon)</option>
                <option value="शाम (Evening)">शाम (Evening)</option>
            </select>
        </div>

        <div style="display:flex; gap:10px; margin-top:14px;">
            <button class="btn btn-outline" onclick="closeModal('modalBooking')">रद्द करें</button>
            <button class="btn btn-primary" onclick="submitBookingRequest()">अनुरोध भेजें</button>
        </div>
    </div>
</div>

<!-- 3. Live Location Tracker Modal -->
<div class="modal-overlay" id="modalLiveTrack">
    <div class="modal-card">
        <h3 class="modal-title">लाइव मशीन स्थान ट्रैकर</h3>
        <p id="trackMachineTitle" style="font-size:12px; color:var(--text-muted);"></p>
        
        <div class="map-canvas-container">
            <canvas id="liveMapCanvas" width="400" height="180"></canvas>
        </div>

        <div style="display:flex; justify-content:space-between; margin-bottom:10px; font-size:13px; font-weight:700;">
            <span style="color:var(--primary);">📍 शेष दूरी: <span id="trackDistance">1.8 किमी</span></span>
            <span style="color:var(--warning);">⏱️ समय: <span id="trackEta">~6 मिनट</span></span>
        </div>
        <p style="font-size:11px; color:var(--text-muted); margin-bottom:14px;">
            🔒 सुरक्षा: यह लाइव लोकेशन केवल अधिकृत सक्रिय बुकिंग के दौरान किसान एवं मशीन मालिक के मध्य सुरक्षित रूप से साझा की जाती है।
        </p>

        <div style="display:flex; gap:10px;">
            <button class="btn btn-outline" onclick="closeModal('modalLiveTrack')">बंद करें</button>
            <a id="btnCallOwnerTrack" href="#" class="btn btn-primary">मालिक को कॉल करें</a>
        </div>
    </div>
</div>

<!-- 4. Digital Bill Modal -->
<div class="modal-overlay" id="modalBill">
    <div class="modal-card">
        <h3 class="modal-title">डिजिटल कृषि बिल एवं रसीद</h3>
        <p id="billNumberLabel" style="font-size:11px; color:var(--text-muted);"></p>
        
        <div style="background:var(--background); padding:10px; border-radius:8px; font-size:12px; margin:8px 0;">
            <div id="billFarmerInfo" style="font-weight:700;"></div>
            <div id="billMachineInfo"></div>
        </div>

        <table class="bill-table">
            <tr><td>कार्य मात्रा:</td><td style="text-align:right;" id="billQty"></td></tr>
            <tr><td>निर्धारित दर:</td><td style="text-align:right;" id="billRate"></td></tr>
            <tr><td>मूल कार्य राशि:</td><td style="text-align:right;" id="billSubtotal"></td></tr>
            <tr><td>छूट (Discount):</td><td style="text-align:right; color:var(--success);" id="billDiscount">- ₹0</td></tr>
            <tr class="total-row"><td>अंतिम कुल योग:</td><td style="text-align:right; color:var(--primary);" id="billFinalTotal"></td></tr>
            <tr><td>प्राप्त भुगतान:</td><td style="text-align:right; color:var(--success); font-weight:700;" id="billPaid"></td></tr>
            <tr style="font-weight:800; color:var(--danger);"><td>शेष बकाया राशि:</td><td style="text-align:right;" id="billBalance"></td></tr>
        </table>

        <div style="display:flex; gap:10px; margin-top:14px;">
            <button class="btn btn-outline" onclick="closeModal('modalBill')">बंद करें</button>
            <button class="btn btn-primary" onclick="shareBillPdf()">शेयर / प्रिंट करें</button>
        </div>
    </div>
</div>

<!-- 5. Record Payment Modal -->
<div class="modal-overlay" id="modalRecordPayment">
    <div class="modal-card">
        <h3 class="modal-title">भुगतान दर्ज करें (Record Payment)</h3>
        <p id="payBillDetails" style="font-size:12px; color:var(--danger); font-weight:700; margin-bottom:10px;"></p>
        
        <div class="form-group">
            <label>प्राप्त राशि (₹):</label>
            <input type="number" id="payAmountInput" class="form-control">
        </div>
        <div class="form-group">
            <label>भुगतान का माध्यम:</label>
            <select id="payMethodSelect" class="form-control">
                <option value="CASH">नकद (Cash)</option>
                <option value="UPI">UPI / PhonePe / GPay</option>
            </select>
        </div>
        <div class="form-group">
            <label>संदर्भ / UTR / रसीद क्र. (वैकल्पिक):</label>
            <input type="text" id="payRefInput" class="form-control" placeholder="उदा. UPI/942523/881">
        </div>

        <div style="display:flex; gap:10px; margin-top:14px;">
            <button class="btn btn-outline" onclick="closeModal('modalRecordPayment')">रद्द करें</button>
            <button class="btn btn-primary" onclick="confirmPaymentRecord()">सुरक्षित करें</button>
        </div>
    </div>
</div>

<!-- 6. Phone Booking Modal (Owner) -->
<div class="modal-overlay" id="modalPhoneBooking">
    <div class="modal-card">
        <h3 class="modal-title">कॉल पर मिली बुकिंग दर्ज करें</h3>
        <p style="font-size:11px; color:var(--text-muted); margin-bottom:10px;">फोन कॉल पर प्राप्त ऑर्डर का डिजिटल रिकॉर्ड बनाएं:</p>
        
        <div class="form-group">
   
