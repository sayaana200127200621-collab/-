# -
пригласительный 
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Александра & Константин | Свадебное приглашение</title>
    <style>
        body { font-family: 'Georgia', serif; margin: 0; padding: 0; background: linear-gradient(to bottom, #f9f5f0, #e8d9c6); color: #4a4a4a; text-align: center; }
        .hero { background: url('your-hero-image.jpg') center/cover; height: 100vh; display: flex; flex-direction: column; justify-content: center; align-items: center; color: white; text-shadow: 2px 2px 4px rgba(0,0,0,0.5); }
        .hero h1 { font-size: 4em; margin: 0; }
        .hero p { font-size: 1.5em; }
        .timer { font-size: 2em; margin: 20px 0; }
        section { padding: 60px 20px; max-width: 800px; margin: auto; }
        .rsvp { background: rgba(255,255,255,0.9); border-radius: 20px; padding: 40px; box-shadow: 0 10px 30px rgba(0,0,0,0.1); }
        form { display: flex; flex-direction: column; gap: 15px; max-width: 400px; margin: auto; }
        input, select, button { padding: 15px; border: 1px solid #ddd; border-radius: 10px; font-size: 1em; }
        button { background: #d4a574; color: white; border: none; cursor: pointer; font-weight: bold; }
        button:hover { background: #b89c5f; }
        @media (max-width: 768px) { .hero h1 { font-size: 2.5em; } }
    </style>
</head>
<body>
    <div class="hero">
        <h1>Александра & Константин</h1>
        <p>Приглашаем на нашу свадьбу!</p>
        <div id="timer" class="timer"></div>
    </div>
    <section id="date">
        <h2>📅 15 июня 2026</h2>
        <p>Церемония: 16:00, Ресторан "Золотой Лотос", Москва</p>
    </section>
    <section id="program">
        <h2>🕒 Программа</h2>
        <ul style="text-align: left; max-width: 500px; margin: auto;">
            >16:00 — Регистрация</l/li>
            >17:00 — Торжественная церемония</l/li>
            >18:00 — Банкет и танцы</li>
        </ul>
    </section>
    <section class="rsvp">
        <h2>Подтвердите участие</h2>
        <form id="rsvpForm">
            <input type="text" placeholder="Ваше имя" required>
            <select required>
                <option>Приду</option>
                <option>Не смогу</option>
                <option>+1 гость</option>
            </select>
            <input type="email" placeholder="Email">
            <button type="submit">Отправить</button>
        </form>
    </section>
    <section id="dresscode">
        <h2>👗 Дресс-код</h2>
        <p>Элегантный casual: платья пастельных тонов, костюмы без галстуков.</p>
    </section>
    <script>
        // Таймер обратного отсчета (замените дату)
        const weddingDate = new Date('2026-06-15T16:00:00').getTime();
        const timer = document.getElementById('timer');
        const interval = setInterval(() => {
            const now = new Date().getTime();
            const distance = weddingDate - now;
            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            timer.innerHTML = `${days}д ${hours}ч ${minutes}м`;
            if (distance < 0) { clearInterval(interval); timer.innerHTML = 'Свадьба началась!'; }
        }, 60000);

        // Форма RSVP (отправка на email или webhook)
        document.getElementById('rsvpForm').addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Спасибо! Ваше подтверждение получено.'); // Замените на реальную отправку
        });
    </script>
</body>
</html>
