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
      align-items: flex-start;
      padding: 0.8rem;
    }

    .site-card {
      max-width: 100%;
      width: 100%;
      background: rgba(30, 28, 24, 0.92);
      backdrop-filter: blur(6px);
      -webkit-backdrop-filter: blur(6px);
      border-radius: 2rem;
      padding: 1.2rem 1rem;
      box-shadow: 0 25px 50px -8px rgba(0, 0, 0, 0.8), inset 0 1px 2px rgba(255, 215, 150, 0.2);
      border: 1px solid #6f6a5f;
      margin: 0 auto;
      overflow-x: hidden;
    }

    .header {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
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
      flex: 1 1 auto;
      min-width: 0;
    }

    .header-left .icon-big {
      font-size: 1.8rem;
      color: #d4c5ad;
      background: #3d3830;
      padding: 0.3rem 0.6rem;
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
      word-break: break-word;
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
      flex-shrink: 0;
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
    }

    .mission-statement i { color: #d4c5ad; font-size: 1.2rem; margin-right: 6px; }
    .mission-statement strong { color: #f0eadc; }

    .grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 0.8rem;
      margin: 1.2rem 0 1.5rem;
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

    .form-section {
      background: #2b2821;
      border-radius: 2rem;
      padding: 1.2rem 1rem 1.5rem;
      border: 1px solid #6a6355;
      box-shadow: inset 0 2px 8px #1d1b16;
    }

    .form-section h2 {
      color: #efe8d9;
      font-size: 1.3rem;
      font-weight: 500;
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 1rem;
    }

    .form-section h2 i { color: #b8a78b; font-size: 1.3rem; }

    .form-row {
      display: flex;
      flex-direction: column;
      gap: 0.8rem;
    }

    .form-group {
      display: flex;
      flex-direction: column;
      gap: 0.2rem;
    }

    .form-group label {
      color: #d3c9b6;
      font-weight: 500;
      font-size: 0.8rem;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .form-group label i { color: #b3a181; width: 1rem; }

    .form-group input,
    .form-group select,
    .form-group textarea {
      background: #1f1c17;
      border: 1px solid #5a5346;
      border-radius: 60px;
      padding: 0.7rem 1rem;
      font-size: 0.9rem;
      color: #f0eadc;
      outline: none;
      transition: 0.2s;
      box-shadow: inset 0 2px 5px #0e0d0a;
      width: 100%;
    }

    .form-group input:focus,
    .form-group select:focus,
    .form-group textarea:focus {
      border-color: #b8a78b;
      background: #26221c;
      box-shadow: 0 0 0 2px rgba(184, 167, 139, 0.2);
    }

    .form-group textarea {
      border-radius: 1.2rem;
      resize: vertical;
      min-height: 80px;
    }

    .form-group select option { background: #2b2821; color: #f0eadc; }
    .form-group .hint {
      font-size: 0.7rem;
      color: #9e937e;
      margin-left: 4px;
      margin-top: 2px;
    }

    .submit-btn {
      background: #7e6f58;
      border: none;
      border-bottom: 3px solid #4d4133;
      padding: 0.8rem 1rem;
      border-radius: 60px;
      font-size: 1.1rem;
      font-weight: 600;
      color: #fefcf5;
      text-shadow: 0 2px 3px #1e1913;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      cursor: pointer;
      transition: 0.15s;
      background: linear-gradient(145deg, #897b64, #6d5f4b);
      box-shadow: 0 4px 0 #3f382d, 0 6px 12px #0b0a07;
      letter-spacing: 0.5px;
      width: 100%;
      margin-top: 0.8rem;
    }

    .submit-btn i { font-size: 1.2rem; color: #f7f0e0; }
    .submit-btn:active {
      transform: translateY(3px);
      border-bottom-width: 1px;
      box-shadow: 0 1px 0 #3f382d;
    }
    .submit-btn:disabled {
      opacity: 0.7;
      cursor: not-allowed;
      transform: translateY(2px);
      border-bottom-width: 2px;
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

    .feedback {
      margin-top: 1rem;
      display: none;
      background: #353027;
      border-radius: 1.5rem;
      padding: 0.8rem 1.2rem;
      border-left: 4px solid #b8a78b;
      color: #e6ddcc;
      font-size: 0.9rem;
    }
    .feedback.error { border-left-color: #c97a5a; }
    .feedback i { margin-right: 8px; }

    @media (max-width: 400px) {
      .site-card { padding: 0.8rem 0.6rem; }
      .header h1 { font-size: 1.2rem; }
      .header-left .icon-big { font-size: 1.4rem; padding: 0.2rem 0.4rem; }
      .header .tag { font-size: 0.6rem; padding: 0.2rem 0.6rem; }
      .mission-statement { font-size: 0.75rem; padding: 0.6rem 0.8rem; }
      .grid { gap: 0.5rem; }
      .sample-card .icon { font-size: 1.6rem; }
      .sample-card h3 { font-size: 0.75rem; }
      .sample-card p { font-size: 0.6rem; }
      .form-section h2 { font-size: 1.1rem; }
      .form-group input, .form-group select, .form-group textarea { font-size: 0.8rem; padding: 0.5rem 0.8rem; }
      .submit-btn { font-size: 0.95rem; padding: 0.6rem 0.8rem; }
    }

    @media (max-width: 360px) {
      .grid { grid-template-columns: 1fr 1fr; gap: 0.4rem; }
      .sample-card { padding: 0.5rem 0.3rem; }
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
  <div style="margin-bottom: 0.3rem;">
    <span style="color: #b9af9b; font-size: 0.8rem;">
      <i class="fas fa-cubes"></i> что закупаем:
    </span>
  </div>
  <div class="grid">
    <div class="sample-card"><div class="icon"><i class="fas fa-tshirt"></i></div><h3>Камуфляж «Мох»</h3><p>костюмы, куртки</p></div>
    <div class="sample-card"><div class="icon"><i class="fas fa-shoe-prints"></i></div><h3>Берцы</h3><p>высокие, усиленные</p></div>
    <div class="sample-card"><div class="icon"><i class="fas fa-vest"></i></div><h3>Зимние куртки</h3><p>утеплённые, мох</p></div>
    <div class="sample-card"><div class="icon"><i class="fas fa-backpack"></i></div><h3>Вещевые мешки</h3><p>60–120 л</p></div>
  </div>

  <!-- ФОРМА -->
  <div class="form-section">
    <h2><i class="fas fa-pen-to-square"></i> Оставить заявку</h2>

    <!-- FormSubmit — почта скрыта -->
    <form id="sellForm" action="https://formsubmit.co/egorgenich8@gmail.com" method="POST">
      <input type="hidden" name="_subject" value="Новая заявка на продажу снаряжения" />
      <input type="hidden" name="_captcha" value="false" />
      <input type="hidden" name="_template" value="table" />

      <div class="form-row">
        <div class="form-group">
          <label for="phone"><i class="fas fa-phone"></i> Телефон *</label>
          <input type="tel" id="phone" name="Телефон" placeholder="+7 912 345-67-89" required />
        </div>

        <div class="form-group">
          <label for="productType"><i class="fas fa-camouflage"></i> Что продаёте? *</label>
          <select id="productType" name="Товар" required>
            <option value="">-- выберите --</option>
            <option value="Камуфляж Мох">Камуфляж «Мох»</option>
            <option value="Берцы Мох">Берцы «Мох»</option>
            <option value="Зимняя куртка Мох">Зимняя куртка «Мох»</option>
            <option value="Вещевой мешок">Вещевой мешок</option>
            <option value="Другое">Другое снаряжение</option>
          </select>
        </div>

        <div class="form-group">
          <label for="quantity"><i class="fas fa-hashtag"></i> Количество</label>
          <input type="text" id="quantity" name="Количество" placeholder="10 комплектов" />
        </div>

        <div class="form-group">
          <label for="price"><i class="fas fa-tag"></i> Ваша цена</label>
          <input type="text" id="price" name="Цена" placeholder="4500 ₽" />
        </div>

        <div class="form-group">
          <label for="city"><i class="fas fa-location-dot"></i> Город</label>
          <input type="text" id="city" name="Город" placeholder="Москва" />
        </div>

        <div class="form-group">
          <label for="message"><i class="fas fa-comment"></i> Подробности</label>
          <textarea id="message" name="Детали" placeholder="Состояние, размеры, фото..." rows="3"></textarea>
          <span class="hint"><i class="fas fa-info-circle"></i> Чем подробнее — тем быстрее ответим</span>
        </div>
      </div>

      <button type="submit" class="submit-btn" id="submitBtn">
        <i class="fas fa-paper-plane"></i> Отправить заявку
      </button>
    </form>

    <div id="formFeedback" class="feedback">
      <i class="fas fa-check-circle"></i>
      <span id="feedbackMessage">Спасибо! Заявка отправлена.</span>
    </div>
  </div>

  <!-- ФУТЕР (без телефона) -->
  <div class="footer-note">
    <span class="badge"><i class="fas fa-envelope"></i> zakup@voen.ru</span>
    <span><i class="fas fa-store"></i> военторг</span>
  </div>
</div>

<script>
  document.getElementById('sellForm').addEventListener('submit', function(e) {
    const btn = document.getElementById('submitBtn');
    const feedbackDiv = document.getElementById('formFeedback');
    const feedbackMessage = document.getElementById('feedbackMessage');

    btn.innerHTML = '<i class="fas fa-spinner fa-pulse"></i> Отправка...';
    btn.disabled = true;

    feedbackMessage.textContent = '⏳ Отправляем заявку...';
    feedbackDiv.style.display = 'block';
    feedbackDiv.className = 'feedback';

    // Сообщение об ошибке, если что-то пошло не так
    setTimeout(function() {
      // Если форма всё ещё не отправлена (например, ошибка сети),
      // показываем краткое "Ошибка"
      if (btn.disabled) {
        feedbackMessage.textContent = 'Ошибка';
        feedbackDiv.className = 'feedback error';
        btn.innerHTML = '<i class="fas fa-paper-plane"></i> Отправить заявку';
        btn.disabled = false;
      }
    }, 8000);
  });
</script>

</body>
</html>
