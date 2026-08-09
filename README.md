<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Закупка снаряжения • Гуманитарная помощь СВО</title>
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
            padding: 1.5rem;
        }

        .site-card {
            max-width: 1100px;
            width: 100%;
            background: rgba(30, 28, 24, 0.88);
            backdrop-filter: blur(6px);
            -webkit-backdrop-filter: blur(6px);
            border-radius: 3.5rem 3.5rem 2.5rem 2.5rem;
            padding: 2.5rem 2rem;
            box-shadow: 0 25px 50px -8px rgba(0, 0, 0, 0.8), inset 0 1px 2px rgba(255, 215, 150, 0.2);
            border: 1px solid #6f6a5f;
        }

        .header {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2.2rem;
            border-bottom: 2px solid #7f7a6b;
            padding-bottom: 1.2rem;
            gap: 0.8rem 1.5rem;
        }

        .header-left {
            display: flex;
            align-items: center;
            gap: 16px;
        }

        .header-left .icon-big {
            font-size: 2.6rem;
            color: #d4c5ad;
            background: #3d3830;
            padding: 0.4rem 0.8rem;
            border-radius: 60px;
            border: 1px solid #8a7d66;
        }

        .header h1 {
            font-size: 2.2rem;
            font-weight: 600;
            letter-spacing: 1px;
            color: #ede7d9;
            text-shadow: 0 4px 10px #1f1b14;
            line-height: 1.2;
        }

        .header h1 .highlight {
            color: #d4c5ad;
            background: #3d3830;
            padding: 0 0.6rem;
            border-radius: 40px;
            font-weight: 500;
            border: 1px solid #6a6355;
        }

        .header .tag {
            background: #4f4a3d;
            padding: 0.6rem 1.8rem;
            border-radius: 60px;
            color: #f0eadc;
            font-weight: 500;
            border: 1px solid #a4967c;
            box-shadow: inset 0 1px 3px #a99b82;
            font-size: 1rem;
            display: flex;
            align-items: center;
            gap: 8px;
            white-space: nowrap;
        }

        .tag i { color: #e6d5b8; font-size: 1.1rem; }
        .tag .heart { color: #e67e7e; }

        .mission-statement {
            background: #2d2922;
            border-radius: 2rem;
            padding: 1.2rem 2rem;
            margin-bottom: 2rem;
            border-left: 6px solid #d4c5ad;
            color: #d6cdbb;
            font-size: 1.05rem;
            line-height: 1.6;
            box-shadow: inset 0 2px 6px #1a1814;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 0.8rem 1.8rem;
        }

        .mission-statement i { color: #d4c5ad; font-size: 1.6rem; }
        .mission-statement strong { color: #f0eadc; }
        .mission-statement .badge-svo {
            background: #4d4133;
            padding: 0.2rem 1.2rem;
            border-radius: 60px;
            font-size: 0.9rem;
            border: 1px solid #8a7d66;
            color: #ede7d9;
            margin-left: auto;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem 1.2rem;
            margin: 2rem 0 2.5rem;
        }

        .sample-card {
            background: #37332c;
            background: linear-gradient(145deg, #3f3a32, #2f2b24);
            border-radius: 2rem;
            padding: 1.2rem 1rem 1.5rem;
            box-shadow: 0 10px 16px -6px #14120e, inset 0 -2px 0 #5d564a;
            border: 1px solid #625b4e;
            text-align: center;
            transition: 0.2s;
        }

        .sample-card:hover {
            border-color: #b8a78b;
            transform: translateY(-4px);
        }

        .sample-card .icon { font-size: 3rem; color: #d3c5ae; margin-bottom: 0.3rem; }
        .sample-card h3 { color: #f0eadc; font-size: 1.1rem; font-weight: 500; }
        .sample-card p { color: #b7aa93; font-size: 0.85rem; margin-top: 0.3rem; }

        .form-section {
            background: #2b2821;
            border-radius: 2.5rem;
            padding: 2rem 2rem 2.2rem;
            border: 1px solid #6a6355;
            box-shadow: inset 0 2px 8px #1d1b16;
            margin-top: 0.5rem;
        }

        .form-section h2 {
            color: #efe8d9;
            font-size: 1.8rem;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 14px;
            margin-bottom: 1.5rem;
        }

        .form-section h2 i { color: #b8a78b; font-size: 1.8rem; }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1.5rem 2rem;
        }

        .form-group {
            display: flex;
            flex-direction: column;
            gap: 0.3rem;
        }

        .form-group.full-width { grid-column: 1 / -1; }

        .form-group label {
            color: #d3c9b6;
            font-weight: 500;
            font-size: 0.95rem;
            letter-spacing: 0.3px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .form-group label i { color: #b3a181; width: 1.2rem; }

        .form-group input,
        .form-group select,
        .form-group textarea {
            background: #1f1c17;
            border: 1px solid #5a5346;
            border-radius: 60px;
            padding: 0.85rem 1.4rem;
            font-size: 1rem;
            color: #f0eadc;
            outline: none;
            transition: 0.2s;
            box-shadow: inset 0 2px 5px #0e0d0a;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            border-color: #b8a78b;
            background: #26221c;
            box-shadow: 0 0 0 3px rgba(184, 167, 139, 0.2);
        }

        .form-group textarea {
            border-radius: 1.5rem;
            resize: vertical;
            min-height: 110px;
        }

        .form-group select option { background: #2b2821; color: #f0eadc; }
        .form-group .hint {
            font-size: 0.8rem;
            color: #9e937e;
            margin-left: 8px;
            margin-top: 2px;
        }

        .submit-btn {
            background: #7e6f58;
            border: none;
            border-bottom: 4px solid #4d4133;
            padding: 1rem 2rem;
            border-radius: 60px;
            font-size: 1.4rem;
            font-weight: 600;
            color: #fefcf5;
            text-shadow: 0 2px 3px #1e1913;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 18px;
            cursor: pointer;
            transition: 0.15s;
            background: linear-gradient(145deg, #897b64, #6d5f4b);
            box-shadow: 0 6px 0 #3f382d, 0 8px 14px #0b0a07;
            letter-spacing: 0.8px;
            width: 100%;
            margin-top: 1.2rem;
        }

        .submit-btn i { font-size: 1.5rem; color: #f7f0e0; }
        .submit-btn:hover {
            background: #9d8d73;
            transform: translateY(1px);
            border-bottom-width: 3px;
            box-shadow: 0 3px 0 #3f382d, 0 10px 18px #0a0906;
        }
        .submit-btn:active {
            transform: translateY(5px);
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
            margin-top: 2.5rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            color: #b9af9b;
            border-top: 1px solid #524c40;
            padding-top: 1.8rem;
            gap: 1rem;
            font-size: 0.95rem;
        }

        .footer-note i { color: #b3a080; margin-right: 6px; }
        .footer-note .badge {
            background: #2b2821;
            padding: 0.4rem 1.5rem;
            border-radius: 60px;
            border: 1px solid #6e6657;
        }

        .feedback {
            margin-top: 1.5rem;
            display: none;
            background: #353027;
            border-radius: 2rem;
            padding: 1rem 1.8rem;
            border-left: 6px solid #b8a78b;
            color: #e6ddcc;
        }
        .feedback.error { border-left-color: #c97a5a; }
        .feedback i { margin-right: 12px; }

        @media (max-width: 750px) {
            .site-card { padding: 1.5rem 1rem; border-radius: 2.5rem; }
            .header h1 { font-size: 1.6rem; }
            .header .tag { font-size: 0.8rem; padding: 0.4rem 1rem; }
            .form-row { grid-template-columns: 1fr; gap: 1rem; }
            .form-group.full-width { grid-column: 1; }
            .mission-statement { font-size: 0.95rem; padding: 1rem 1.2rem; flex-direction: column; align-items: flex-start; }
            .mission-statement .badge-svo { margin-left: 0; }
            .grid { grid-template-columns: repeat(2, 1fr); gap: 1rem; }
        }

        @media (max-width: 480px) {
            .grid { grid-template-columns: 1fr 1fr; gap: 0.8rem; }
            .sample-card .icon { font-size: 2.4rem; }
            .sample-card h3 { font-size: 0.95rem; }
            .form-section { padding: 1.5rem 1.2rem; }
            .header-left .icon-big { font-size: 2rem; padding: 0.2rem 0.6rem; }
        }
    </style>
</head>
<body>
<div class="site-card">

    <div class="header">
        <div class="header-left">
            <span class="icon-big"><i class="fas fa-hand-holding-heart"></i></span>
            <h1><span class="highlight">Снаряжение</span> <span style="font-size: 0.9em;">для СВО</span></h1>
        </div>
        <div class="tag">
            <i class="fas fa-truck"></i> Покупаем <i class="fas fa-arrow-right" style="margin: 0 4px;"></i>
            <span><i class="fas fa-heart heart"></i> гуманитарная помощь</span>
        </div>
    </div>

    <div class="mission-statement">
        <i class="fas fa-bullseye"></i>
        <span><strong>Мы закупаем военное снаряжение</strong> по <strong>высоким ценам</strong> для передачи <strong>гуманитарной помощи</strong> в район СВО.</span>
        <span class="badge-svo"><i class="fas fa-flag"></i> #СВО #помощь</span>
    </div>

    <div style="margin-bottom: 0.2rem;">
        <span style="color: #b9af9b; font-size: 0.95rem; letter-spacing: 1px;">
            <i class="fas fa-cubes"></i> что закупаем:
        </span>
    </div>
    <div class="grid">
        <div class="sample-card"><div class="icon"><i class="fas fa-tshirt"></i></div><h3>Камуфляж «Мох»</h3><p>костюмы, куртки, штаны</p></div>
        <div class="sample-card"><div class="icon"><i class="fas fa-shoe-prints"></i></div><h3>Берцы</h3><p>высокие, усиленные</p></div>
        <div class="sample-card"><div class="icon"><i class="fas fa-vest"></i></div><h3>Зимние куртки</h3><p>утеплённые, мох</p></div>
        <div class="sample-card"><div class="icon"><i class="fas fa-backpack"></i></div><h3>Вещевые мешки</h3><p>60–120 л, камуфляж</p></div>
    </div>

    <div class="form-section" id="orderForm">
        <h2><i class="fas fa-pen-to-square"></i> Отправить заявку на продажу</h2>

        <form id="sellForm">
            <div class="form-row">
                <div class="form-group">
                    <label for="phone"><i class="fas fa-phone"></i> Телефон *</label>
                    <input type="tel" id="phone" name="phone" placeholder="+7 912 345-67-89" required />
                </div>

                <div class="form-group">
                    <label for="productType"><i class="fas fa-camouflage"></i> Что продаёте? *</label>
                    <select id="productType" name="productType" required>
                        <option value="">-- выберите --</option>
                        <option value="Камуфляж Мох">Камуфляж «Мох» (костюм/комплект)</option>
                        <option value="Берцы Мох">Берцы «Мох»</option>
                        <option value="Зимняя куртка Мох">Зимняя куртка «Мох»</option>
                        <option value="Вещевой мешок">Вещевой мешок (камуфляж)</option>
                        <option value="Другое">Другое снаряжение</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="quantity"><i class="fas fa-hashtag"></i> Количество / объём</label>
                    <input type="text" id="quantity" name="quantity" placeholder="10 комплектов, 50 пар..." />
                </div>

                <div class="form-group">
                    <label for="price"><i class="fas fa-tag"></i> Ваша цена (за шт/комплект)</label>
                    <input type="text" id="price" name="price" placeholder="например: 4500 ₽" />
                </div>

                <div class="form-group">
                    <label for="city"><i class="fas fa-location-dot"></i> Город / регион</label>
                    <input type="text" id="city" name="city" placeholder="Москва, Ростов..." />
                </div>

                <div class="form-group full-width">
                    <label for="message"><i class="fas fa-comment"></i> Подробности, состояние, фото (ссылка)</label>
                    <textarea id="message" name="message" placeholder="Опишите товар: состояние, размеры, комплектация, ссылка на фото и т.д."></textarea>
                    <span class="hint"><i class="fas fa-info-circle"></i> Чем подробнее, тем быстрее мы свяжемся с вами.</span>
                </div>
            </div>

            <button type="submit" class="submit-btn" id="submitBtn">
                <i class="fas fa-paper-plane"></i> Отправить заявку
            </button>
        </form>

        <div id="formFeedback" class="feedback">
            <i class="fas fa-check-circle"></i>
            <span id="feedbackMessage">Спасибо! Ваша заявка принята. Мы свяжемся с вами в ближайшее время.</span>
        </div>
    </div>

    <div class="footer-note">
        <span class="badge"><i class="fas fa-phone"></i> +7 (912) 345-67-89</span>
        <span><i class="fas fa-envelope"></i> zakup@voen.ru</span>
        <span><i class="fas fa-hand-holding-heart"></i> закупка для гуманитарной помощи</span>
    </div>
</div>

<!-- Подключаем EmailJS -->
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>

<script>
    (function() {
        // ===== НАСТРОЙКИ EMAILJS =====
        // Зарегистрируйтесь на https://www.emailjs.com/
        // Получите эти данные в личном кабинете
        const PUBLIC_KEY = 'ваш_публичный_ключ';    // ← Замените на ваш Public Key
        const SERVICE_ID = 'service_ваш_id';       // ← Замените на ваш Service ID
        const TEMPLATE_ID = 'template_ваш_id';     // ← Замените на ваш Template ID

        // Инициализируем EmailJS
        emailjs.init(PUBLIC_KEY);

        const form = document.getElementById('sellForm');
        const feedbackDiv = document.getElementById('formFeedback');
        const feedbackMessage = document.getElementById('feedbackMessage');
        const submitBtn = document.getElementById('submitBtn');

        function showFeedback(text, isSuccess = true) {
            feedbackMessage.textContent = text;
            feedbackDiv.style.display = 'block';
            feedbackDiv.className = 'feedback' + (isSuccess ? '' : ' error');
            feedbackDiv.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }

        form.addEventListener('submit', async function(e) {
            e.preventDefault();

            // Получаем данные
            const phone = document.getElementById('phone').value.trim();
            const productType = document.getElementById('productType').value;
            const quantity = document.getElementById('quantity').value.trim();
            const price = document.getElementById('price').value.trim();
            const city = document.getElementById('city').value.trim();
            const message = document.getElementById('message').value.trim();

            // Валидация
            if (!phone) {
                showFeedback('❌ Пожалуйста, укажите номер телефона.', false);
                return;
            }
            const phoneClean = phone.replace(/[^+\d]/g, '');
            if (phoneClean.length < 6) {
                showFeedback('❌ Введите корректный номер телефона (например, +7 912 345-67-89).', false);
                return;
            }

            if (!productType) {
                showFeedback('❌ Пожалуйста, выберите, что вы продаёте.', false);
                return;
            }

            // Блокируем кнопку
            const originalText = submitBtn.innerHTML;
            submitBtn.innerHTML = '<i class="fas fa-spinner fa-pulse"></i> Отправка...';
            submitBtn.disabled = true;

            try {
                // Подготавливаем данные для EmailJS
                const templateParams = {
                    phone: phone,
                    product: productType,
                    quantity: quantity || 'не указано',
                    price: price || 'не указана',
                    city: city || 'не указан',
                    message: message || 'без подробностей',
                    time: new Date().toLocaleString('ru-RU')
                };

                // Отправляем через EmailJS
                const response = await emailjs.send(SERVICE_ID, TEMPLATE_ID, templateParams);

                if (response.status === 200) {
                    showFeedback('✅ Спасибо! Ваша заявка успешно отправлена. Мы свяжемся с вами в ближайшее время.', true);
                    form.reset();
                } else {
                    throw new Error('Ошибка отправки: ' + response.text);
                }

            } catch (error) {
                console.error('Ошибка:', error);
                showFeedback('❌ Ошибка отправки: ' + error.message + '. Попробуйте позже или позвоните по телефону.', false);
            } finally {
                submitBtn.innerHTML = originalText;
                submitBtn.disabled = false;
            }
        });
    })();
</script>

</body>
</html>
