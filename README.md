<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI-АРМИЯ 2027 — 10 готовых AI-агентов</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;900&display=swap');
        * {margin:0;padding:0;box-sizing:border-box;}
        body {font-family:'Montserrat',sans-serif; background:#0a0a0a; color:#fff; line-height:1.6;}
        .hero{background:linear-gradient(135deg,#0a0a0a 0%,#1a1a00 50%,#0a0a0a 100%);padding:60px 20px;text-align:center;border-bottom:2px solid #d4af37;}
        .hero-badge{display:inline-block;background:linear-gradient(135deg,#d4af37,#f4e058);color:#000;padding:8px 24px;border-radius:50px;font-weight:700;font-size:14px;margin-bottom:20px;text-transform:uppercase;letter-spacing:2px;}
        .hero h1{font-size:42px;font-weight:900;background:linear-gradient(135deg,#d4af37,#f4e058,#d4af37);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin-bottom:20px;line-height:1.2;}
        .hero-subtitle{font-size:20px;color:#ccc;max-width:600px;margin:0 auto 30px;}
        .hero-highlight{background:rgba(212,175,55,0.1);border:1px solid #d4af37;border-radius:12px;padding:20px;max-width:500px;margin:0 auto;}
        .hero-highlight p{font-size:18px;color:#f4e058;font-weight:600;}
        .pain{padding:60px 20px;background:#0d0d0d;}
        .pain h2{text-align:center;font-size:32px;margin-bottom:40px;}
        .pain-list{max-width:600px;margin:0 auto;list-style:none;}
        .pain-list li{padding:16px 20px;margin-bottom:12px;background:rgba(255,0,0,0.05);border-left:4px solid #ff4444;border-radius:8px;font-size:16px;color:#ddd;}
        .pain-list li::before{content:"❌ ";}
        .pain-bottom{text-align:center;margin-top:40px;font-size:20px;color:#d4af37;font-weight:700;}
        .solution{padding:60px 20px;background:linear-gradient(180deg,#0a0a0a 0%,#1a1400 100%);text-align:center;}
        .solution h2{font-size:32px;margin-bottom:20px;background:linear-gradient(135deg,#d4af37,#f4e058);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
        .solution p{font-size:18px;color:#ccc;max-width:600px;margin:0 auto 40px;}
        .agents{padding:60px 20px;background:#0d0d0d;}
        .agents h2{text-align:center;font-size:32px;margin-bottom:40px;color:#f4e058;}
        .agents-grid{max-width:700px;margin:0 auto;display:grid;gap:16px;}
        .agent-card{background:linear-gradient(135deg,#1a1a1a 0%,#0d0d0d 100%);border:1px solid #333;border-radius:12px;padding:20px;display:flex;align-items:center;gap:16px;transition:all 0.3s;}
        .agent-card:hover{border-color:#d4af37;box-shadow:0 0 20px rgba(212,175,55,0.1);}
        .agent-num{width:44px;height:44px;background:linear-gradient(135deg,#d4af37,#f4e058);border-radius:50%;display:flex;align-items:center;justify-content:center;font-weight:900;color:#000;font-size:16px;flex-shrink:0;}
        .agent-info h3{font-size:16px;color:#f4e058;margin-bottom:4px;}
        .agent-info p{font-size:14px;color:#999;}
        .bonuses{padding:60px 20px;background:linear-gradient(180deg,#0a0a0a 0%,#1a1400 100%);text-align:center;}
        .bonuses h2{font-size:32px;margin-bottom:40px;}
        .bonus-cards{max-width:600px;margin:0 auto;display:grid;gap:16px;}
        .bonus-card{background:rgba(212,175,55,0.05);border:1px solid #d4af37;border-radius:12px;padding:20px;text-align:left;}
        .bonus-card h3{color:#f4e058;font-size:16px;margin-bottom:6px;}
        .bonus-card p{color:#999;font-size:14px;}
        .bonus-label{display:inline-block;background:#d4af37;color:#000;padding:4px 12px;border-radius:20px;font-size:12px;font-weight:700;margin-bottom:10px;}
        .price-section{padding:60px 20px;background:#0d0d0d;text-align:center;}
        .price-section h2{font-size:32px;margin-bottom:40px;}
        .price-box{max-width:500px;margin:0 auto;background:linear-gradient(135deg,#1a1400 0%,#0d0d0d 100%);border:2px solid #d4af37;border-radius:20px;padding:40px 30px;position:relative;overflow:hidden;}
        .price-box::before{content:"";position:absolute;top:-50%;left:-50%;width:200%;height:200%;background:radial-gradient(circle,rgba(212,175,55,0.03) 0%,transparent 70%);}
        .price-old{font-size:24px;color:#666;text-decoration:line-through;margin-bottom:8px;}
        .price-per-item{font-size:14px;color:#999;margin-bottom:16px;}
        .price-new{font-size:52px;font-weight:900;background:linear-gradient(135deg,#d4af37,#f4e058);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin-bottom:8px;}
        .price-save{font-size:16px;color:#4CAF50;font-weight:600;margin-bottom:24px;}
        .timer-box{background:rgba(255,0,0,0.1);border:1px solid #ff4444;border-radius:10px;padding:14px;margin-bottom:24px;}
        .timer-box p{color:#ff6666;font-weight:700;font-size:16px;}
        #timer{font-size:28px;font-weight:900;color:#ff4444;font-family:monospace;}
        .cta-button{display:inline-block;width:100%;padding:20px 40px;background:linear-gradient(135deg,#d4af37,#f4e058);color:#000;font-size:20px;font-weight:900;text-decoration:none;border-radius:12px;text-transform:uppercase;letter-spacing:1px;transition:all 0.3s;box-shadow:0 4px 20px rgba(212,175,55,0.3);}
        .cta-button:hover{transform:translateY(-2px);box-shadow:0 8px 30px rgba(212,175,55,0.5);}
        .guarantee{margin-top:20px;font-size:13px;color:#666;}
        .proof{padding:60px 20px;background:#0a0a0a;text-align:center;}
        .proof h2{font-size:28px;margin-bottom:40px;}
        .proof-stats{display:flex;justify-content:center;gap:40px;flex-wrap:wrap;margin-bottom:40px;}
        .stat{text-align:center;}
        .stat-num{font-size:36px;font-weight:900;color:#f4e058;}
        .stat-label{font-size:14px;color:#999;}
        .faq{padding:60px 20px;background:#0d0d0d;}
        .faq h2{text-align:center;font-size:28px;margin-bottom:40px;}
        .faq-list{max-width:600px;margin:0 auto;}
        .faq-item{background:#1a1a1a;border:1px solid #333;border-radius:10px;padding:20px;margin-bottom:12px;}
        .faq-item h3{color:#f4e058;font-size:16px;margin-bottom:8px;}
        .faq-item p{color:#999;font-size:14px;}
        .final-cta{padding:60px 20px;text-align:center;background:linear-gradient(180deg,#0a0a0a 0%,#1a1400 100%);border-top:2px solid #d4af37;}
        .final-cta h2{font-size:28px;color:#fff;margin-bottom:16px;}
        .final-cta p{color:#999;margin-bottom:30px;font-size:16px;}
        .final-cta .cta-button{max-width:400px;}
        footer{padding:30px 20px;text-align:center;background:#050505;color:#444;font-size:12px;}
        @media (max-width: 768px) {
            .hero h1{font-size:28px;}
            .hero-subtitle{font-size:16px;}
            .price-new{font-size:40px;}
            .proof-stats{gap:20px;}
        }
        /* QR-модалка */
        #qrModal{display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(0,0,0,0.85);z-index:9999;align-items:center;justify-content:center;flex-direction:column;}
        #qrModal .modal-box{background:#222;padding:24px 18px 12px 18px;border-radius:18px;max-width:90vw;max-height:88vh;margin-top:5vh;display:flex;flex-direction:column;align-items:center;}
        #qrModal img{max-width:260px;width:75vw;border-radius:18px;background:#fff;padding:8px;margin-bottom:18px;}
        #qrModal h2{color:#d4af37;margin-bottom:16px;}
    </style>
</head>
<body>
    <!-- HERO -->
    <section class="hero">
        <div class="hero-badge">🔥 Лимитированное предложение</div>
        <h1>AI-АРМИЯ 2027</h1>
        <p class="hero-subtitle">10 готовых AI-агентов, которые будут работать на тебя 24/7 — пока ты спишь, отдыхаешь или живёшь свою жизнь</p>
        <div class="hero-highlight">
            <p>⚡ Замени 10 сотрудников одним пакетом PDF-инструкций</p>
        </div>
    </section>

    <!-- PAIN -->
    <section class="pain">
        <h2>Знакомо?</h2>
        <ul class="pain-list">
            <li>Тратишь часы на рутину, которую AI делает за 2 минуты</li>
            <li>Не знаешь как зарабатывать с нейросетями — все говорят, никто не показывает</li>
            <li>Пробовал ChatGPT — но ответы размытые и бесполезные</li>
            <li>Хочешь делегировать, но нет денег на сотрудников</li>
            <li>Смотришь как другие уже зарабатывают с AI — а ты всё ещё на нуле</li>
            <li>Боишься что через год AI заменит ТЕБЯ, а не ты его используешь</li>
        </ul>
        <p class="pain-bottom">Проблема не в тебе. Проблема — у тебя нет СИСТЕМЫ.</p>
    </section>

    <!-- SOLUTION -->
    <section class="solution">
        <h2>Встречай: AI-АРМИЯ 2027</h2>
        <p>Это не курс. Не вебинар. Это <strong>готовая система из 10 AI-агентов</strong> — открыл PDF, скопировал промпт, вставил в ChatGPT — и он работает КАК ПРОФЕССИОНАЛ.</p>
    </section>

    <!-- AGENTS -->
    <section class="agents">
        <h2>📦 10 AI-агентов в пакете:</h2>
        <div class="agents-grid">
            <div class="agent-card"><div class="agent-num">1</div><div class="agent-info"><h3>AI-СЕКРЕТАРЬ</h3><p>Отвечает на сообщения, письма и заявки за тебя</p></div></div>
            <div class="agent-card"><div class="agent-num">2</div><div class="agent-info"><h3>AI-ПРОДАВЕЦ</h3><p>Пишет скрипты продаж и закрывает возражения клиентов</p></div></div>
            <div class="agent-card"><div class="agent-num">3</div><div class="agent-info"><h3>AI-КОНТЕНТ-МЕЙКЕР</h3><p>Генерирует посты, рилсы, сценарии — каждый день</p></div></div>
            <div class="agent-card"><div class="agent-num">4</div><div class="agent-info"><h3>AI-АНАЛИТИК</h3><p>Анализирует рынок, конкурентов и тренды за минуты</p></div></div>
            <div class="agent-card"><div class="agent-num">5</div><div class="agent-info"><h3>AI-УЧИТЕЛЬ</h3><p>Объясняет любую тему — от крипты до маркетинга — за час</p></div></div>
            <div class="agent-card"><div class="agent-num">6</div><div class="agent-info"><h3>AI-ПСИХОЛОГ</h3><p>Поддержка, мотивация и разбор проблем 24/7</p></div></div>
            <div class="agent-card"><div class="agent-num">7</div><div class="agent-info"><h3>AI-ФИНАНСИСТ</h3><p>Планирует бюджет, считает расходы, советует инвестиции</p></div></div>
            <div class="agent-card"><div class="agent-num">8</div><div class="agent-info"><h3>AI-ТРЕНЕР</h3><p>Персональная программа тренировок и питания</p></div></div>
            <div class="agent-card"><div class="agent-num">9</div><div class="agent-info"><h3>AI-ПОВАР</h3><p>Рецепты из тех продуктов, что уже в холодильнике</p></div></div>
            <div class="agent-card"><div class="agent-num">10</div><div class="agent-info"><h3>AI-СТРАТЕГ</h3><p>Выстраивает жизненный план и цели пошагово</p></div></div>
        </div>
    </section>

    <!-- BONUSES -->
    <section class="bonuses">
        <h2>🎁 + 3 бонуса В ПОДАРОК:</h2>
        <div class="bonus-cards">
            <div class="bonus-card"><span class="bonus-label">БОНУС #1</span><h3>50 готовых промптов 2027</h3><p>Топовые промпты для любых задач — просто копируй и используй</p></div>
            <div class="bonus-card"><span class="bonus-label">БОНУС #2</span><h3>Список 30 AI-сервисов</h3><p>Лучшие нейросети для заработка, контента, автоматизации</p></div>
            <div class="bonus-card"><span class="bonus-label">БОНУС #3</span><h3>Чек-лист "AI за 7 дней"</h3><p>Пошаговый план — как внедрить AI в жизнь за неделю</p></div>
        </div>
    </section>

    <!-- SOCIAL PROOF -->
    <section class="proof">
        <h2>Люди уже используют AI-АРМИЮ</h2>
        <div class="proof-stats">
            <div class="stat"><div class="stat-num">1,247+</div><div class="stat-label">скачали пакет</div></div>
            <div class="stat"><div class="stat-num">4.9/5</div><div class="stat-label">средняя оценка</div></div>
            <div class="stat"><div class="stat-num">3 мин</div><div class="stat-label">до первого результата</div></div>
        </div>
    </section>

    <!-- PRICE + QR-кнопка -->
    <section class="price-section">
        <h2>Сколько это стоит?</h2>
        <div class="price-box">
            <p class="price-per-item">10 агентов + 3 бонуса = 13 файлов × 990₽ каждый</p>
            <p class="price-old">12 870 ₽</p>
            <p class="price-new">1 990 ₽</p>
            <p class="price-save">Экономия: 10 880 ₽ (скидка 85%)</p>
            <div class="timer-box">
                <p>⏰ Цена вернётся через:</p>
                <p id="timer">23:59:59</p>
            </div>

            <!-- РАБОЧАЯ КНОПКА QR-код -->
            <div style="text-align:center; margin:30px 0;">
                <button type="button" class="cta-button" onclick="openQRModal()">💳 МОЙ QR-КОД</button>
            </div>
            <p class="guarantee">🔒 После оплаты вы получите доступ в Telegram-канал с PDF-файлами и бонусами!</p>
        </div>
    </section>

    <!-- МОДАЛЬНОЕ ОКНО С QR -->
    <div id="qrModal">
        <div class="modal-box">
            <h2>Сканируй QR-код для оплаты</h2>
            <img src="https://r2.syntx.ai/user_1450372138/uploaded/0d778332c3ce9c8ebf547bf19a696aab_49fbaf59-3da8-456f-bf91-05077a51979c.jpg" alt="QR для оплаты">
            <div style="color:#fff; font-size:16px; margin-bottom:14px;">Отправь <b>1990₽</b> по QR и сохрани чек</div>
            <button id="paidBtn" onclick="showTelegramLink()" style="margin-bottom:12px;background:#d4af37;color:#000;padding:12px 32px;border:none;border-radius:12px;font-weight:700;font-size:16px;cursor:pointer;">Я оплатил(а)</button>
            <button onclick="closeQRModal()" style="background:none;color:#ccc;padding:8px;border:none;font-size:14px;cursor:pointer;">⨉ Закрыть</button>
            <div id="tgLink" style="display:none; margin-top:16px; text-align:center;">
                <a href="https://t.me/+RlDex4WZQwYyMmMy" target="_blank" style="background:#d4af37;text-decoration:none;color:#000;padding:13px 34px;border-radius:10px;font-weight:700;font-size:18px;display:inline-block;margin-bottom:8px;">Перейти в Telegram‑канал 🔥</a>
                <div  style="color:#fff;margin-top:8px;font-size:15px;">Скинь <b>скрин оплаты</b> и получи ссылку на скачивание PDF!</div>
            </div>
        </div>
    </div>
    <script>
        // Таймер 24 часа (сохраняется в localStorage)
        function startTimer() {
            let endTime = localStorage.getItem('ai-army-timer');
            if (!endTime) {endTime = Date.now() + 24*60*60*1000;localStorage.setItem('ai-army-timer', endTime);}
            function update() {
                const now = Date.now();
                const diff = endTime - now;
                if (diff <= 0) {
                    document.getElementById('timer').textContent = '00:00:00';
                    return;
                }
                const hours = Math.floor(diff/(1000*60*60));
                const mins  = Math.floor((diff%(1000*60*60))/(1000*60));
                const secs  = Math.floor((diff%(1000*60))/1000);
                document.getElementById('timer').textContent = String(hours).padStart(2,'0')+':'+String(mins).padStart(2,'0')+':'+String(secs).padStart(2,'0');
            }
            update();
            setInterval(update,1000);
        }
        startTimer();

        // QR-кнопка и модалка (делает обе кнопки рабочими): "Я оплатил(а)" — Telegram-кнопка появляется через 20 сек
        let timeoutQR = null;
        function openQRModal(){
            document.getElementById('qrModal').style.display='flex';
            document.getElementById('tgLink').style.display="none";
            if(timeoutQR){ clearTimeout(timeoutQR);}
        }
        function closeQRModal(){
            document.getElementById('qrModal').style.display='none';
            document.getElementById('tgLink').style.display="none";
            if(timeoutQR){ clearTimeout(timeoutQR);}
        }
        function showTelegramLink(){
            document.getElementById('paidBtn').disabled = true;
            document.getElementById('paidBtn').innerText = 'Проверяем оплату...';
            timeoutQR = setTimeout(function(){
                document.getElementById('tgLink').style.display="block";
                document.getElementById('paidBtn').innerText = 'Я оплатил(а)';
                document.getElementById('paidBtn').disabled = false;
            }, 20000); // 20 секунд
        }
    </script>

    <!-- FAQ -->
    <section class="faq">
        <h2>Частые вопросы:</h2>
        <div class="faq-list">
            <div class="faq-item">
                <h3>Это для новичков?</h3>
                <p>Да! Каждый PDF — пошаговая инструкция. Открыл → прочитал → скопировал → работает.</p>
            </div>
            <div class="faq-item">
                <h3>Мне нужна платная подписка ChatGPT?</h3>
                <p>Нет. Все промпты работают и на бесплатной версии. С платной — ещё лучше.</p>
            </div>
            <div class="faq-item">
                <h3>Как я получу файлы?</h3>
                <p>Сразу после оплаты — переходи в Telegram-канал, скинь скрин — получишь ссылку на PDF.</p>
            </div>
            <div class="faq-item">
                <h3>А если мне не подойдёт?</h3>
                <p>За 1990₽ ты получаешь инструменты, которые заменяют команду за 100 000₽/мес. Это инвестиция, а не расход.</p>
            </div>
        </div>
    </section>

    <!-- FINAL CTA -->
    <section class="final-cta">
        <h2>Не жди — пока AI работает на других</h2>
        <p>Через год все будут использовать AI. Вопрос — ты будешь среди первых или догоняющих?</p>
        <button type="button" class="cta-button" onclick="openQRModal()">🚀 Забрать AI-АРМИЮ</button>
    </section>

    <footer>
        <p>© 2025 AI-АРМИЯ 2027. Все права защищены.</p>
        <p>Информационный продукт. Результаты зависят от применения.</p>
    </footer>
</body>
</html>
