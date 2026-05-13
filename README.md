<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tidy Team – Reinigungsvertrag mit Abgabegarantie</title>
    <style>
        :root {
            --purple: #2E1A5E;
            --purple-light: #4A2D8A;
            --blue: #00C8E0;
            --blue-light: #6EE7F7;
            --white: #FFFFFF;
            --gray-light: #F4F6F9;
            --gray: #8896A6;
            --shadow: 0 2px 12px rgba(46,26,94,.12);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; }

        html, body { height: 100%; }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: var(--purple);
            line-height: 1.5;
            position: relative;
            min-height: 100vh;
        }

        /* ── Background image: full-page, semi-transparent ── */
        body::before {
            content: '';
            position: fixed;
            inset: 0;
            background: url('background.png') top center / cover no-repeat;
            opacity: 0.12;
            z-index: -1;
            pointer-events: none;
        }

        /* ── Layout ── */
        .page-wrapper {
            max-width: 860px;
            margin: 0 auto;
            padding: 24px 20px 60px;
        }

        /* ── Header ── */
        .header {
            text-align: center;
            margin-bottom: 28px;
        }
        .header img {
            max-width: 260px;
            height: auto;
            margin-bottom: 8px;
        }
        .header h1 {
            font-size: 1.6rem;
            color: var(--purple);
            font-weight: 700;
            letter-spacing: .5px;
        }
        .header p {
            color: var(--gray);
            font-size: .92rem;
        }

        /* ── Sections / Cards ── */
        .section {
            background: rgba(255,255,255,.92);
            border: 1px solid #E2E6EC;
            border-radius: 12px;
            padding: 24px 28px;
            margin-bottom: 20px;
            box-shadow: var(--shadow);
        }
        .section h2 {
            font-size: 1.1rem;
            color: var(--purple);
            margin-bottom: 16px;
            border-bottom: 2px solid var(--blue);
            padding-bottom: 6px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .section h2 .icon { font-size: 1.25rem; }

        /* ── Form Elements ── */
        label {
            display: block;
            font-weight: 600;
            font-size: .88rem;
            margin-bottom: 4px;
            color: var(--purple);
        }
        input[type="text"],
        input[type="email"],
        input[type="tel"],
        input[type="date"],
        input[type="number"],
        input[type="time"],
        select,
        textarea {
            width: 100%;
            padding: 10px 14px;
            border: 1px solid #CDD3DC;
            border-radius: 8px;
            font-size: .95rem;
            color: #333;
            background: var(--white);
            transition: border-color .2s;
        }
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--blue);
            box-shadow: 0 0 0 3px rgba(0,200,224,.18);
        }
        textarea { resize: vertical; min-height: 90px; }

        .row { display: flex; gap: 16px; flex-wrap: wrap; margin-bottom: 14px; }
        .col { flex: 1 1 220px; }

        .checkbox-group label {
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 400;
            cursor: pointer;
            padding: 4px 0;
        }
        .checkbox-group input[type="checkbox"] {
            width: 18px; height: 18px; accent-color: var(--blue);
        }

        /* ── Leistungen checklist (original contract style) ── */
        .leistungen-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px 24px;
            margin-top: 8px;
        }
        .leistung-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 8px 12px;
            background: var(--gray-light);
            border-radius: 8px;
            gap: 8px;
        }
        .leistung-item .leistung-label {
            font-weight: 600;
            font-size: .9rem;
            color: var(--purple);
            flex: 1;
        }
        .leistung-item .leistung-controls {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .leistung-item .leistung-controls label {
            display: flex;
            align-items: center;
            gap: 4px;
            font-weight: 400;
            font-size: .85rem;
            margin-bottom: 0;
        }
        .leistung-item .leistung-controls input[type="radio"] {
            accent-color: var(--blue);
            width: 16px; height: 16px;
        }
        .leistung-item .leistung-controls input[type="number"] {
            width: 60px;
            padding: 4px 8px;
            font-size: .85rem;
            border-radius: 6px;
        }

        /* ── Extras section ── */
        .extras-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px 24px;
            margin-top: 8px;
        }
        .extra-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 8px 12px;
            background: var(--gray-light);
            border-radius: 8px;
            gap: 8px;
        }
        .extra-item .extra-label {
            font-weight: 600;
            font-size: .9rem;
            color: var(--purple);
            flex: 1;
        }
        .extra-item .extra-controls {
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .extra-item .extra-controls label {
            display: flex;
            align-items: center;
            gap: 4px;
            font-weight: 400;
            font-size: .85rem;
            margin-bottom: 0;
        }
        .extra-item .extra-controls input[type="radio"] {
            accent-color: var(--blue);
            width: 16px; height: 16px;
        }

        /* ── Buttons ── */
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            padding: 11px 22px;
            border: none;
            border-radius: 8px;
            font-size: .95rem;
            font-weight: 600;
            cursor: pointer;
            transition: background .2s, transform .1s;
        }
        .btn:active { transform: scale(.97); }
        .btn-primary {
            background: var(--purple);
            color: var(--white);
        }
        .btn-primary:hover { background: var(--purple-light); }
        .btn-blue {
            background: var(--blue);
            color: var(--white);
        }
        .btn-blue:hover { background: #00b0c8; }
        .btn-outline {
            background: transparent;
            border: 2px solid var(--purple);
            color: var(--purple);
        }
        .btn-outline:hover { background: var(--purple); color: var(--white); }
        .btn-whatsapp { background: #25D366; color: #fff; }
        .btn-whatsapp:hover { background: #1ebe57; }

        .actions {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 12px;
            justify-content: center;
        }

        /* ── Signature Canvas ── */
        .sig-wrapper {
            border: 2px dashed #CDD3DC;
            border-radius: 10px;
            position: relative;
            background: #FAFBFD;
            overflow: hidden;
        }
        .sig-canvas {
            width: 100%;
            height: 160px;
            display: block;
            cursor: crosshair;
            touch-action: none;
        }
        .sig-label {
            text-align: center;
            font-size: .82rem;
            color: var(--gray);
            padding: 4px 0;
            border-top: 1px solid #E2E6EC;
            background: #f9fafb;
        }
        .sig-actions {
            display: flex;
            gap: 8px;
            margin-top: 8px;
        }

        /* ── Dictation button ── */
        .dictation-btn {
            background: var(--blue);
            color: #fff;
            border: none;
            border-radius: 50%;
            width: 38px; height: 38px;
            font-size: 1.1rem;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            vertical-align: middle;
            margin-left: 8px;
            transition: background .2s;
        }
        .dictation-btn.recording { background: #E53935; animation: pulse 1s infinite; }
        @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.6} }

        /* ── Company Footer ── */
        .company-footer {
            text-align: center;
            padding: 20px 16px;
            margin-top: 24px;
            border-top: 2px solid var(--blue);
            font-size: .82rem;
            color: var(--gray);
            line-height: 1.7;
        }
        .company-footer strong {
            color: var(--purple);
            font-size: .88rem;
        }
        .company-footer a {
            color: var(--blue);
            text-decoration: none;
        }
        .company-footer a:hover { text-decoration: underline; }

        /* ── Responsive ── */
        @media(max-width:600px){
            .page-wrapper { padding: 12px 8px 40px; }
            .section { padding: 16px 14px; }
            .row { flex-direction: column; gap: 10px; }
            .header img { max-width: 180px; }
            .leistungen-grid, .extras-grid { grid-template-columns: 1fr; }
            .leistung-item, .extra-item { flex-wrap: wrap; }
        }

        /* ── Print ── */
        @media print {
            body::before { opacity: 0.06; }
            .btn, .sig-actions, .actions, .dictation-btn { display: none !important; }
            .section { break-inside: avoid; box-shadow: none; border: 1px solid #ddd; }
        }
    </style>
</head>
<body>

<div class="page-wrapper">

    <!-- Header -->
    <div class="header">
        <img src="Tidy_Team_Logo_RGB_2C_Zusatz.jpg" alt="Tidy Team – Die Reinigungsprofis">
        <h1>Reinigungsvertrag mit Abgabegarantie</h1>
        <p>Bitte füllen Sie alle relevanten Felder aus</p>
    </div>

    <form id="tidyForm">

        <!-- 1 ─ Kundendaten -->
        <div class="section">
            <h2><span class="icon">👤</span> Kundendaten</h2>
            <div class="row">
                <div class="col">
                    <label for="besichtigung">Besichtigungstermin</label>
                    <input type="date" id="besichtigung">
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="anrede">Anrede</label>
                    <select id="anrede">
                        <option value="">— bitte wählen —</option>
                        <option>Herr</option>
                        <option>Frau</option>
                        <option>Firma</option>
                    </select>
                </div>
                <div class="col">
                    <label for="vorname">Vorname</label>
                    <input type="text" id="vorname" placeholder="Max">
                </div>
                <div class="col">
                    <label for="nachname">Nachname</label>
                    <input type="text" id="nachname" placeholder="Muster">
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="firma">Firma (optional)</label>
                    <input type="text" id="firma">
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="strasse">Strasse &amp; Nr.</label>
                    <input type="text" id="strasse" placeholder="Musterstrasse 12">
                </div>
                <div class="col">
                    <label for="plz">PLZ</label>
                    <input type="text" id="plz" placeholder="8000">
                </div>
                <div class="col">
                    <label for="ort">Ort</label>
                    <input type="text" id="ort" placeholder="Zürich">
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="telefon">Telefon</label>
                    <input type="tel" id="telefon" placeholder="+41 79 123 45 67">
                </div>
                <div class="col">
                    <label for="email">E-Mail</label>
                    <input type="email" id="email" placeholder="max@muster.ch">
                </div>
            </div>
        </div>

        <!-- 2 ─ Objektdaten -->
        <div class="section">
            <h2><span class="icon">🏠</span> Objektdaten</h2>
            <div class="row">
                <div class="col">
                    <label for="obj_strasse">Objektadresse (falls abweichend)</label>
                    <input type="text" id="obj_strasse">
                </div>
                <div class="col">
                    <label for="obj_plz">PLZ / Ort</label>
                    <input type="text" id="obj_plz">
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="obj_typ">Objekttyp</label>
                    <select id="obj_typ">
                        <option value="">— bitte wählen —</option>
                        <option>Wohnung</option>
                        <option>Haus</option>
                        <option>Büro / Gewerbe</option>
                        <option>Praxis</option>
                        <option>Treppenhaus</option>
                        <option>Anderes</option>
                    </select>
                </div>
                <div class="col">
                    <label for="zimmer">Wohnung / Zimmeranzahl</label>
                    <input type="number" id="zimmer" min="1" max="30">
                </div>
                <div class="col">
                    <label for="flaeche">Wohnfläche (m²)</label>
                    <input type="number" id="flaeche" min="1">
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="stockwerk">Stockwerk</label>
                    <input type="text" id="stockwerk">
                </div>
                <div class="col">
                    <label for="lift">Lift vorhanden</label>
                    <select id="lift">
                        <option value="">— bitte wählen —</option>
                        <option>Ja</option>
                        <option>Nein</option>
                    </select>
                </div>
                <div class="col">
                    <label for="zugang">Schlüssel / Zugang</label>
                    <select id="zugang">
                        <option value="">— bitte wählen —</option>
                        <option>Kunde anwesend</option>
                        <option>Schlüssel hinterlegt</option>
                        <option>Schlüsselübergabe</option>
                        <option>Code / Badge</option>
                    </select>
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="preis">Preis (CHF)</label>
                    <input type="number" id="preis" step="0.05" min="0" placeholder="0.00">
                </div>
            </div>
        </div>

        <!-- 3 ─ Termin & Preise -->
        <div class="section">
            <h2><span class="icon">📅</span> Termin &amp; Preise</h2>
            <div class="row">
                <div class="col">
                    <label for="datum_start">Reinigungstermin (Datum)</label>
                    <input type="date" id="datum_start">
                </div>
                <div class="col">
                    <label for="abgabetermin">Abgabetermin (Datum)</label>
                    <input type="date" id="abgabetermin">
                </div>
                <div class="col">
                    <label for="zeit_von">Uhrzeit von</label>
                    <input type="time" id="zeit_von">
                </div>
                <div class="col">
                    <label for="zeit_bis">Uhrzeit bis</label>
                    <input type="time" id="zeit_bis">
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <label for="auftragstyp">Auftragstyp</label>
                    <select id="auftragstyp">
                        <option value="">— bitte wählen —</option>
                        <option>Unterhaltsreinigung</option>
                        <option>Grundreinigung</option>
                        <option>Endreinigung / Umzug</option>
                        <option>Baureinigung</option>
                        <option>Fensterreinigung</option>
                        <option>Büroreinigung</option>
                        <option>Sonderreinigung</option>
                    </select>
                </div>
                <div class="col">
                    <label for="turnus">Turnus</label>
                    <select id="turnus">
                        <option value="">— bitte wählen —</option>
                        <option>Einmalig</option>
                        <option>Wöchentlich</option>
                        <option>14-täglich</option>
                        <option>Monatlich</option>
                        <option>Nach Vereinbarung</option>
                    </select>
                </div>
                <div class="col">
                    <label for="preismodell">Preismodell</label>
                    <select id="preismodell">
                        <option value="">— bitte wählen —</option>
                        <option>Stundenansatz</option>
                        <option>Pauschal</option>
                        <option>Nach Aufwand</option>
                    </select>
                </div>
                <div class="col">
                    <label for="mwst">inkl. MwSt.</label>
                    <select id="mwst">
                        <option>Ja (8.1 %)</option>
                        <option>Nein</option>
                    </select>
                </div>
            </div>
        </div>

        <!-- 4 ─ Leistungen (Original contract checklist) -->
        <div class="section">
            <h2><span class="icon">🧹</span> Leistungen</h2>
            <div class="leistungen-grid">
                <!-- Storen / Lamellen -->
                <div class="leistung-item">
                    <span class="leistung-label">Storen / Lamellen</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_storen" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_storen" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Fenster -->
                <div class="leistung-item">
                    <span class="leistung-label">Fenster</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_fenster" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_fenster" value="Nein"> Nein</label>
                        <label>Stk. <input type="number" id="fenster_stk" min="0" max="99" style="width:55px;"></label>
                    </div>
                </div>
                <!-- WC / Bad -->
                <div class="leistung-item">
                    <span class="leistung-label">WC / Bad (Anzahl)</span>
                    <div class="leistung-controls">
                        <label>Stk. <input type="number" id="wc_stk" min="0" max="20" style="width:55px;"></label>
                    </div>
                </div>
                <!-- Waschmaschine / Tumbler -->
                <div class="leistung-item">
                    <span class="leistung-label">Waschmaschine / Tumbler</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_waschmaschine" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_waschmaschine" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Küche -->
                <div class="leistung-item">
                    <span class="leistung-label">Küche</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_kueche" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_kueche" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Balkon -->
                <div class="leistung-item">
                    <span class="leistung-label">Balkon</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_balkon" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_balkon" value="Nein"> Nein</label>
                        <label>Anz. <input type="number" id="balkon_anz" min="0" max="10" style="width:55px;"></label>
                    </div>
                </div>
                <!-- Wintergarten -->
                <div class="leistung-item">
                    <span class="leistung-label">Wintergarten</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_wintergarten" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_wintergarten" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Kärcher -->
                <div class="leistung-item">
                    <span class="leistung-label">Kärcher</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_kaercher" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_kaercher" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Teppich -->
                <div class="leistung-item">
                    <span class="leistung-label">Teppich</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_teppich" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_teppich" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Keller -->
                <div class="leistung-item">
                    <span class="leistung-label">Keller</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_keller" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_keller" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Estrich -->
                <div class="leistung-item">
                    <span class="leistung-label">Estrich</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_estrich" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_estrich" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Garage -->
                <div class="leistung-item">
                    <span class="leistung-label">Garage</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_garage" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_garage" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Briefkasten -->
                <div class="leistung-item">
                    <span class="leistung-label">Briefkasten</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_briefkasten" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_briefkasten" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Boden -->
                <div class="leistung-item">
                    <span class="leistung-label">Boden (wischen, saugen)</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_boden" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_boden" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Staubwischen -->
                <div class="leistung-item">
                    <span class="leistung-label">Staubwischen</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_staub" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_staub" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Bügeln / Wäsche -->
                <div class="leistung-item">
                    <span class="leistung-label">Bügeln / Wäsche</span>
                    <div class="leistung-controls">
                        <label><input type="radio" name="l_buegeln" value="Ja"> Ja</label>
                        <label><input type="radio" name="l_buegeln" value="Nein"> Nein</label>
                    </div>
                </div>
            </div>
        </div>

        <!-- 5 ─ Extras -->
        <div class="section">
            <h2><span class="icon">⚙️</span> Extras</h2>
            <div class="extras-grid">
                <!-- Bezahlung -->
                <div class="extra-item">
                    <span class="extra-label">Bezahlung</span>
                    <div class="extra-controls">
                        <label><input type="radio" name="bezahlung" value="Bar"> Bar</label>
                        <label><input type="radio" name="bezahlung" value="Twint"> Twint</label>
                    </div>
                </div>
                <!-- Übergabe dabei -->
                <div class="extra-item">
                    <span class="extra-label">Übergabe dabei</span>
                    <div class="extra-controls">
                        <label><input type="radio" name="uebergabe" value="Ja"> Ja</label>
                        <label><input type="radio" name="uebergabe" value="Nein"> Nein</label>
                    </div>
                </div>
                <!-- Vollmacht -->
                <div class="extra-item">
                    <span class="extra-label">Vollmacht</span>
                    <div class="extra-controls">
                        <label><input type="radio" name="vollmacht" value="Ja"> Ja</label>
                        <label><input type="radio" name="vollmacht" value="Nein"> Nein</label>
                    </div>
                </div>
            </div>
        </div>

        <!-- 6 ─ Bemerkungen + Diktierfunktion -->
        <div class="section">
            <h2><span class="icon">📝</span> Bemerkungen
                <button type="button" class="dictation-btn" id="dictBtn" title="Spracheingabe starten" onclick="toggleDictation()">🎤</button>
            </h2>
            <textarea id="bemerkungen" rows="5" placeholder="Zusätzliche Anmerkungen, Wünsche oder Sonderwünsche …"></textarea>
        </div>

        <!-- 7 ─ Unterschriften (Tidy Team + Kunde) -->
        <div class="section">
            <h2><span class="icon">✍️</span> Unterschriften</h2>
            <div class="row">
                <!-- Tidy Team Signature -->
                <div class="col">
                    <div class="sig-wrapper">
                        <canvas id="signatureCanvasTT" class="sig-canvas"></canvas>
                        <div class="sig-label">Tidy Team</div>
                    </div>
                    <div class="sig-actions">
                        <button type="button" class="btn btn-outline" onclick="clearSignature('TT')" style="font-size:.85rem;padding:7px 16px;">Löschen</button>
                    </div>
                </div>
                <!-- Kunde Signature -->
                <div class="col">
                    <div class="sig-wrapper">
                        <canvas id="signatureCanvasKunde" class="sig-canvas"></canvas>
                        <div class="sig-label">Kunde</div>
                    </div>
                    <div class="sig-actions">
                        <button type="button" class="btn btn-outline" onclick="clearSignature('Kunde')" style="font-size:.85rem;padding:7px 16px;">Löschen</button>
                    </div>
                </div>
            </div>
            <div class="row" style="margin-top:12px;">
                <div class="col">
                    <label for="ort_datum">Ort / Datum</label>
                    <input type="text" id="ort_datum" placeholder="Zürich, 13.05.2026">
                </div>
            </div>
        </div>

        <!-- 8 ─ Aktionen -->
        <div class="section" style="text-align:center;">
            <h2 style="justify-content:center;"><span class="icon">📤</span> Vertrag senden / speichern</h2>
            <div class="actions">
                <button type="button" class="btn btn-primary" onclick="generatePDF()">📄 PDF erstellen</button>
                <button type="button" class="btn btn-blue" onclick="sendEmail()">✉️ Per E-Mail senden</button>
                <button type="button" class="btn btn-whatsapp" onclick="sendWhatsApp()">💬 WhatsApp senden</button>
                <button type="button" class="btn btn-outline" onclick="window.print()">🖨️ Drucken</button>
            </div>
        </div>

    </form>

    <!-- Company Footer -->
    <div class="company-footer">
        <strong>Tidy Team GmbH</strong><br>
        Freiestrasse 38, 8580 Amriswil<br>
        Tel: <a href="tel:+41787379716">078 737 97 16</a> · 
        E-Mail: <a href="mailto:info@tidy-team.ch">info@tidy-team.ch</a> · 
        Web: <a href="https://tidy-team.ch" target="_blank">tidy-team.ch</a><br>
        UBS IBAN: CH84 0020 3203 1111 7301 A – 0203-1111 73.01A
    </div>

</div>

<!-- ════════════════════════════════════════
     JavaScript
     ════════════════════════════════════════ -->
<script>
/* ── Dual Signature Pads ── */
const sigPads = {};

function initSignaturePad(suffix) {
    const canvas = document.getElementById('signatureCanvas' + suffix);
    const ctx = canvas.getContext('2d');
    const pad = {
        canvas, ctx,
        drawing: false,
        hasSignature: false,
        signatureImageBackup: null
    };
    sigPads[suffix] = pad;

    function resize() {
        const rect = canvas.parentElement.getBoundingClientRect();
        const dpr = window.devicePixelRatio || 1;
        const newW = Math.floor(rect.width * dpr);
        const newH = Math.floor(160 * dpr);

        if (pad.hasSignature) {
            try { pad.signatureImageBackup = canvas.toDataURL('image/png'); } catch (e) {}
        }

        canvas.width = newW;
        canvas.height = newH;
        canvas.style.height = '160px';
        ctx.scale(dpr, dpr);
        ctx.lineWidth = 2;
        ctx.lineCap = 'round';
        ctx.strokeStyle = '#2E1A5E';

        if (pad.signatureImageBackup && pad.hasSignature) {
            const img = new Image();
            img.onload = function() {
                ctx.save();
                ctx.setTransform(1, 0, 0, 1, 0, 0);
                ctx.drawImage(img, 0, 0, newW, newH);
                ctx.restore();
            };
            img.src = pad.signatureImageBackup;
        }
    }

    function getPos(e) {
        const rect = canvas.getBoundingClientRect();
        const t = e.touches ? e.touches[0] : e;
        return { x: t.clientX - rect.left, y: t.clientY - rect.top };
    }

    canvas.addEventListener('mousedown', e => { pad.drawing = true; pad.hasSignature = true; ctx.beginPath(); const p = getPos(e); ctx.moveTo(p.x, p.y); });
    canvas.addEventListener('mousemove', e => { if (!pad.drawing) return; const p = getPos(e); ctx.lineTo(p.x, p.y); ctx.stroke(); });
    canvas.addEventListener('mouseup', () => { pad.drawing = false; if (pad.hasSignature) try { pad.signatureImageBackup = canvas.toDataURL('image/png'); } catch(e){} });
    canvas.addEventListener('mouseleave', () => { pad.drawing = false; });
    canvas.addEventListener('touchstart', e => { e.preventDefault(); pad.drawing = true; pad.hasSignature = true; ctx.beginPath(); const p = getPos(e); ctx.moveTo(p.x, p.y); }, { passive: false });
    canvas.addEventListener('touchmove', e => { e.preventDefault(); if (!pad.drawing) return; const p = getPos(e); ctx.lineTo(p.x, p.y); ctx.stroke(); }, { passive: false });
    canvas.addEventListener('touchend', e => { pad.drawing = false; if (pad.hasSignature) try { pad.signatureImageBackup = canvas.toDataURL('image/png'); } catch(e2){} });

    resize();
    window.addEventListener('resize', resize);
}

initSignaturePad('TT');
initSignaturePad('Kunde');

function clearSignature(suffix) {
    const pad = sigPads[suffix];
    const dpr = window.devicePixelRatio || 1;
    pad.ctx.save();
    pad.ctx.setTransform(1, 0, 0, 1, 0, 0);
    pad.ctx.clearRect(0, 0, pad.canvas.width, pad.canvas.height);
    pad.ctx.restore();
    pad.hasSignature = false;
    pad.signatureImageBackup = null;
}

/* ── Dictation (Web Speech API) ── */
let recognition, isRecording = false;
function toggleDictation() {
    const btn = document.getElementById('dictBtn');
    const ta = document.getElementById('bemerkungen');
    if (!('webkitSpeechRecognition' in window || 'SpeechRecognition' in window)) {
        alert('Spracheingabe wird in diesem Browser nicht unterstützt. Bitte verwenden Sie Chrome.');
        return;
    }
    if (isRecording) {
        recognition.stop();
        return;
    }
    const SR = window.SpeechRecognition || window.webkitSpeechRecognition;
    recognition = new SR();
    recognition.lang = 'de-CH';
    recognition.continuous = true;
    recognition.interimResults = true;
    let finalText = ta.value;
    recognition.onresult = e => {
        let interim = '';
        for (let i = e.resultIndex; i < e.results.length; i++) {
            if (e.results[i].isFinal) {
                finalText += e.results[i][0].transcript + ' ';
            } else {
                interim += e.results[i][0].transcript;
            }
        }
        ta.value = finalText + interim;
    };
    recognition.onstart = () => { isRecording = true; btn.classList.add('recording'); };
    recognition.onend = () => { isRecording = false; btn.classList.remove('recording'); ta.value = finalText; };
    recognition.onerror = e => { console.error(e); isRecording = false; btn.classList.remove('recording'); };
    recognition.start();
}

/* ── Collect form data ── */
function collectData() {
    const f = id => (document.getElementById(id)?.value || '').trim();
    const r = name => { const el = document.querySelector('input[name="'+name+'"]:checked'); return el ? el.value : ''; };

    // Collect all Leistungen
    const leistungen = {};
    const leistungNames = ['l_storen','l_fenster','l_waschmaschine','l_kueche','l_balkon','l_wintergarten','l_kaercher','l_teppich','l_keller','l_estrich','l_garage','l_briefkasten','l_boden','l_staub','l_buegeln'];
    leistungNames.forEach(name => { leistungen[name] = r(name); });

    const padTT = sigPads['TT'];
    const padKunde = sigPads['Kunde'];

    return {
        besichtigung: f('besichtigung'),
        anrede: f('anrede'), vorname: f('vorname'), nachname: f('nachname'),
        firma: f('firma'), strasse: f('strasse'), plz: f('plz'), ort: f('ort'),
        telefon: f('telefon'), email: f('email'),
        obj_strasse: f('obj_strasse'), obj_plz: f('obj_plz'),
        obj_typ: f('obj_typ'), zimmer: f('zimmer'), flaeche: f('flaeche'),
        stockwerk: f('stockwerk'), lift: f('lift'), zugang: f('zugang'),
        preis: f('preis'),
        auftragstyp: f('auftragstyp'), turnus: f('turnus'),
        datum_start: f('datum_start'), abgabetermin: f('abgabetermin'),
        zeit_von: f('zeit_von'), zeit_bis: f('zeit_bis'),
        preismodell: f('preismodell'), mwst: f('mwst'),
        leistungen,
        fenster_stk: f('fenster_stk'), wc_stk: f('wc_stk'), balkon_anz: f('balkon_anz'),
        bezahlung: r('bezahlung'), uebergabe: r('uebergabe'), vollmacht: r('vollmacht'),
        bemerkungen: f('bemerkungen'), ort_datum: f('ort_datum'),
        signatureTT: padTT.hasSignature ? (padTT.signatureImageBackup || padTT.canvas.toDataURL('image/png')) : null,
        signatureKunde: padKunde.hasSignature ? (padKunde.signatureImageBackup || padKunde.canvas.toDataURL('image/png')) : null
    };
}

/* ── PDF Generation ── */
function generatePDF() {
    if (typeof window.jspdf !== 'undefined') {
        buildJsPDF();
        return;
    }
    const loadScript = (url) => {
        return new Promise((resolve, reject) => {
            const s = document.createElement('script');
            s.src = url;
            s.onload = resolve;
            s.onerror = reject;
            document.head.appendChild(s);
        });
    };
    const primaryURL = 'https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.2/jspdf.umd.min.js';
    const fallbackURL = 'https://unpkg.com/jspdf@2.5.2/dist/jspdf.umd.min.js';

    loadScript(primaryURL)
        .catch(() => loadScript(fallbackURL))
        .then(() => buildJsPDF())
        .catch(() => {
            alert('PDF-Bibliothek konnte nicht geladen werden. Verwenden Sie die Druckfunktion.');
            window.print();
        });
}

function buildJsPDF() {
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF('p', 'mm', 'a4');
    const d = collectData();
    let y = 20;

    doc.setFont('helvetica', 'bold');
    doc.setFontSize(16);
    doc.setTextColor(46, 26, 94);
    doc.text('Reinigungsvertrag mit Abgabegarantie', 105, y, { align: 'center' });
    y += 4;
    doc.setFontSize(9);
    doc.setFont('helvetica', 'normal');
    doc.setTextColor(100, 100, 100);
    doc.text('Tidy Team GmbH', 105, y + 4, { align: 'center' });
    y += 14;

    function heading(text) {
        doc.setFont('helvetica', 'bold');
        doc.setFontSize(11);
        doc.setTextColor(0, 200, 224);
        doc.text(text, 14, y);
        y += 2;
        doc.setDrawColor(0, 200, 224);
        doc.line(14, y, 196, y);
        y += 7;
    }

    function line(label, value) {
        if (!value) return;
        if (y > 270) { doc.addPage(); y = 20; }
        doc.setFont('helvetica', 'bold');
        doc.setFontSize(9);
        doc.setTextColor(46, 26, 94);
        doc.text(label + ':', 14, y);
        doc.setFont('helvetica', 'normal');
        doc.setTextColor(60, 60, 60);
        doc.text(String(value), 65, y);
        y += 5.5;
    }

    heading('Kundendaten');
    line('Besichtigungstermin', d.besichtigung);
    line('Anrede', d.anrede);
    line('Name', (d.vorname + ' ' + d.nachname).trim());
    line('Firma', d.firma);
    line('Adresse', d.strasse + ', ' + d.plz + ' ' + d.ort);
    line('Telefon', d.telefon);
    line('E-Mail', d.email);

    heading('Objektdaten');
    line('Objektadresse', d.obj_strasse || '(wie Kundenadresse)');
    line('PLZ / Ort', d.obj_plz);
    line('Objekttyp', d.obj_typ);
    line('Zimmer', d.zimmer);
    line('Fläche', d.flaeche ? d.flaeche + ' m²' : '');
    line('Stockwerk', d.stockwerk);
    line('Lift', d.lift);
    line('Zugang', d.zugang);
    line('Preis', d.preis ? 'CHF ' + d.preis : '');

    heading('Termin');
    line('Reinigungstermin', d.datum_start);
    line('Abgabetermin', d.abgabetermin);
    line('Uhrzeit', (d.zeit_von && d.zeit_bis) ? d.zeit_von + ' – ' + d.zeit_bis : '');
    line('Auftragstyp', d.auftragstyp);
    line('Turnus', d.turnus);
    line('Preismodell', d.preismodell);
    line('MwSt.', d.mwst);

    heading('Leistungen');
    const leistungLabels = {
        'l_storen': 'Storen / Lamellen', 'l_fenster': 'Fenster', 'l_waschmaschine': 'Waschmaschine / Tumbler',
        'l_kueche': 'Küche', 'l_balkon': 'Balkon', 'l_wintergarten': 'Wintergarten',
        'l_kaercher': 'Kärcher', 'l_teppich': 'Teppich', 'l_keller': 'Keller',
        'l_estrich': 'Estrich', 'l_garage': 'Garage', 'l_briefkasten': 'Briefkasten',
        'l_boden': 'Boden', 'l_staub': 'Staubwischen', 'l_buegeln': 'Bügeln / Wäsche'
    };
    for (const [key, label] of Object.entries(leistungLabels)) {
        let val = d.leistungen[key];
        if (key === 'l_fenster' && d.fenster_stk) val = (val || 'Ja') + ' (' + d.fenster_stk + ' Stk.)';
        if (key === 'l_balkon' && d.balkon_anz) val = (val || 'Ja') + ' (' + d.balkon_anz + ' Anz.)';
        if (val) line(label, val);
    }
    if (d.wc_stk) line('WC / Bad', d.wc_stk + ' Stk.');

    heading('Extras');
    line('Bezahlung', d.bezahlung);
    line('Übergabe dabei', d.uebergabe);
    line('Vollmacht', d.vollmacht);

    if (d.bemerkungen) {
        heading('Bemerkungen');
        doc.setFont('helvetica', 'normal');
        doc.setFontSize(9);
        doc.setTextColor(60, 60, 60);
        const lines = doc.splitTextToSize(d.bemerkungen, 170);
        doc.text(lines, 14, y);
        y += lines.length * 4.5 + 5;
    }

    // Signatures
    if (d.signatureTT || d.signatureKunde) {
        if (y > 210) { doc.addPage(); y = 20; }
        heading('Unterschriften');
        const sigY = y;
        if (d.signatureTT) {
            try {
                doc.addImage(d.signatureTT, 'PNG', 14, sigY, 75, 28);
            } catch (e) { console.error(e); }
            doc.setFont('helvetica', 'normal');
            doc.setFontSize(8);
            doc.setTextColor(100, 100, 100);
            doc.text('Tidy Team', 14, sigY + 32);
        }
        if (d.signatureKunde) {
            try {
                doc.addImage(d.signatureKunde, 'PNG', 110, sigY, 75, 28);
            } catch (e) { console.error(e); }
            doc.setFont('helvetica', 'normal');
            doc.setFontSize(8);
            doc.setTextColor(100, 100, 100);
            doc.text('Kunde', 110, sigY + 32);
        }
        y = sigY + 38;
    }
    line('Ort / Datum', d.ort_datum);

    // Footer
    y = 282;
    doc.setFont('helvetica', 'normal');
    doc.setFontSize(7);
    doc.setTextColor(120, 120, 120);
    doc.text('Tidy Team GmbH · Freiestrasse 38, 8580 Amriswil · Tel: 078 737 97 16 · info@tidy-team.ch · tidy-team.ch · UBS IBAN: CH84 0020 3203 1111 7301 A', 105, y, { align: 'center' });

    const name = (d.nachname || 'vertrag').replace(/\s+/g, '_');
    const fileName = 'TidyTeam_Vertrag_' + name + '.pdf';

    try {
        const blob = doc.output('blob');
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.href = url;
        a.download = fileName;
        a.style.display = 'none';
        document.body.appendChild(a);
        a.click();
        setTimeout(() => {
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
        }, 500);
    } catch (e) {
        try {
            doc.save(fileName);
        } catch (e2) {
            const pdfDataUri = doc.output('datauristring');
            const w = window.open('', '_blank');
            if (w) {
                w.document.write('<iframe width="100%" height="100%" src="' + pdfDataUri + '"></iframe>');
            } else {
                alert('Bitte erlauben Sie Pop-ups für diese Seite, um das PDF anzuzeigen.');
            }
        }
    }
}

/* ── E-Mail ── */
function sendEmail() {
    const d = collectData();
    const subject = encodeURIComponent('Reinigungsvertrag mit Abgabegarantie – ' + d.vorname + ' ' + d.nachname);
    const body = encodeURIComponent(
        'Reinigungsvertrag mit Abgabegarantie\n\n' +
        'Besichtigungstermin: ' + d.besichtigung + '\n\n' +
        'Kunde: ' + d.anrede + ' ' + d.vorname + ' ' + d.nachname + '\n' +
        'Firma: ' + d.firma + '\n' +
        'Adresse: ' + d.strasse + ', ' + d.plz + ' ' + d.ort + '\n' +
        'Telefon: ' + d.telefon + '\n' +
        'E-Mail: ' + d.email + '\n\n' +
        'Objekt: ' + d.obj_typ + ', ' + d.zimmer + ' Zimmer, ' + d.flaeche + ' m², Lift: ' + d.lift + '\n' +
        'Auftrag: ' + d.auftragstyp + ' (' + d.turnus + ')\n' +
        'Reinigungstermin: ' + d.datum_start + '\n' +
        'Abgabetermin: ' + d.abgabetermin + '\n' +
        'Uhrzeit: ' + d.zeit_von + '–' + d.zeit_bis + '\n' +
        'Preis: CHF ' + d.preis + ' (' + d.preismodell + ', ' + d.mwst + ')\n\n' +
        'Bezahlung: ' + d.bezahlung + '\n' +
        'Übergabe dabei: ' + d.uebergabe + '\n' +
        'Vollmacht: ' + d.vollmacht + '\n\n' +
        'Bemerkungen: ' + d.bemerkungen + '\n\n' +
        'Ort/Datum: ' + d.ort_datum
    );
    const recipient = d.email ? d.email : '';
    window.location.href = 'mailto:' + recipient + '?subject=' + subject + '&body=' + body;
}

/* ── WhatsApp ── */
function sendWhatsApp() {
    const d = collectData();
    const text = encodeURIComponent(
        '🧹 *Reinigungsvertrag mit Abgabegarantie*\n\n' +
        '📋 *Besichtigung:* ' + d.besichtigung + '\n' +
        '👤 *Kunde:* ' + d.anrede + ' ' + d.vorname + ' ' + d.nachname + '\n' +
        '📍 ' + d.strasse + ', ' + d.plz + ' ' + d.ort + '\n' +
        '📞 ' + d.telefon + '\n' +
        '✉️ ' + d.email + '\n\n' +
        '🏠 *Objekt:* ' + d.obj_typ + ', ' + d.zimmer + ' Zi., ' + d.flaeche + ' m², Lift: ' + d.lift + '\n' +
        '🧹 *Auftrag:* ' + d.auftragstyp + ' (' + d.turnus + ')\n' +
        '📅 *Reinigungstermin:* ' + d.datum_start + '\n' +
        '📅 *Abgabetermin:* ' + d.abgabetermin + '\n' +
        '⏰ *Uhrzeit:* ' + d.zeit_von + '–' + d.zeit_bis + '\n' +
        '💰 *Preis:* CHF ' + d.preis + ' (' + d.preismodell + ')\n\n' +
        '💳 *Bezahlung:* ' + d.bezahlung + '\n' +
        '🤝 *Übergabe dabei:* ' + d.uebergabe + '\n' +
        '📜 *Vollmacht:* ' + d.vollmacht + '\n\n' +
        '📝 *Bemerkungen:* ' + d.bemerkungen
    );
    const phone = d.telefon.replace(/[^0-9+]/g, '');
    window.open('https://wa.me/' + phone + '?text=' + text, '_blank');
}
</script>

</body>
</html>
