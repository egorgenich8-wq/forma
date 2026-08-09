<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>Закупка снаряжения • Военторг</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Roboto, system-ui, sans-serif;
    }

    body {
      background: #2d2a24;
      background-image: radial-gradient(circle at 20% 30%, #4a443b 0%, #1f1c17 100%);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 0.8rem;
    }

    .site-card {
      max-width: 100%;
      width: 100%;
      max-width: 500px;
      background: rgba(30, 28, 24, 0.92);
      backdrop-filter: blur(6px);
      -webkit-backdrop-filter: blur(6px);
      border-radius: 2rem;
      padding: 1.5rem 1.2rem;
      box-shadow: 0 25px 50px -8px rgba(0, 0, 0, 0.8), inset 0 1px 2px rgba(255, 215, 150, 0.2);
      border: 1px solid #6f6a5f;
      margin: 0 auto;
      overflow-x: hidden;
      text-align: center;
    }

    .header {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
      margin-bottom: 1.5rem;
      border-bottom: 2px solid #7f7a6b;
      padding-bottom: 0.8rem;
      gap: 0.5rem;
    }

    .header-left {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .header-left .icon-big {
      font-size: 2rem;
      color: #d4c5ad;
      background: #3d3830;
      padding: 0.3rem 0.7rem;
      border-radius: 60px;
      border: 1px solid #8a7d66;
      flex-shrink: 0;
    }

    .header h1 {
      font-size: 1.5rem;
      font-weight: 600;
      letter-spacing: 0.5px;
      color: #ede7d9;
      text-shadow: 0 4px 10px #1f1b14;
      line-height: 1.2;
    }

    .header h1 .highlight {
      color: #d4c5ad;
      background: #3d3830;
      padding: 0 0.4rem;
      border-radius: 40px;
      font-weight: 500;
      border: 1px solid #6a6355;
    }

    .header .tag {
      background: #4f4a3d;
      padding: 0.3rem 0.8rem;
      border-radius: 60px;
      color: #f0eadc;
      font-weight: 500;
      border: 1px solid #a4967c;
      font-size: 0.7rem;
      display: flex;
      align-items: center;
      gap: 4px;
      white-space: nowrap;
    }

    .tag i { color: #e6d5b8; font-size: 0.8rem; }

    .mission-statement {
      background: #2d2922;
      border-radius: 1.5rem;
      padding: 0.8rem 1.2rem;
      margin-bottom: 1.5rem;
      border-left: 4px solid #d4c5ad;
      color: #d6cdbb;
      font-size: 0.9rem;
      line-height: 1.5;
      box-shadow: inset 0 2px 6px #1a1814;
      text-align: left;
    }

    .mission-statement i { color: #d4c5ad; font-size: 1.2rem; margin-right: 6px; }
    .mission-statement strong { color: #f0eadc; }

    .grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 0.8rem;
      margin: 1.2rem 0 1.8rem;
    }

    .sample-card {
      background: #37332c;
      background: linear-gradient(145deg, #3f3a32, #2f2b24);
      border-radius: 1.5rem;
      padding: 0.8rem 0.5rem 1rem;
      box-shadow: 0 8px 12px -6px #14120e, inset 0 -2px 0 #5d564a;
      border: 1px solid #625b4e;
      text-align: center;
      transition: 0.2s;
    }

    .sample-card:active {
      transform: scale(0.97);
    }

    .sample-card .icon { font-size: 2rem; color: #d3c5ae; margin-bottom: 0.2rem; }
    .sample-card h3 { color: #f0eadc; font-size: 0.85rem; font-weight: 500; }
    .sample-card p { color: #b7aa93; font-size: 0.7rem; margin-top: 0.1rem; }

    /* БЛОК КНОПОК */
    .call-block {
      background: #2b2821;
      border-radius: 2rem;
      padding: 1.5rem 1.2rem;
      border: 1px solid #6a6355;
      box-shadow: inset 0 2px 8px #1d1b16;
      margin-bottom: 0.5rem;
    }

    .call-block .phone-number {
      font-size: 1.8rem;
      font-weight: 700;
      color: #f0eadc;
      letter-spacing: 1px;
      margin-bottom: 0.3rem;
    }

    .call-block .phone-number i {
      color: #b8a78b;
      margin-right: 10px;
    }

    .call-block .sub-text {
      color: #b9af9b;
      font-size: 0.85rem;
      margin-bottom: 1.2rem;
    }

    .btn-group {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }

    .btn-group .row {
      display: flex;
      gap: 0.8rem;
    }

    .btn-group .row .btn {
      flex: 1;
    }

    .btn {
      border: none;
      border-bottom: 3px solid #4d4133;
      padding: 0.9rem 1rem;
      border-radius: 60px;
      font-size: 1.1rem;
      font-weight: 600;
      color: #fefcf5;
      text-shadow: 0 2px 3px #1e1913;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      cursor: pointer;
      transition: 0.15s;
      box-shadow: 0 4px 0 #3f382d, 0 6px 12px #0b0a07;
      letter-spacing: 0.5px;
      width: 100%;
      text-decoration: none;
      background: linear-gradient(145deg, #897b64, #6d5f4b);
    }

    .btn:active {
      transform: translateY(3px);
      border-bottom-width: 1px;
      box-shadow: 0 1px 0 #3f382d;
    }

    .btn i { font-size: 1.3rem; }

    .btn-phone {
      background: linear-gradient(145deg, #3a7a5a, #2a5a40);
      border-bottom-color: #1a3a2a;
      box-shadow: 0 4px 0 #1a3a2a, 0 6px 12px #0b0a07;
    }

    .btn-phone:active {
      box-shadow: 0 1px 0 #1a3a2a;
    }

    .btn-whatsapp {
      background: linear-gradient(145deg, #25D366, #128C7E);
      border-bottom-color: #075E54;
      box-shadow: 0 4px 0 #075E54, 0 6px 12px #0b0a07;
    }

    .btn-whatsapp:active {
      box-shadow: 0 1px 0 #075E54;
    }

    .btn-whatsapp i {
      color: #fff;
    }

    .footer-note {
      margin-top: 1.5rem;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      align-items: center;
      color: #b9af9b;
      border-top: 1px solid #524c40;
      padding-top: 1rem;
      gap: 0.5rem 1.5rem;
      font-size: 0.75rem;
      text-align: center;
    }

    .footer-note i { color: #b3a080; margin-right: 4px; }
    .footer-note .badge {
      background: #2b2821;
      padding: 0.2rem 1rem;
      border-radius: 60px;
      border: 1px solid #6e6657;
    }

    @media (max-width: 400px) {
      .site-card { padding: 1rem 0.8rem; }
      .header h1 { font-size: 1.2rem; }
      .header-left .icon-big { font-size: 1.4rem; padding: 0.2rem 0.4rem; }
      .header .tag { font-size: 0.6rem; padding: 0.2rem 0.6rem; }
      .mission-statement { font-size: 0.75rem; padding: 0.6rem 0.8rem; }
      .grid { gap: 0.5rem; }
      .sample-card .icon { font-size: 1.6rem; }
      .sample-card h3 { font-size: 0.75rem; }
      .sample-card p { font-size: 0.6rem; }
      .call-block .phone-number { font-size: 1.4rem; }
      .btn { font-size: 0.95rem; padding: 0.7rem 0.8rem; }
      .btn i { font-size: 1.1rem; }
    }

    @media (max-width: 360px) {
      .grid { grid-template-columns: 1fr 1fr; gap: 0.4rem; }
      .sample-card { padding: 0.5rem 0.3rem; }
      .btn-group .row {
        flex-direction: column;
      }
    }
  </style>
</head>
<body>
<div class="site-card">

  <!-- ШАПКА -->
  <div class="header">
    <div class="header-left">
      <span class="icon-big"><i class="fas fa-store"></i></span>
      <h1><span class="highlight">Военторг</span> Закуп</h1>
    </div>
    <div class="tag">
      <i class="fas fa-truck"></i> Покупаем
    </div>
  </div>

  <!-- ОПИСАНИЕ -->
  <div class="mission-statement">
    <i class="fas fa-handshake"></i>
    <span><strong>Скупаем военное снаряжение</strong> для перепродажи в военторге. Работаем с частными лицами и организациями.</span>
  </div>

  <!-- ЧТО ЗАКУПАЕМ -->
  <div style="margin-bottom: 0.3rem; text-align: left;">
    <span style="color: #b9af9b; font-size: 0.8rem;">
      <i class="fas fa-cubes"></i> что закупаем:
    </span>
  </div>
  <div class="grid">
    <div class="sample-card"><div class="icon"><i class="fas fa-tshirt"></i></div><h3>Камуфляж «Мох»</h3><p>костюмы, куртки</p></div>
    <div class="sample-card"><div class="icon"><i class="fas fa-shoe-prints"></i></div><h3>Берцы</h3><p>высокие, усиленные</p></div>
    <div class="sample-card"><div class="icon"><i class="fas fa-vest"></i></div><h3>Зимние куртки «Мох»</h3><p>утеплённые</p></div>
    <div class="sample-card"><div class="icon"><i class="fas fa-backpack"></i></div><h3>Вещевые мешки</h3><p>60–120 л</p></div>
  </div>

  <!-- КНОПКИ ЗВОНОК + WHATSAPP -->
  <div class="call-block">
    <div class="phone-number">
      <i class="fas fa-phone"></i> +7 905 466-59-47
    </div>
    <div class="sub-text">
      <i class="fas fa-clock"></i> Звоните или пишите с 9:00 до 21:00
    </div>

    <div class="btn-group">
      <div class="row">
        <a href="tel:+79054665947" class="btn btn-phone">
          <i class="fas fa-phone-volume"></i> Позвонить
        </a>
      </div>
      <div class="row">
        <a href="https://wa.me/79054665947" target="_blank" class="btn btn-whatsapp">
          <i class="fab fa-whatsapp"></i> Написать в WhatsApp
        </a>
      </div>
    </div>
  </div>

  <!-- ФУТЕР -->
  <div class="footer-note">
    <span class="badge"><i class="fas fa-envelope"></i> zakup@voen.ru</span>
    <span><i class="fas fa-store"></i> военторг</span>
  </div>
</div>
</body>
</html>
