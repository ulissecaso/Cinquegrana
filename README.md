<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="theme-color" content="#c8102e">
<title>Cinquegrana Scavolini</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --red: #c8102e;
  --red-dark: #a00d24;
  --red-light: #f5e6e9;
  --black: #111111;
  --gray-dark: #2a2a2a;
  --gray: #666;
  --gray-light: #f4f4f2;
  --white: #ffffff;
  --cream: #faf9f7;
  --gold: #b8963e;
  --radius: 12px;
  --shadow: 0 4px 24px rgba(0,0,0,0.08);
  --shadow-lg: 0 12px 48px rgba(0,0,0,0.14);
}

* { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--cream);
  color: var(--black);
  min-height: 100vh;
  max-width: 430px;
  margin: 0 auto;
  position: relative;
  overflow-x: hidden;
}

/* ── HEADER ── */
.header {
  background: var(--black);
  color: var(--white);
  padding: 18px 20px 14px;
  position: sticky;
  top: 0;
  z-index: 100;
  display: flex;
  align-items: center;
  gap: 14px;
  box-shadow: 0 2px 16px rgba(0,0,0,0.3);
}
.header-logo {
  width: 38px;
  height: 38px;
  background: var(--red);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  font-weight: 600;
  color: white;
  flex-shrink: 0;
}
.header-text { flex: 1; }
.header-brand {
  font-family: 'Cormorant Garamond', serif;
  font-size: 17px;
  font-weight: 600;
  letter-spacing: 0.3px;
  line-height: 1.2;
}
.header-sub {
  font-size: 10px;
  color: rgba(255,255,255,0.5);
  letter-spacing: 1.5px;
  text-transform: uppercase;
  margin-top: 1px;
}

/* ── NAV TABS ── */
.nav {
  background: var(--white);
  display: flex;
  border-bottom: 2px solid var(--gray-light);
  position: sticky;
  top: 70px;
  z-index: 99;
  overflow-x: auto;
  scrollbar-width: none;
}
.nav::-webkit-scrollbar { display: none; }
.nav-btn {
  flex: 1;
  min-width: 70px;
  padding: 12px 8px 10px;
  border: none;
  background: none;
  cursor: pointer;
  font-family: 'DM Sans', sans-serif;
  font-size: 10px;
  font-weight: 500;
  color: var(--gray);
  letter-spacing: 0.5px;
  text-transform: uppercase;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  transition: color 0.2s;
  border-bottom: 2px solid transparent;
  margin-bottom: -2px;
  white-space: nowrap;
}
.nav-btn .icon { font-size: 18px; }
.nav-btn.active { color: var(--red); border-bottom-color: var(--red); }

/* ── PAGES ── */
.page { display: none; padding: 20px 16px 100px; animation: fadeIn 0.25s ease; }
.page.active { display: block; }
@keyframes fadeIn { from { opacity: 0; transform: translateY(6px); } to { opacity: 1; transform: translateY(0); } }

/* ── SECTION TITLE ── */
.section-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 28px;
  font-weight: 300;
  color: var(--black);
  margin-bottom: 4px;
  line-height: 1.1;
}
.section-subtitle {
  font-size: 12px;
  color: var(--gray);
  letter-spacing: 0.5px;
  margin-bottom: 20px;
}

/* ── SEARCH BOX ── */
.search-wrap { position: relative; margin-bottom: 16px; }
.search-input {
  width: 100%;
  padding: 13px 16px 13px 44px;
  border: 1.5px solid #e8e8e6;
  border-radius: var(--radius);
  font-family: 'DM Sans', sans-serif;
  font-size: 14px;
  background: var(--white);
  color: var(--black);
  outline: none;
  transition: border-color 0.2s;
}
.search-input:focus { border-color: var(--red); }
.search-icon {
  position: absolute;
  left: 14px;
  top: 50%;
  transform: translateY(-50%);
  color: var(--gray);
  font-size: 16px;
}

/* ── COMMISSIONE CARD ── */
.comm-card {
  background: var(--white);
  border-radius: var(--radius);
  padding: 16px;
  margin-bottom: 10px;
  box-shadow: var(--shadow);
  cursor: pointer;
  transition: transform 0.15s, box-shadow 0.15s;
  border-left: 4px solid transparent;
}
.comm-card:active { transform: scale(0.98); }
.comm-card.stato-lavorazione { border-left-color: #f59e0b; }
.comm-card.stato-pronto { border-left-color: #10b981; }
.comm-card.stato-pianificata { border-left-color: #3b82f6; }
.comm-card.stato-consegnato { border-left-color: #6b7280; }
.comm-card.stato-attesa { border-left-color: var(--red); }

.comm-top { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 8px; }
.comm-id { font-size: 11px; color: var(--gray); letter-spacing: 0.5px; font-weight: 500; }
.stato-badge {
  font-size: 10px;
  font-weight: 600;
  padding: 3px 8px;
  border-radius: 20px;
  letter-spacing: 0.3px;
}
.badge-lavorazione { background: #fef3c7; color: #92400e; }
.badge-pronto { background: #d1fae5; color: #065f46; }
.badge-pianificata { background: #dbeafe; color: #1e40af; }
.badge-consegnato { background: #f3f4f6; color: #374151; }
.badge-attesa { background: #fee2e2; color: #991b1b; }

.comm-name { font-size: 16px; font-weight: 600; margin-bottom: 4px; }
.comm-meta { font-size: 12px; color: var(--gray); display: flex; gap: 12px; flex-wrap: wrap; }
.comm-meta span { display: flex; align-items: center; gap: 4px; }

/* ── DETAIL MODAL ── */
.modal-overlay {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.6);
  z-index: 200;
  align-items: flex-end;
}
.modal-overlay.open { display: flex; animation: fadeIn 0.2s ease; }
.modal {
  background: var(--white);
  border-radius: 20px 20px 0 0;
  width: 100%;
  max-width: 430px;
  margin: 0 auto;
  padding: 24px 20px 40px;
  max-height: 85vh;
  overflow-y: auto;
  animation: slideUp 0.3s ease;
}
@keyframes slideUp { from { transform: translateY(100%); } to { transform: translateY(0); } }
.modal-handle { width: 40px; height: 4px; background: #e0e0e0; border-radius: 2px; margin: 0 auto 20px; }
.modal-title { font-family: 'Cormorant Garamond', serif; font-size: 24px; font-weight: 400; margin-bottom: 4px; }
.modal-id { font-size: 12px; color: var(--gray); margin-bottom: 20px; }
.modal-row { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid var(--gray-light); }
.modal-label { font-size: 12px; color: var(--gray); font-weight: 500; text-transform: uppercase; letter-spacing: 0.5px; }
.modal-value { font-size: 14px; font-weight: 500; text-align: right; max-width: 60%; }
.modal-close {
  width: 100%;
  margin-top: 24px;
  padding: 14px;
  background: var(--black);
  color: white;
  border: none;
  border-radius: var(--radius);
  font-family: 'DM Sans', sans-serif;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  letter-spacing: 0.5px;
}

/* ── TIMELINE ── */
.timeline { margin: 20px 0; }
.timeline-step { display: flex; gap: 12px; margin-bottom: 0; }
.timeline-left { display: flex; flex-direction: column; align-items: center; }
.timeline-dot {
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #e0e0e0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 10px;
  flex-shrink: 0;
  transition: background 0.3s;
}
.timeline-dot.done { background: var(--red); color: white; }
.timeline-dot.active { background: var(--black); color: white; }
.timeline-line { width: 2px; height: 32px; background: #e0e0e0; margin: 2px 0; }
.timeline-line.done { background: var(--red); }
.timeline-content { padding-top: 2px; padding-bottom: 20px; }
.timeline-step-name { font-size: 13px; font-weight: 600; }
.timeline-step-desc { font-size: 11px; color: var(--gray); margin-top: 2px; }

/* ── FORM ASSISTENZA ── */
.form-group { margin-bottom: 16px; }
.form-label { font-size: 12px; font-weight: 600; color: var(--gray-dark); letter-spacing: 0.5px; text-transform: uppercase; margin-bottom: 6px; display: block; }
.form-input, .form-select, .form-textarea {
  width: 100%;
  padding: 13px 16px;
  border: 1.5px solid #e8e8e6;
  border-radius: var(--radius);
  font-family: 'DM Sans', sans-serif;
  font-size: 14px;
  background: var(--white);
  color: var(--black);
  outline: none;
  transition: border-color 0.2s;
  appearance: none;
}
.form-input:focus, .form-select:focus, .form-textarea:focus { border-color: var(--red); }
.form-textarea { resize: none; height: 100px; }
.form-submit {
  width: 100%;
  padding: 16px;
  background: var(--red);
  color: white;
  border: none;
  border-radius: var(--radius);
  font-family: 'DM Sans', sans-serif;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  letter-spacing: 0.3px;
  margin-top: 8px;
  transition: background 0.2s;
}
.form-submit:active { background: var(--red-dark); }
.success-msg {
  display: none;
  background: #d1fae5;
  color: #065f46;
  padding: 16px;
  border-radius: var(--radius);
  font-size: 14px;
  font-weight: 500;
  text-align: center;
  margin-top: 12px;
}

/* ── PUNTI VENDITA ── */
.store-card {
  background: var(--white);
  border-radius: var(--radius);
  overflow: hidden;
  margin-bottom: 14px;
  box-shadow: var(--shadow);
}
.store-header {
  background: var(--black);
  color: white;
  padding: 16px;
  display: flex;
  align-items: center;
  gap: 12px;
}
.store-icon {
  width: 36px;
  height: 36px;
  background: var(--red);
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  flex-shrink: 0;
}
.store-city { font-size: 16px; font-weight: 600; }
.store-brand { font-size: 11px; color: rgba(255,255,255,0.5); letter-spacing: 0.5px; }
.store-body { padding: 16px; }
.store-info-row { display: flex; align-items: center; gap: 10px; padding: 8px 0; border-bottom: 1px solid var(--gray-light); }
.store-info-row:last-child { border-bottom: none; }
.store-info-icon { font-size: 16px; width: 20px; text-align: center; flex-shrink: 0; }
.store-info-text { font-size: 13px; color: var(--gray-dark); }
.store-actions { display: flex; gap: 8px; padding: 12px 16px 16px; }
.store-btn {
  flex: 1;
  padding: 10px;
  border-radius: 8px;
  border: none;
  font-family: 'DM Sans', sans-serif;
  font-size: 12px;
  font-weight: 600;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  transition: opacity 0.2s;
  text-decoration: none;
}
.store-btn:active { opacity: 0.7; }
.btn-call { background: var(--red); color: white; }
.btn-whatsapp { background: #25d366; color: white; }
.btn-map { background: var(--gray-light); color: var(--black); }

/* ── ARREDATORI ── */
.arreda-card {
  background: var(--white);
  border-radius: var(--radius);
  padding: 16px;
  margin-bottom: 10px;
  box-shadow: var(--shadow);
  display: flex;
  align-items: center;
  gap: 14px;
}
.arreda-avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--red), var(--red-dark));
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  color: white;
  font-weight: 600;
  flex-shrink: 0;
}
.arreda-info { flex: 1; }
.arreda-name { font-size: 15px; font-weight: 600; margin-bottom: 2px; }
.arreda-store { font-size: 12px; color: var(--gray); }
.arreda-actions { display: flex; gap: 8px; }
.arreda-btn {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: none;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  cursor: pointer;
  text-decoration: none;
  transition: opacity 0.2s;
}
.arreda-btn:active { opacity: 0.7; }
.btn-wa { background: #25d366; }
.btn-ph { background: var(--gray-light); }

/* ── CHI SIAMO ── */
.about-hero {
  background: var(--black);
  border-radius: var(--radius);
  padding: 28px 20px;
  margin-bottom: 16px;
  text-align: center;
  position: relative;
  overflow: hidden;
}
.about-hero::before {
  content: '';
  position: absolute;
  top: -30px;
  right: -30px;
  width: 120px;
  height: 120px;
  background: var(--red);
  border-radius: 50%;
  opacity: 0.15;
}
.about-logo-big {
  width: 64px;
  height: 64px;
  background: var(--red);
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Cormorant Garamond', serif;
  font-size: 32px;
  font-weight: 600;
  color: white;
  margin: 0 auto 14px;
}
.about-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 22px;
  color: white;
  font-weight: 400;
  margin-bottom: 4px;
}
.about-subtitle { font-size: 12px; color: rgba(255,255,255,0.5); letter-spacing: 1px; text-transform: uppercase; }
.about-card {
  background: var(--white);
  border-radius: var(--radius);
  padding: 20px;
  margin-bottom: 12px;
  box-shadow: var(--shadow);
}
.about-card-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 8px;
  color: var(--red);
}
.about-card-text { font-size: 14px; color: var(--gray-dark); line-height: 1.6; }
.brand-chips { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 10px; }
.brand-chip {
  padding: 6px 14px;
  background: var(--gray-light);
  border-radius: 20px;
  font-size: 12px;
  font-weight: 500;
  color: var(--gray-dark);
}
.contatti-row {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 14px 0;
  border-bottom: 1px solid var(--gray-light);
  text-decoration: none;
  color: inherit;
}
.contatti-row:last-child { border-bottom: none; }
.contatti-icon {
  width: 40px;
  height: 40px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  flex-shrink: 0;
}
.icon-wa { background: #e7faf0; }
.icon-ph { background: #e8f0fe; }
.icon-mail { background: #fce8e6; }
.contatti-info { flex: 1; }
.contatti-label { font-size: 11px; color: var(--gray); font-weight: 500; text-transform: uppercase; letter-spacing: 0.5px; }
.contatti-value { font-size: 14px; font-weight: 500; margin-top: 1px; }
.contatti-arrow { color: var(--gray); font-size: 16px; }

/* ── EMPTY STATE ── */
.empty-state { text-align: center; padding: 48px 24px; }
.empty-icon { font-size: 48px; margin-bottom: 12px; }
.empty-title { font-size: 16px; font-weight: 600; margin-bottom: 6px; }
.empty-text { font-size: 13px; color: var(--gray); line-height: 1.5; }

/* ── LOADING ── */
.loading { text-align: center; padding: 40px 20px; color: var(--gray); font-size: 14px; }
.spinner { width: 28px; height: 28px; border: 3px solid var(--gray-light); border-top-color: var(--red); border-radius: 50%; animation: spin 0.8s linear infinite; margin: 0 auto 12px; }
@keyframes spin { to { transform: rotate(360deg); } }

/* ── BOTTOM NAV (mobile) ── */
.bottom-nav {
  position: fixed;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100%;
  max-width: 430px;
  background: var(--white);
  border-top: 1px solid #e8e8e6;
  display: flex;
  z-index: 100;
  padding-bottom: env(safe-area-inset-bottom);
}
.bottom-btn {
  flex: 1;
  padding: 10px 4px 8px;
  border: none;
  background: none;
  cursor: pointer;
  font-family: 'DM Sans', sans-serif;
  font-size: 9px;
  font-weight: 500;
  color: var(--gray);
  letter-spacing: 0.3px;
  text-transform: uppercase;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  transition: color 0.2s;
}
.bottom-btn .b-icon { font-size: 20px; }
.bottom-btn.active { color: var(--red); }
</style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <div class="header-logo">C</div>
  <div class="header-text">
    <div class="header-brand">Cinquegrana Scavolini</div>
    <div class="header-sub">Arredamenti • Dal 1990</div>
  </div>
</div>

<!-- PAGES -->

<!-- 1. COMMISSIONI -->
<div class="page active" id="page-commissioni">

  <!-- SCHERMATA LOGIN -->
  <div id="login-box">
    <div class="section-title">Le tue commissioni</div>
    <div class="section-subtitle">Inserisci il tuo codice per accedere</div>
    <div class="about-card" style="margin-top:8px">
      <div class="form-group" style="margin-bottom:0">
        <label class="form-label">Codice sito</label>
        <input class="form-input" id="codice-input" type="text" placeholder="es. 4935Ill" autocomplete="off" autocapitalize="off" spellcheck="false">
        <div id="login-error" style="display:none;color:#991b1b;font-size:13px;margin-top:8px;">Codice non trovato. Controlla e riprova.</div>
      </div>
      <button class="form-submit" style="margin-top:16px" onclick="accediConCodice()">Accedi</button>
    </div>
    <div style="margin-top:16px;background:var(--gray-light);border-radius:var(--radius);padding:14px;font-size:12px;color:var(--gray);line-height:1.6;">
      Il codice sito ti e stato fornito dal tuo arredatore. E composto da un numero seguito da alcune lettere, es. 4935Ill
    </div>
  </div>

  <!-- SCHERMATA RISULTATI -->
  <div id="risultati-box" style="display:none">
    <div style="display:flex;align-items:center;gap:10px;margin-bottom:4px">
      <button onclick="tornaLogin()" style="background:none;border:none;cursor:pointer;font-size:20px;padding:0;color:var(--gray)">&#8592;</button>
      <div class="section-title" style="margin-bottom:0">Le tue commissioni</div>
    </div>
    <div class="section-subtitle" id="codice-attivo" style="padding-left:30px"></div>
    <div id="commissioni-list"></div>
  </div>

</div>

<!-- 2. ASSISTENZA -->
<div class="page" id="page-assistenza">
  <div class="section-title">Assistenza</div>
  <div class="section-subtitle">Apri una segnalazione</div>
  <div class="about-card">
    <div class="form-group">
      <label class="form-label">Numero commissione</label>
      <input class="form-input" id="ass-id" type="text" placeholder="es. 439/26">
    </div>
    <div class="form-group">
      <label class="form-label">Nome e cognome</label>
      <input class="form-input" id="ass-nome" type="text" placeholder="Il tuo nome">
    </div>
    <div class="form-group">
      <label class="form-label">Tipo problema</label>
      <select class="form-select" id="ass-tipo">
        <option value="">Seleziona…</option>
        <option>Ritardo consegna</option>
        <option>Prodotto difettoso</option>
        <option>Merce mancante</option>
        <option>Problema montaggio</option>
        <option>Altro</option>
      </select>
    </div>
    <div class="form-group">
      <label class="form-label">Descrizione</label>
      <textarea class="form-textarea" id="ass-desc" placeholder="Descrivi il problema…"></textarea>
    </div>
    <button class="form-submit" onclick="inviaAssistenza()">📩 Invia segnalazione</button>
    <div class="success-msg" id="success-msg">✅ Segnalazione inviata! Ti contatteremo presto.</div>
  </div>
  <div class="about-card" style="margin-top:14px">
    <div class="about-card-title" style="font-size:15px">Contatto diretto assistenza</div>
    <a class="contatti-row" href="https://wa.me/393333236226">
      <div class="contatti-icon icon-wa">💬</div>
      <div class="contatti-info">
        <div class="contatti-label">WhatsApp Assistenza</div>
        <div class="contatti-value">Scrivici ora</div>
      </div>
      <div class="contatti-arrow">›</div>
    </a>
    <a class="contatti-row" href="tel:+390818919381">
      <div class="contatti-icon icon-ph">📞</div>
      <div class="contatti-info">
        <div class="contatti-label">Telefono</div>
        <div class="contatti-value">081 891 9381</div>
      </div>
      <div class="contatti-arrow">›</div>
    </a>
    <a class="contatti-row" href="mailto:assistenza@cinquegrana.it">
      <div class="contatti-icon icon-mail">✉️</div>
      <div class="contatti-info">
        <div class="contatti-label">Email</div>
        <div class="contatti-value">assistenza@cinquegrana.it</div>
      </div>
      <div class="contatti-arrow">›</div>
    </a>
  </div>
</div>

<!-- 3. PUNTI VENDITA -->
<div class="page" id="page-negozi">
  <div class="section-title">Punti vendita</div>
  <div class="section-subtitle">4 showroom in Campania</div>

  <div class="store-card">
    <div class="store-header">
      <div class="store-icon">🏪</div>
      <div>
        <div class="store-city">Sant'Arpino</div>
        <div class="store-brand">SCAVOLINI STORE</div>
      </div>
    </div>
    <div class="store-body">
      <div class="store-info-row"><span class="store-info-icon">📍</span><span class="store-info-text">Via Alessandro Volta 146, 81030 Sant'Arpino (CE)</span></div>
      <div class="store-info-row"><span class="store-info-icon">🕐</span><span class="store-info-text">Dom 10:00–13:00 / 16:30–20:00 • Lun–Sab 9:00–13:00 / 15:30–20:00</span></div>
      <div class="store-info-row"><span class="store-info-icon">📞</span><span class="store-info-text">081 891 9381</span></div>
    </div>
    <div class="store-actions">
      <a class="store-btn btn-call" href="tel:+390818919381">📞 Chiama</a>
      <a class="store-btn btn-whatsapp" href="https://wa.me/393333236226">💬 WhatsApp</a>
      <a class="store-btn btn-map" href="https://maps.google.com/?q=Via+Alessandro+Volta+146+Sant'Arpino+CE" target="_blank">🗺 Mappa</a>
    </div>
  </div>

  <div class="store-card">
    <div class="store-header">
      <div class="store-icon">🏪</div>
      <div>
        <div class="store-city">Giugliano in Campania</div>
        <div class="store-brand">SCAVOLINI STORE</div>
      </div>
    </div>
    <div class="store-body">
      <div class="store-info-row"><span class="store-info-icon">📍</span><span class="store-info-text">Via Appia Km. 18, 80014 Giugliano in Campania (NA)</span></div>
      <div class="store-info-row"><span class="store-info-icon">🕐</span><span class="store-info-text">Dom 10:00–13:00 / 16:30–20:00 • Lun–Sab 9:00–13:00 / 15:30–20:00</span></div>
      <div class="store-info-row"><span class="store-info-icon">📞</span><span class="store-info-text">081 891 9381</span></div>
    </div>
    <div class="store-actions">
      <a class="store-btn btn-call" href="tel:+390818919381">📞 Chiama</a>
      <a class="store-btn btn-whatsapp" href="https://wa.me/393668703035">💬 WhatsApp</a>
      <a class="store-btn btn-map" href="https://maps.google.com/?q=Via+Appia+Km18+Giugliano+in+Campania+NA" target="_blank">🗺 Mappa</a>
    </div>
  </div>

  <div class="store-card">
    <div class="store-header">
      <div class="store-icon">🏪</div>
      <div>
        <div class="store-city">Villaricca</div>
        <div class="store-brand">SCAVOLINI STORE</div>
      </div>
    </div>
    <div class="store-body">
      <div class="store-info-row"><span class="store-info-icon">📍</span><span class="store-info-text">Corso Europa, 80010 Villaricca (NA)</span></div>
      <div class="store-info-row"><span class="store-info-icon">🕐</span><span class="store-info-text">Dom 10:00–13:00 / 16:30–20:00 • Lun–Sab 9:00–13:00 / 15:30–20:00</span></div>
      <div class="store-info-row"><span class="store-info-icon">📞</span><span class="store-info-text">081 891 9381</span></div>
    </div>
    <div class="store-actions">
      <a class="store-btn btn-call" href="tel:+390818919381">📞 Chiama</a>
      <a class="store-btn btn-whatsapp" href="https://wa.me/393341532717">💬 WhatsApp</a>
      <a class="store-btn btn-map" href="https://maps.google.com/?q=Corso+Europa+Villaricca+NA" target="_blank">🗺 Mappa</a>
    </div>
  </div>

  <div class="store-card">
    <div class="store-header">
      <div class="store-icon">🏪</div>
      <div>
        <div class="store-city">Ottaviano</div>
        <div class="store-brand">SCAVOLINI STORE</div>
      </div>
    </div>
    <div class="store-body">
      <div class="store-info-row"><span class="store-info-icon">📍</span><span class="store-info-text">Via Pentelete 84, 80044 Ottaviano (NA)</span></div>
      <div class="store-info-row"><span class="store-info-icon">🕐</span><span class="store-info-text">Dom 10:00–13:00 / 16:30–20:00 • Lun–Sab 9:30–13:00 / 15:30–20:00</span></div>
      <div class="store-info-row"><span class="store-info-icon">📞</span><span class="store-info-text">081 891 9381</span></div>
    </div>
    <div class="store-actions">
      <a class="store-btn btn-call" href="tel:+390818919381">📞 Chiama</a>
      <a class="store-btn btn-whatsapp" href="https://wa.me/393668703814">💬 WhatsApp</a>
      <a class="store-btn btn-map" href="https://maps.google.com/?q=Via+Pentelete+84+Ottaviano+NA" target="_blank">🗺 Mappa</a>
    </div>
  </div>
</div>

<!-- 4. ARREDATORI -->
<div class="page" id="page-arredatori">
  <div class="section-title">Il tuo arredatore</div>
  <div class="section-subtitle">Contatta il tuo referente</div>
  <div id="arredatori-list">
    <div class="loading"><div class="spinner"></div>Caricamento team…</div>
  </div>
</div>

<!-- 5. CHI SIAMO -->
<div class="page" id="page-chisiamo">
  <div class="about-hero">
    <div class="about-logo-big">C</div>
    <div class="about-title">Arredamenti Cinquegrana</div>
    <div class="about-subtitle">Scavolini Store • Dal 1990</div>
  </div>
  <div class="about-card">
    <div class="about-card-title">La nostra storia</div>
    <div class="about-card-text">Da oltre 30 anni progettiamo e realizziamo ambienti su misura per le famiglie della Campania. Passione, qualità e attenzione al cliente sono i valori che ci guidano ogni giorno.</div>
  </div>
  <div class="about-card">
    <div class="about-card-title">I brand che trattiamo</div>
    <div class="brand-chips">
      <span class="brand-chip">Scavolini</span>
      <span class="brand-chip">Lube Cucine</span>
      <span class="brand-chip">Creo Kitchens</span>
      <span class="brand-chip">Febal Casa</span>
    </div>
  </div>
  <div class="about-card">
    <div class="about-card-title">Contattaci</div>
    <a class="contatti-row" href="https://wa.me/393333236226">
      <div class="contatti-icon icon-wa">💬</div>
      <div class="contatti-info">
        <div class="contatti-label">WhatsApp</div>
        <div class="contatti-value">Scrivici su WhatsApp</div>
      </div>
      <div class="contatti-arrow">›</div>
    </a>
    <a class="contatti-row" href="tel:+390818919381">
      <div class="contatti-icon icon-ph">📞</div>
      <div class="contatti-info">
        <div class="contatti-label">Telefono</div>
        <div class="contatti-value">081 891 9381</div>
      </div>
      <div class="contatti-arrow">›</div>
    </a>
    <a class="contatti-row" href="mailto:info@cinquegrana.it">
      <div class="contatti-icon icon-mail">✉️</div>
      <div class="contatti-info">
        <div class="contatti-label">Email</div>
        <div class="contatti-value">info@cinquegrana.it</div>
      </div>
      <div class="contatti-arrow">›</div>
    </a>
  </div>
</div>

<!-- BOTTOM NAV -->
<div class="bottom-nav">
  <button class="bottom-btn active" onclick="showPage('commissioni',this)">
    <span class="b-icon">📦</span>Commissioni
  </button>
  <button class="bottom-btn" onclick="showPage('assistenza',this)">
    <span class="b-icon">🔧</span>Assistenza
  </button>
  <button class="bottom-btn" onclick="showPage('negozi',this)">
    <span class="b-icon">🏪</span>Negozi
  </button>
  <button class="bottom-btn" onclick="showPage('arredatori',this)">
    <span class="b-icon">👤</span>Team
  </button>
  <button class="bottom-btn" onclick="showPage('chisiamo',this)">
    <span class="b-icon">ℹ️</span>Chi siamo
  </button>
</div>

<!-- DETAIL MODAL -->
<div class="modal-overlay" id="modal-overlay" onclick="closeModal(event)">
  <div class="modal" id="modal-content">
    <div class="modal-handle"></div>
    <div id="modal-body"></div>
    <button class="modal-close" onclick="closeModal()">Chiudi</button>
  </div>
</div>

<script>
// ── CONFIGURAZIONE ──
// IMPORTANTE: sostituisci SHEET_ID con l'ID del tuo Google Sheet
// e assicurati che il foglio sia condiviso pubblicamente in lettura
const SHEET_ID = 'IL_TUO_SHEET_ID_QUI';
const COMMISSIONI_SHEET = 'COMMISSIONI';
const ARREDATORI_SHEET = 'ARREDATORI';

// Dati di esempio (usati finché non configuri il Google Sheet)
const DEMO_COMMISSIONI = [
  { codice:'9999Test', descrizione:'Cucina Lube modello Clover - basi rovere voyage, pensili cemento, top laminato grigio', data_ordine:'22/03/2026', data_consegna:'30/04/2026', stato:'In lavorazione', arredatore:'Angela Cinquegrana' },
  { id:'433/26', nome:'Caterina', cognome:'Auriemma', data_ordine:'21/03/2026', data_consegna:'26/04/2026', stato:'🔵 Consegna Pianificata', arredatore:'Angela Cinquegrana', note:'Soggiorno completo' },
  { id:'434/26', nome:'Erika', cognome:'Carbone', data_ordine:'21/03/2026', data_consegna:'30/05/2026', stato:'🔴 In attesa prodotto', arredatore:'Stefania Ciardulli', note:'In attesa conferma fornitore' },
  { id:'435/26', nome:'Giuseppe', cognome:'Ferraro', data_ordine:'20/03/2026', data_consegna:'15/04/2026', stato:'✅ Consegnato', arredatore:'Luigi Franzese', note:'Camera da letto completa' },
  { id:'436/26', nome:'Maria', cognome:'De Rosa', data_ordine:'19/03/2026', data_consegna:'10/04/2026', stato:'🟢 Pronto', arredatore:'Angela Cinquegrana', note:'Bagno su misura' },
];

const DEMO_ARREDATORI = [
  { nome:'Angela', cognome:'Cinquegrana', negozio:"Sant'Arpino", telefono:'3331234567', email:'angela@cinquegrana.it' },
  { nome:'Stefania', cognome:'Ciardulli', negozio:'Giugliano', telefono:'3337654321', email:'stefania@cinquegrana.it' },
  { nome:'Luigi', cognome:'Franzese', negozio:'Villaricca', telefono:'3339876543', email:'luigi@cinquegrana.it' },
  { nome:'Rossella', cognome:'Cinquegrana', negozio:'Ottaviano', telefono:'3332345678', email:'rossella@cinquegrana.it' },
];

let allCommissioni = [];
let commissioniVisibili = []; // commissioni filtrate per codice attivo

// ── LOGIN CODICE SITO ──
function accediConCodice() {
  const codice = document.getElementById('codice-input').value.trim();
  if (!codice) return;

  // Cerca nel dataset tutte le righe con quel codice (case-insensitive)
  const trovate = allCommissioni.filter(c => {
    const cod = (c.codice || c['Codice'] || '').toLowerCase();
    return cod === codice.toLowerCase();
  });

  if (trovate.length === 0) {
    document.getElementById('login-error').style.display = 'block';
    return;
  }

  document.getElementById('login-error').style.display = 'none';
  commissioniVisibili = trovate;

  // Mostra i risultati
  document.getElementById('login-box').style.display = 'none';
  document.getElementById('risultati-box').style.display = 'block';
  document.getElementById('codice-attivo').textContent = 'Codice: ' + codice + ' — ' + trovate.length + ' articoli';
  renderCommissioni(commissioniVisibili);
}

function tornaLogin() {
  document.getElementById('risultati-box').style.display = 'none';
  document.getElementById('login-box').style.display = 'block';
  document.getElementById('codice-input').value = '';
  commissioniVisibili = [];
}

// Permette di premere Invio nel campo codice
document.addEventListener('DOMContentLoaded', function() {
  const inp = document.getElementById('codice-input');
  if (inp) inp.addEventListener('keydown', function(e) {
    if (e.key === 'Enter') accediConCodice();
  });
});

// ── NAVIGAZIONE ──
function showPage(id, btn) {
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.bottom-btn').forEach(b => b.classList.remove('active'));
  document.getElementById('page-' + id).classList.add('active');
  btn.classList.add('active');
  window.scrollTo(0,0);
}

// ── COMMISSIONI ──
function getStatoClass(stato) {
  if (!stato) return '';
  const s = stato.toLowerCase();
  if (s.includes('lavorazione')) return 'stato-lavorazione';
  if (s.includes('pronto')) return 'stato-pronto';
  if (s.includes('pianificata')) return 'stato-pianificata';
  if (s.includes('consegnato')) return 'stato-consegnato';
  if (s.includes('giacenza')) return 'stato-pianificata';
  if (s.includes('ordinato')) return 'stato-lavorazione';
  if (s.includes('attesa')) return 'stato-attesa';
  return '';
}
function getBadgeClass(stato) {
  if (!stato) return '';
  const s = stato.toLowerCase();
  if (s.includes('lavorazione')) return 'badge-lavorazione';
  if (s.includes('pronto')) return 'badge-pronto';
  if (s.includes('pianificata')) return 'badge-pianificata';
  if (s.includes('consegnato')) return 'badge-consegnato';
  if (s.includes('giacenza')) return 'badge-pianificata';
  if (s.includes('ordinato')) return 'badge-lavorazione';
  if (s.includes('attesa')) return 'badge-attesa';
  return '';
}

function renderCommissioni(data) {
  const list = document.getElementById('commissioni-list');
  if (!data.length) {
    list.innerHTML = `<div class="empty-state"><div class="empty-icon">&#128237;</div><div class="empty-title">Nessuna commissione trovata</div><div class="empty-text">Prova con un altro codice</div></div>`;
    return;
  }
  list.innerHTML = data.map((c,i) => {
    const stato = c.stato || c['Status'] || c['Stato Ordine'] || '—';
    const desc = c.descrizione || c['Descrizione'] || c.note || '—';
    const dataConsegna = c.data_consegna || c['Data consegna'] || '';
    const dataOrdine = c.data_ordine || c['Data commissione'] || '';
    // Tronca la descrizione se troppo lunga
    const descBreve = desc.length > 80 ? desc.substring(0, 80) + '…' : desc;
    return `
    <div class="comm-card ${getStatoClass(stato)}" onclick="openModal(${i})">
      <div class="comm-top">
        <span class="comm-id">${dataOrdine ? '📅 ' + dataOrdine : ''}</span>
        <span class="stato-badge ${getBadgeClass(stato)}">${stato}</span>
      </div>
      <div class="comm-name" style="font-size:14px;font-weight:500;margin-top:4px">${descBreve}</div>
      <div class="comm-meta" style="margin-top:6px">
        ${dataConsegna ? `<span>🚚 Consegna: ${dataConsegna}</span>` : ''}
      </div>
    </div>`;
  }).join('');
}

function getSteps(stato) {
  const steps = [
    { name: 'Ordine ricevuto', desc: 'Commissione registrata nel sistema' },
    { name: 'In lavorazione', desc: 'Prodotto in produzione o in arrivo' },
    { name: 'Pronto', desc: 'Prodotto disponibile in magazzino' },
    { name: 'Consegna pianificata', desc: 'Data di consegna confermata' },
    { name: 'Consegnato', desc: 'Consegna completata con successo' },
  ];
  let activeIdx = 1;
  if (stato && stato.includes('Pronto')) activeIdx = 2;
  else if (stato && stato.includes('Pianificata')) activeIdx = 3;
  else if (stato && stato.includes('Consegnato')) activeIdx = 4;
  else if (stato && stato.includes('attesa')) activeIdx = 1;
  return { steps, activeIdx };
}

function openModal(idx) {
  const c = commissioniVisibili[idx];
  const id = c.codice || c['Codice'] || '—';
  const nome = c.descrizione || c['Descrizione'] || '—';
  const stato = c.stato || c['Status'] || c['Stato Ordine'] || '—';
  const dataOrdine = c.data_ordine || c['Data commissione'] || '—';
  const dataConsegna = c.data_consegna || c['Data consegna'] || 'Da definire';
  const arredatore = c.arredatore || c['Arredatore'] || '';
  const note = '';
  const { steps, activeIdx } = getSteps(stato);

  document.getElementById('modal-body').innerHTML = `
    <div class="modal-title" style="font-size:16px;line-height:1.4">${nome}</div>
    <div class="modal-id">Codice: ${id}</div>
    <div class="modal-row"><span class="modal-label">Stato</span><span class="modal-value"><span class="stato-badge ${getBadgeClass(stato)}">${stato}</span></span></div>
    <div class="modal-row"><span class="modal-label">Data ordine</span><span class="modal-value">${dataOrdine}</span></div>
    <div class="modal-row"><span class="modal-label">Consegna prevista</span><span class="modal-value">${dataConsegna}</span></div>
    <div class="modal-row"><span class="modal-label">Arredatore</span><span class="modal-value">${arredatore}</span></div>
    ${note ? `<div class="modal-row"><span class="modal-label">Note</span><span class="modal-value">${note}</span></div>` : ''}
    <div style="margin-top:20px;margin-bottom:4px;font-size:12px;font-weight:600;color:var(--gray);text-transform:uppercase;letter-spacing:0.5px">Piano di avanzamento</div>
    <div class="timeline">
      ${steps.map((s,i) => `
        <div class="timeline-step">
          <div class="timeline-left">
            <div class="timeline-dot ${i < activeIdx ? 'done' : i === activeIdx ? 'active' : ''}">${i < activeIdx ? '✓' : i+1}</div>
            ${i < steps.length-1 ? `<div class="timeline-line ${i < activeIdx ? 'done' : ''}"></div>` : ''}
          </div>
          <div class="timeline-content">
            <div class="timeline-step-name" style="color:${i === activeIdx ? 'var(--red)' : i < activeIdx ? 'var(--gray)' : 'var(--black)'}">${s.name}</div>
            <div class="timeline-step-desc">${s.desc}</div>
          </div>
        </div>
      `).join('')}
    </div>
  `;
  document.getElementById('modal-overlay').classList.add('open');
}

function closeModal(e) {
  if (!e || e.target === document.getElementById('modal-overlay') || !e.target) {
    document.getElementById('modal-overlay').classList.remove('open');
  }
}

// ── ARREDATORI ──
function renderArredatori(data) {
  const list = document.getElementById('arredatori-list');
  list.innerHTML = data.map(a => {
    const nome = `${a.nome || a['Nome'] || ''} ${a.cognome || a['Cognome'] || ''}`.trim();
    const iniziali = nome.split(' ').map(n => n[0]).join('').substring(0,2).toUpperCase();
    const negozio = a.negozio || a['Punto Vendita'] || '';
    const tel = (a.telefono || a['Telefono Diretto'] || a['WhatsApp'] || '').replace(/\s/g,'');
    const email = a.email || a['Email'] || '';
    return `
      <div class="arreda-card">
        <div class="arreda-avatar">${iniziali}</div>
        <div class="arreda-info">
          <div class="arreda-name">${nome}</div>
          <div class="arreda-store">📍 ${negozio}</div>
        </div>
        <div class="arreda-actions">
          ${tel ? `<a class="arreda-btn btn-wa" href="https://wa.me/39${tel}" title="WhatsApp">💬</a>` : ''}
          ${tel ? `<a class="arreda-btn btn-ph" href="tel:+39${tel}" title="Chiama">📞</a>` : ''}
        </div>
      </div>
    `;
  }).join('');
}

// ── ASSISTENZA ──
function inviaAssistenza() {
  const id = document.getElementById('ass-id').value.trim();
  const nome = document.getElementById('ass-nome').value.trim();
  const tipo = document.getElementById('ass-tipo').value;
  const desc = document.getElementById('ass-desc').value.trim();
  if (!nome || !tipo || !desc) { alert('Compila tutti i campi obbligatori'); return; }
  // In produzione qui invieresti i dati al Google Sheet via Apps Script
  document.getElementById('success-msg').style.display = 'block';
  document.getElementById('ass-id').value = '';
  document.getElementById('ass-nome').value = '';
  document.getElementById('ass-tipo').value = '';
  document.getElementById('ass-desc').value = '';
  setTimeout(() => { document.getElementById('success-msg').style.display = 'none'; }, 4000);
}

// ── CARICAMENTO DATI ──
function loadData() {
  allCommissioni = DEMO_COMMISSIONI;
  // Non renderizziamo commissioni all'avvio — aspettiamo il codice sito
  renderArredatori(DEMO_ARREDATORI);

  /* CODICE PER GOOGLE SHEET REALE (decommenta quando pronto):
  try {
    const urlComm = `https://docs.google.com/spreadsheets/d/${SHEET_ID}/gviz/tq?tqx=out:json&sheet=${COMMISSIONI_SHEET}`;
    const resComm = await fetch(urlComm);
    const textComm = await resComm.text();
    const jsonComm = JSON.parse(textComm.substring(47).slice(0,-2));
    const cols = jsonComm.table.cols.map(c => c.label);
    allCommissioni = jsonComm.table.rows.map(r => {
      const obj = {};
      r.c.forEach((cell, i) => { obj[cols[i]] = cell ? cell.v : ''; });
      return obj;
    }).filter(r => r['Visibile al Cliente'] === 'SI');
    renderCommissioni(allCommissioni);

    const urlArr = `https://docs.google.com/spreadsheets/d/${SHEET_ID}/gviz/tq?tqx=out:json&sheet=${ARREDATORI_SHEET}`;
    const resArr = await fetch(urlArr);
    const textArr = await resArr.text();
    const jsonArr = JSON.parse(textArr.substring(47).slice(0,-2));
    const colsArr = jsonArr.table.cols.map(c => c.label);
      const arredatori = jsonArr.table.rows.map(r => {
      const obj = {};
      r.c.forEach((cell, i) => { obj[colsArr[i]] = cell ? cell.v : ''; });
      return obj;
    });
    renderArredatori(arredatori);
  } catch(e) {
    console.error('Errore caricamento dati:', e);
    // In caso di errore, usa i dati demo
    allCommissioni = DEMO_COMMISSIONI;
    renderCommissioni(allCommissioni);
    renderArredatori(DEMO_ARREDATORI);
  }
  */
}

// Avvia al caricamento della pagina
document.addEventListener('DOMContentLoaded', loadData);
</script>
</body>
</html>
