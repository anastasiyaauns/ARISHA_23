
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сказка о принцессе Арише</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,400;0,500;0,600;0,700;1,400;1,500;1,600&family=Marck+Script&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(180deg, #0d0618 0%, #1a0a2e 15%, #2d1b4e 40%, #4a2c6a 65%, #6b3d8a 85%, #8b5fa8 100%);
            min-height: 100vh;
            font-family: 'Cormorant Garamond', serif;
            color: #f0e6d3;
            overflow-x: hidden;
        }
        
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        
        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #fff;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }
        
        .shooting-star {
            position: absolute;
            width: 100px;
            height: 2px;
            background: linear-gradient(90deg, transparent, #fff, transparent);
            animation: shoot 4s linear infinite;
            opacity: 0;
        }
        
        @keyframes twinkle {
            0%, 100% { opacity: 0.2; }
            50% { opacity: 1; }
        }
        
        @keyframes shoot {
            0% { transform: translateX(-100px) translateY(0); opacity: 0; }
            10% { opacity: 1; }
            20% { transform: translateX(100vw) translateY(100px); opacity: 0; }
            100% { opacity: 0; }
        }
        
        .container {
            max-width: 820px;
            margin: 0 auto;
            padding: 60px 35px;
            position: relative;
            z-index: 1;
        }
        
        .book-cover {
            text-align: center;
            margin-bottom: 60px;
            padding: 50px 40px;
            background: rgba(255, 255, 255, 0.04);
            border-radius: 25px;
            border: 2px solid rgba(255, 215, 0, 0.3);
            box-shadow: 0 0 60px rgba(255, 215, 0, 0.08), inset 0 0 40px rgba(255, 215, 0, 0.02);
            position: relative;
            overflow: hidden;
        }
        
        .book-cover::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,215,0,0.05) 0%, transparent 70%);
            animation: glow 8s ease-in-out infinite;
        }
        
        @keyframes glow {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(180deg); }
        }
        
        .sun-icon {
            font-size: 70px;
            margin-bottom: 25px;
            display: block;
            animation: rotate 25s linear infinite;
            filter: drop-shadow(0 0 15px rgba(255, 215, 0, 0.6));
        }
        
        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }
        
        h1 {
            font-family: 'Marck Script', cursive;
            font-size: 4em;
            color: #ffd700;
            text-shadow: 0 0 30px rgba(255, 215, 0, 0.5);
            margin-bottom: 15px;
            position: relative;
        }
        
        .subtitle {
            font-size: 1.4em;
            color: #d4a5a5;
            font-style: italic;
            position: relative;
        }
        
        .dedication {
            margin-top: 25px;
            padding: 15px;
            background: rgba(255, 215, 0, 0.08);
            border-radius: 15px;
            font-style: italic;
            font-size: 1.1em;
            color: #e8c4a0;
            position: relative;
        }
        
        .chapter {
            margin: 50px 0;
            padding: 35px;
            background: rgba(255, 255, 255, 0.025);
            border-radius: 18px;
            border-left: 4px solid #ffd700;
            position: relative;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .chapter:hover {
            transform: translateX(5px);
            box-shadow: -5px 0 30px rgba(255, 215, 0, 0.1);
        }
        
        .chapter::before {
            content: '✦';
            position: absolute;
            top: -18px;
            left: 25px;
            color: #ffd700;
            font-size: 28px;
            background: #2d1b4e;
            padding: 0 12px;
        }
        
        h2 {
            font-family: 'Marck Script', cursive;
            font-size: 2.4em;
            color: #ffd700;
            margin-bottom: 25px;
            text-align: center;
            text-shadow: 0 0 15px rgba(255, 215, 0, 0.3);
        }
        
        h3 {
            font-family: 'Marck Script', cursive;
            font-size: 1.6em;
            color: #e8c4a0;
            margin: 25px 0 15px 0;
            text-align: center;
        }
        
        p {
            font-size: 1.22em;
            line-height: 2;
            margin-bottom: 20px;
            text-align: justify;
            text-indent: 35px;
        }
        
        .highlight {
            color: #ffd700;
            font-weight: 600;
        }
        
        .dialogue {
            font-style: italic;
            color: #e8c4c4;
            border-left: 3px solid #e8c4c4;
            padding-left: 25px;
            margin: 20px 0;
            font-size: 1.15em;
        }
        
        .dialogue-center {
            text-align: center;
            font-style: italic;
            color: #e8c4c4;
            margin: 20px 0;
            font-size: 1.15em;
            padding: 15px;
            background: rgba(232, 196, 196, 0.05);
            border-radius: 10px;
        }
        
        .magic-word {
            display: inline-block;
            background: linear-gradient(45deg, #ffd700, #ff6b6b, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 700;
            font-size: 1.15em;
            animation: shimmer 3s infinite;
        }
        
        @keyframes shimmer {
            0%, 100% { filter: brightness(1); }
            50% { filter: brightness(1.3); }
        }
        
        .divider {
            text-align: center;
            font-size: 2.2em;
            color: #ffd700;
            margin: 40px 0;
            opacity: 0.5;
            letter-spacing: 15px;
        }
        
        .ending {
            text-align: center;
            padding: 50px 40px;
            background: rgba(255, 215, 0, 0.08);
            border-radius: 25px;
            margin-top: 60px;
            border: 2px solid rgba(255, 215, 0, 0.35);
            position: relative;
            overflow: hidden;
        }
        
        .ending::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, rgba(255,215,0,0.1) 0%, transparent 70%);
        }
        
        .ending h2 {
            font-size: 2.8em;
            margin-bottom: 25px;
            position: relative;
        }
        
        .ending p {
            text-align: center;
            text-indent: 0;
            font-size: 1.35em;
            position: relative;
        }
        
        .heart {
            color: #ff6b6b;
            font-size: 1.8em;
            animation: pulse 1.5s infinite;
            display: inline-block;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.25); }
        }
        
        .date-badge {
            display: inline-block;
            background: rgba(255, 215, 0, 0.15);
            border: 1px solid rgba(255, 215, 0, 0.4);
            border-radius: 25px;
            padding: 6px 18px;
            font-size: 0.95em;
            color: #ffd700;
            margin: 5px;
            transition: all 0.3s ease;
        }
        
        .date-badge:hover {
            background: rgba(255, 215, 0, 0.25);
            transform: translateY(-2px);
        }
        
        .scroll-indicator {
            text-align: center;
            margin-top: 35px;
            font-size: 2.2em;
            animation: bounce 2.5s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(12px); }
        }
        
        .floating {
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-12px); }
        }
        
        .emoji-center {
            text-align: center;
            font-size: 2.5em;
            margin: 25px 0;
            letter-spacing: 10px;
        }
        
        .poem {
            text-align: center;
            font-style: italic;
            color: #e8c4a0;
            font-size: 1.15em;
            line-height: 2.2;
            margin: 25px 0;
            padding: 20px;
            background: rgba(255, 215, 0, 0.04);
            border-radius: 15px;
        }
        
        .memory-box {
            background: rgba(255, 255, 255, 0.03);
            border: 1px dashed rgba(255, 215, 0, 0.3);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
        }
        
        .memory-box p {
            text-indent: 0;
            text-align: center;
            margin-bottom: 10px;
        }
        
        .memory-box p:last-child {
            margin-bottom: 0;
        }
        
        .quote-mark {
            font-size: 3em;
            color: rgba(255, 215, 0, 0.3);
            line-height: 0.5;
            display: block;
            text-align: center;
            margin-bottom: 10px;
        }

        .pizza-oven {
            text-align: center;
            font-size: 4em;
            margin: 20px 0;
            position: relative;
        }
        
        .smoke {
            position: relative;
            display: inline-block;
        }
        
        .smoke::after {
            content: '💨';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 0.5em;
            animation: smoke-rise 2s ease-in-out infinite;
            opacity: 0;
        }
        
        @keyframes smoke-rise {
            0% { top: -10px; opacity: 0; }
            30% { opacity: 0.8; }
            100% { top: -50px; opacity: 0; }
        }
        
        .burnt-pizza {
            display: inline-block;
            animation: shake 0.5s ease-in-out infinite;
            filter: grayscale(0.3) sepia(0.2);
        }
        
        @keyframes shake {
            0%, 100% { transform: rotate(-2deg); }
            50% { transform: rotate(2deg); }
        }
        
        .dog-eating {
            font-size: 3em;
            text-align: center;
            margin: 20px 0;
            animation: munch 1s ease-in-out infinite;
        }
        
        @keyframes munch {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        
        .recipe-box {
            background: rgba(139, 69, 19, 0.15);
            border: 2px dashed rgba(255, 165, 0, 0.4);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            font-family: 'Marck Script', cursive;
            font-size: 1.3em;
            color: #f4a460;
            text-align: center;
        }
        
        .recipe-box p {
            text-indent: 0;
            text-align: center;
            margin-bottom: 8px;
            font-size: 1.1em;
        }
        
        .recipe-box p:last-child {
            margin-bottom: 0;
        }
        
        .timer {
            display: inline-block;
            background: rgba(255, 0, 0, 0.15);
            border: 2px solid rgba(255, 0, 0, 0.4);
            border-radius: 50%;
            width: 60px;
            height: 60px;
            line-height: 56px;
            text-align: center;
            font-size: 1.2em;
            color: #ff6b6b;
            font-weight: 700;
            animation: tick 1s ease-in-out infinite;
        }
        
        @keyframes tick {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }
        
        .oven-glow {
            text-align: center;
            font-size: 2em;
            margin: 15px 0;
            animation: oven-heat 2s ease-in-out infinite;
        }
        
        @keyframes oven-heat {
            0%, 100% { filter: brightness(1); }
            50% { filter: brightness(1.3) drop-shadow(0 0 10px rgba(255, 100, 0, 0.5)); }
        }

        /* === НОВЫЕ СТИЛИ ДЛЯ ФИНАЛЬНЫХ ГЛАВ === */
        .letter-box {
            background: rgba(255, 215, 0, 0.05);
            border: 1px solid rgba(255, 215, 0, 0.25);
            border-radius: 18px;
            padding: 30px 35px;
            margin: 30px 0;
            position: relative;
        }

        .letter-box::before {
            content: '✉';
            position: absolute;
            top: -16px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 22px;
            background: #2d1b4e;
            padding: 0 14px;
            color: #ffd700;
        }

        .letter-box p {
            text-indent: 0;
            text-align: left;
            font-style: italic;
            color: #e8d5b0;
            font-size: 1.2em;
            line-height: 2.1;
            margin-bottom: 12px;
        }

        .letter-box p:last-child {
            margin-bottom: 0;
        }

        .number-big {
            font-family: 'Marck Script', cursive;
            font-size: 5em;
            color: rgba(255, 215, 0, 0.15);
            display: block;
            text-align: center;
            line-height: 1;
            margin: 10px 0;
        }

        .years-counter {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin: 30px 0;
        }

        .year-item {
            text-align: center;
            background: rgba(255, 215, 0, 0.07);
            border: 1px solid rgba(255, 215, 0, 0.2);
            border-radius: 15px;
            padding: 15px 20px;
            min-width: 120px;
            transition: transform 0.3s ease;
        }

        .year-item:hover {
            transform: translateY(-5px);
        }

        .year-item .num {
            font-family: 'Marck Script', cursive;
            font-size: 2.8em;
            color: #ffd700;
            display: block;
        }

        .year-item .label {
            font-size: 0.9em;
            color: #d4a5a5;
            font-style: italic;
        }

        .wish-star {
            display: inline-block;
            font-size: 1.3em;
            animation: wish-pulse 2s ease-in-out infinite;
        }

        @keyframes wish-pulse {
            0%, 100% { transform: scale(1) rotate(0deg); opacity: 0.8; }
            50% { transform: scale(1.2) rotate(10deg); opacity: 1; }
        }

        .final-poem {
            text-align: center;
            font-style: italic;
            color: #e8c4a0;
            font-size: 1.25em;
            line-height: 2.5;
            margin: 30px 0;
            padding: 30px;
            background: rgba(255, 215, 0, 0.04);
            border: 1px dashed rgba(255, 215, 0, 0.2);
            border-radius: 20px;
            position: relative;
        }

        .final-poem::before,
        .final-poem::after {
            content: '🌟';
            position: absolute;
            font-size: 1.5em;
            top: 15px;
        }
        .final-poem::before { left: 20px; }
        .final-poem::after { right: 20px; }

        .confetti-line {
            text-align: center;
            font-size: 2em;
            margin: 20px 0;
            letter-spacing: 8px;
            animation: confetti-dance 3s ease-in-out infinite;
        }

        @keyframes confetti-dance {
            0%, 100% { letter-spacing: 8px; }
            50% { letter-spacing: 14px; }
        }

        .golden-rule {
            background: linear-gradient(135deg, rgba(255,215,0,0.12) 0%, rgba(255,100,100,0.08) 100%);
            border-radius: 18px;
            padding: 28px 35px;
            margin: 28px 0;
            text-align: center;
            border: 1px solid rgba(255, 215, 0, 0.3);
        }

        .golden-rule p {
            text-indent: 0;
            text-align: center;
            font-size: 1.3em;
            color: #ffd700;
            line-height: 1.8;
            margin: 0;
        }

        .signature {
            font-family: 'Marck Script', cursive;
            font-size: 2em;
            color: #ffd700;
            text-align: right;
            margin-top: 20px;
            opacity: 0.8;
        }

        .age-badge {
            display: inline-block;
            background: linear-gradient(135deg, rgba(255,215,0,0.2), rgba(255,100,100,0.15));
            border: 2px solid rgba(255, 215, 0, 0.5);
            border-radius: 50%;
            width: 90px;
            height: 90px;
            line-height: 86px;
            text-align: center;
            font-family: 'Marck Script', cursive;
            font-size: 2.5em;
            color: #ffd700;
            margin: 20px auto;
            display: block;
            animation: age-glow 3s ease-in-out infinite;
            box-shadow: 0 0 30px rgba(255,215,0,0.2);
        }

        @keyframes age-glow {
            0%, 100% { box-shadow: 0 0 20px rgba(255,215,0,0.2); }
            50% { box-shadow: 0 0 45px rgba(255,215,0,0.5); }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeIn 1s ease forwards;
        }

        @keyframes fadeIn {
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars"></div>
    
    <div class="container">
        <div class="book-cover">
            <span class="sun-icon">☀️</span>
            <h1>Сказка о принцессе Арише</h1>
            <p class="subtitle">История одной дружбы, которая пережила всё на свете</p>
            <div style="margin-top: 25px;">
                <span class="date-badge">28 апреля 2003</span>
                <span class="date-badge">Село Чля</span>
                <span class="date-badge">39-е царство</span>
                <span class="date-badge">Хабаровский край</span>
            </div>
            <div class="dedication">
                «Эта история — про девочку, которая родилась в маленьком селе,<br>
                но сделала чью-то жизнь бесконечно большой»
            </div>
        </div>
        
        <div class="scroll-indicator floating">📜</div>
        
        <!-- ГЛАВА 1 -->
        <div class="chapter">
            <h2>Глава первая: Как всё начиналось</h2>
            <p>
                <span class="highlight">Давным-давно</span>, так давно, что даже старейшины села Чля ещё помнили те времена молодыми, в далёком тридевятом царстве, где реки пели колыбельные зелёным полям, а берёзы шептали свои секреты ветру, случилось чудо. Не простое чудо — а такое, от которого мир становится чуть светлее, чуть теплее, чуть добрее.
            </p>
            <p>
                В одно прекрасное весеннее утро, когда солнце, словно золотой мячик, подпрыгнуло над горизонтом и улыбнулось земле своим самым лучезарным лучом, в маленьком домике на окраине села Чля раздался первый крик. Не громкий, не испуганный — а <span class="highlight">солнечный</span>. Такой, от которого хочется улыбнуться, даже если ты никогда раньше не улыбался.
            </p>
            <p>
                Родилась девочка. Не простая — <span class="highlight">белобрыса</span>, с волосами цвета спелой пшеницы, с глазами цвета <span class="highlight">изумрудных озёр</span>, в которых отражалось всё небо. Мать её, взглянув на дочь, сразу поняла: это имя должно быть таким же светлым, как она сама. И назвала её <span class="highlight">Аришей</span>.
            </p>
            <p>
                Ариша. Три слога, а сколько в них музыки! Словно кто-то переливал солнечные лучи в бокал и звенел ими. Это имя сразу стало самым прекрасным звуком во всём тридевятом царстве. Да что там — во всём Хабаровском крае.
            </p>
            <p>
                Но вот загадка: в ту же пору, под тем же небом, в соседнем домике жила другая девочка. <span class="highlight">Тёмненькая</span>, как ночка без луны, но с характером <span class="highlight">огненным, как закат</span>. Их мамы были подругами с незапамятных времён — с пелёнок, с первых шагов, с первых слов. Словно две сестры, разделённые судьбой, но соединённые душой.
            </p>
            <p>
                Так и повстречались <span class="highlight">принцесса и нищенка</span>. Только нищенка была совсем не нищей — у неё было богатство, которого не купишь за деньги: верность, смелость и сердце, готовое на всё ради друга. А принцесса была совсем не из замка — её корона была сплетена из соломинок, а троном служил пень под старым дубом.
            </p>
            <p>
                Они были просто две маленькие девочки из села Чля. Но суждено им было стать <span class="highlight">самыми близкими людьми на свете</span>. Не потому что так решили взрослые. Потому что так захотели их сердца.
            </p>
        </div>
        
        <div class="divider">✦ ✧ ✦</div>
        
        <!-- ГЛАВА 2 -->
        <div class="chapter">
            <h2>Глава вторая: Волшебные приключения</h2>
            
            <h3>🏠 Домик на четырёх деревьях</h3>
            <p>
                В детстве Ариша и её тёмненькая подруга жили так, словно мир был создан только для них двоих. Каждое утро начиналось с одного и того же вопроса: <span class="highlight">«Что интересного сегодня придумаем?»</span> И каждый день они находили ответ.
            </p>
            <p>
                Однажды они решили построить <span class="highlight">настоящий замок</span>. Не из подушек на диване — а настоящий, из досок и гвоздей, среди четырёх могучих деревьев на окраине села. Они тащили доски, которые нашли где-то в сарае, прибивали их к стволам, мазали грязью щели (это, по их мнению, было цементом) и торжественно объявляли себя <span class="highlight">королевами леса</span>.
            </p>
            <p>
                Правда, до леса они так и не дошли — кто-то всегда останавливал их в самом начале пути. Бабушка кричала с крыльца, мама звала обедать, соседская собака лаяла. Но это ничуть не умаляло величия их замысла. Ведь главное — не сам замок. Главное — <span class="highlight">что они строили его вместе</span>.
            </p>
            
            <div class="emoji-center">🌳🏠🌳<br>🌳&nbsp;&nbsp;&nbsp;🌳</div>
            
            <h3>🐍 Змея-червяк</h3>
            <p>
                Ариша всегда была самой отважной. Не потому что не боялась — а потому что <span class="highlight">любопытство всегда побеждало страх</span>. Однажды она прибежала домой с чем-то длинным, ползучим и совершенно живым в руках.
            </p>
            <div class="dialogue">
                «Смотри, какой крутой червяк!» — торжественно объявила она, протягивая подруге змею среднего размера.
            </div>
            <p>
                Подруга, конечно, визжала. Бабушка, конечно, визжала ещё громче. А Ариша стояла посреди всего этого хаоса с лицом человека, который только что совершил великое открытие. Потому что для неё это <span class="highlight">и было великим открытием</span> — мир полон чудес, и она хотела поделиться каждым из них.
            </p>
            
            <h3>🏊 Тайные озёра</h3>
            <p>
                А сколько было тайных побегов на озеро! Они ждали, пока взрослые отвлекутся, и ускользали, словно две маленькие тени. Бежали по тропинкам, которые знали только они, через заросли, которые казались им джунглями, к воде, которая казалась им океаном.
            </p>
            <p>
                Они купались, пока солнце не пряталось за горизонт, пока вода не становилась ледяной, пока губы не синеют. А потом, мокрые и счастливые, <span class="highlight">сушили свои вещи утюгом</span> — притворяясь взрослыми домохозяйками. Утюг жужжал, ткань шипела, а они смеялись до слёз.
            </p>
            <p>
                Бабушка, конечно, ругала их — но в её голосе всегда звучала не злость, а <span class="highlight">тёплая, сияющая любовь</span>. Потому что она тоже когда-то была маленькой девочкой, которая убегала на озеро.
            </p>
            
            <h3>🍹 Алхимики</h3>
            <p>
                А ещё они были <span class="highlight">алхимиками</span>. Настоящими, серьёзными, в белых халатах (которые на самом деле были старыми футболками их мам). Они брали лимонад «Буратина» — тот самый, золотистый, с пузырьками, — наливали в большой стакан, добавляли йогурт питьевой и тщательно перемешивали ложкой.
            </p>
            <div class="dialogue">
                «Эликсир готов, госпожа алхимик!» — говорила одна.<br>
                «Пьём за здоровье королевства!» — отвечала другая.
            </div>
            <p>
                И притворялись пьяными. Такими взрослыми, такими важными. Кривлялись, шатались, говорили невпопад. В их маленьких руках обычные напитки превращались в <span class="highlight">волшебные эликсиры</span>, а кухня — в лабораторию, где творились чудеса.
            </p>
            
            <h3>🎒 Сундучок на палке</h3>
            <p>
                Был у них ещё один ритуал. Они брали маленький сундучок — такой, как в мультиках, на верёвочке, на палке, — и складывали туда всё самое необходимое для похода в лес. Кусочек хлеба. Яблоко. Спички (которые им, конечно, нельзя было брать). Бутылочку с водой. И, самое главное, — <span class="highlight">карту сокровищ</span>, нарисованную мелом на картонке.
            </p>
            <p>
                Они собирались идти в лес. Собирались. Снова собирались. И снова. Но так и не дошли — кто-то всегда останавливал их. Мама звала есть. Бабушка просила помочь. Дождь начинался. Или просто становилось темно.
            </p>
            <p>
                Но знаете что? <span class="highlight">Собираться — это тоже было приключением</span>. Потому что в эти минуты, пока они укладывали свой сундучок, они были настоящими путешественницами. А настоящие путешественники знают: дорога важнее пункта назначения.
            </p>
        </div>
        
        <div class="divider">✦ ✧ ✦</div>
        
        <!-- ГЛАВА 2.5 — ПИЦЦА -->
        <div class="chapter">
            <h2>Глава вторая с половиной: Пицца судного дня</h2>
            
            <h3>🍕 Великий кулинарный эксперимент</h3>
            <p>
                Были у них не только алхимические эликсиры. Были и <span class="highlight">кулинарные подвиги</span>. Однажды Ариша, сияя от важности, объявила:
            </p>
            <div class="dialogue">
                «Я умею готовить пиццу! Мама меня научила!»
            </div>
            <p>
                Подруга, конечно, поверила. Как можно было не верить Арише, когда она говорила что-то с такими горящими глазами? И они решили: <span class="highlight">сегодня — день пиццы</span>. Настоящей, взрослой, итальянской пиццы. Только без Италии. И без взрослых.
            </p>
            
            <div class="recipe-box">
                <p style="font-size: 1.4em; color: #ffd700;">📋 Рецепт «Пиццы от Шефа Ариши»</p>
                <p>✦ Мука — много (сколько есть)</p>
                <p>✦ Вода — из-под крана, тёплая</p>
                <p>✦ Масло — <span class="highlight">куча</span> (чтобы не прилипло)</p>
                <p>✦ Колбаса — нарезать всего и побольше</p>
                <p>✦ Сыр — если найдём</p>
                <p>✦ Томатная паста — ложка-другая</p>
                <p>✦ Надежда — бесконечно</p>
            </div>
            
            <p>
                Они намесили тесто. Руками, с энтузиазмом, с грязью под ногтями и мукой в волосах. Тесто получилось... <span class="highlight">особенным</span>. То ли муки мало, то ли воды много, то ли просто они были слишком маленькими, чтобы понимать пропорции. Но они были <span class="highlight">уверены</span> — и это главное в кулинарии, правда?
            </p>
            <p>
                Ариша руководила процессом с такой серьёзностью, словно готовила для самого короля. Нарезали колбасу — <span class="highlight">всего и побольше</span>. Посыпали сыром — пока не кончился. Полили томатной пастой — так, чтобы красиво. И, самое главное, <span class="highlight">налили в противень кучу масла</span>. Потому что мама сказала, что масло — это вкусно. Значит, чем больше масла, тем вкуснее пицца. Логика железная.
            </p>
            
            <div class="pizza-oven">
                <span class="smoke">🔥</span>
            </div>
            <p style="text-align: center; text-indent: 0; font-size: 1em; color: #d4a5a5; margin-top: -10px;">
                <em>Духовка готова. Масло бултыхается. Надежда пылает.</em>
            </p>
            
            <h3>⏰ Пять часов ожидания</h3>
            <p>
                Пиццу поставили в духовку. И стали ждать. Ждали. <span class="highlight">Ждали пять часов</span>. Пять. Целых. Часов.
            </p>
            <p>
                Почему пять? Потому что они забыли про неё. Потому что дети — они такие. Потому что где-то между «поставили в духовку» и «вспомнили про пиццу» прошла целая вечность: они построили ещё один замок из подушек, посмотрели мультик, подрались из-за куклы, помирились, съели печенье и решили, что пора бы уже пообедать.
            </p>
            <div class="oven-glow">⏰ 🔥 ⏰</div>
            <p style="text-align: center; text-indent: 0;">
                <span class="timer">5ч</span>
            </p>
            
            <h3>😱 Чудовище из духовки</h3>
            <p>
                Когда они наконец вспомнили про свою пиццу и открыли духовку, мир изменился. Перед ними лежало <span class="highlight">чудовище</span>. Не пицца — а артефакт. Артефакт древней кулинарной магии.
            </p>
            <p>
                <span class="highlight">Снизу</span> тесто было чёрным, хрустящим, горелым. Таким, от которого весь дом пах дымом. <span class="highlight">Сверху</span> — сырое. Белое, тягучее, живое. Колбаса сохранила свой первозданный вид, сыр так и не расплавился, а томатная паста превратилась в какую-то загадочную субстанцию, которую наука ещё не изучила.
            </p>
            
            <div class="pizza-oven">
                <span class="burnt-pizza">🍕</span>
            </div>
            <p style="text-align: center; text-indent: 0; font-size: 1em; color: #d4a5a5; margin-top: -10px;">
                <em>Снизу — уголь. Сверху — снег. Идеальный баланс.</em>
            </p>
            
            <div class="dialogue">
                «Ну... она выглядит... интересно?» — осторожно произнесла Ариша.<br>
                «Может, это так и должно быть?» — поддержала подруга, хотя обе знали правду.
            </div>
            
            <h3>🐕 Герой нашего времени</h3>
            <p>
                Они стояли над своим творением. Две маленькие поварихи с грязными руками и разбитыми кулинарными мечтами. Пицца была несъедобной. Даже по меркам детей, которые едят песок и считают это нормальным.
            </p>
            <p>
                И тут появился <span class="highlight">он</span>. Соседская собака. Тот самый, который лаял, когда они строили замок. Тот самый, который бегал за ними по деревне. Тот самый, спаситель.
            </p>
            <p>
                Он подошёл. Понюхал. Посмотрел на них виноватыми глазами — словно говорил: <span class="highlight">«Девочки, ну что вы наделали...»</span> — и съел. Всю. Целиком. За три секунды.
            </p>
            
            <div class="dog-eating">🐕 🍕 😋</div>
            
            <p>
                Они смотрели на него с благоговением. Это был <span class="highlight">единственный гурман в мире</span>, которому понравилась их пицца. Единственное существо, оценившее их творчество по достоинству. Или по голодности. Но всё равно — <span class="highlight">оценило</span>.
            </p>
            <div class="dialogue">
                «Мы должны открыть ресторан!» — воскликнула Ариша.<br>
                «Только для собак?» — уточнила подруга.<br>
                «Для всех! Но собаки — вип-гости.»
            </div>
            <p>
                Пицца была провалом. Но этот провал стал <span class="highlight">легендой</span>. Они смеялись над ним годами. Смеялись, когда выросли. Смеются до сих пор. Потому что настоящая дружба — это не только совместные победы. Это и <span class="highlight">совместные катастрофы</span>, над которыми потом можно хохотать до слёз.
            </p>
            <p>
                А соседская собака? Она жила долго и счастливо. И, по слухам, до конца своих дней вспоминала тот день как <span class="highlight">самый вкусный в своей жизни</span>.
            </p>
        </div>
        
        <div class="divider">🍕 ✦ 🍕</div>
        
        <!-- ГЛАВА 3 -->
        <div class="chapter">
            <h2>Глава третья: Магические слова и песни</h2>
            
            <h3>✨ НИФИФИФУФУ</h3>
            <p>
                У девочек был свой секретный язык. Слово, которое они произносили, когда мир казался слишком прекрасным, чтобы быть правдой. Когда они видели радугу после дождя. Когда находили пятак на дороге. Когда бабушка пекла пироги. Когда просто смотрели друг на друга и понимали: <span class="highlight">всё это — наше</span>.
            </p>
            <div class="memory-box">
                <span class="quote-mark">"</span>
                <p style="font-size: 1.3em; color: #ffd700; font-weight: 600;">
                    НИФИФИФУФУ!
                </p>
                <p style="font-style: italic; color: #d4a5a5;">
                    — что в переводе на обычный язык означало:<br>
                    «Ничего себе, офигеть!»
                </p>
            </div>
            <p>
                Это слово было их паролем. Их заклинанием. Их боевым кличем. Они произносили его часто, потому что мир вокруг них был полон чудес. И каждый раз, когда кто-то из них выкрикивал <span class="magic-word">НИФИФИФУФУ!</span>, другая тут же отвечала: «НИФИФИФУФУ!» — и они смеялись, смеялись, смеялись, пока животики не начинали болеть.
            </p>
            <p>
                Это слово жило только между ними. Никто больше не знал, что оно значит. Никто не понимал, почему они вдруг начинают хихикать в магазине, в школе, в церкви. Это было <span class="highlight">их</span>. Только их.
            </p>
            
            <h3>🎤 Песни на центральной улице</h3>
            <p>
                А как они пели! Не в душе, не под подушкой — а <span class="highlight">на всю улицу</span>. Когда вышла песня Глюкозы, две маленькие девочки стояли на центральной улице своей деревни и во всю глотку выкрикивали:
            </p>
            <div class="dialogue-center">
                «А у меня самая самая самая красивая попа!»
            </div>
            <p>
                И в тот самый момент, когда пелось слово <span class="highlight">«попа»</span>, они снимали и показывали... ну, вы понимаете, что. Это было их любимое развлечение, их маленький бунт против скучного мира взрослых.
            </p>
            <p>
                Соседи смотрели из окон и качали головами. Прохожие улыбались. А они стояли посреди улицы, держась за руки, и чувствовали себя <span class="highlight">самыми свободными существами на планете</span>. Потому что когда ты с лучшей подругой — ты можешь всё.
            </p>
        </div>
        
        <div class="divider">✦ ✧ ✦</div>
        
        <!-- ГЛАВА 4 -->
        <div class="chapter">
            <h2>Глава четвёртая: Бисерная империя</h2>
            
            <h3>💎 Первый бизнес</h3>
            <p>
                Ариша была не просто красавицей — она была <span class="highlight">мастерицей</span>. Её маленькие пальчики умели творить чудеса. Она брала крошечные бусинки — красные, синие, золотые, серебряные — и превращала их в <span class="highlight">волшебные украшения</span>.
            </p>
            <p>
                Браслеты, ожерелья, заколки, брелочки. Каждое изделие было уникальным, потому что Ариша вкладывала в него частичку своей души. Она не просто плела — она <span class="highlight">рассказывала истории</span> бисером.
            </p>
            <p>
                И вот тут-то началась настоящая сказка о богатстве и предпринимательстве. Две маленькие девочки — одна мастер, другая менеджер — решили, что их творения достойны мира.
            </p>
            
            <h3>🚪 По домам</h3>
            <p>
                Они <span class="highlight">ходили по домам</span>. Стучали в двери. Улыбались самыми обворожительными улыбками. И предлагали:
            </p>
            <div class="dialogue">
                «Здравствуйте! Мы продаём украшения ручной работы. Очень красивые. Очень модные. Самые лучшие в селе Чля!»
            </div>
            <p>
                И люди покупали. Не потому что украшения были особенными (хотя они были). А потому что две маленькие девочки с горящими глазами — это <span class="highlight">невозможно отказать</span>.
            </p>
            <p>
                На вырученные деньги они покупали ещё бисер — разноцветный, сверкающий, манящий. И делали ещё больше украшений. Это был их первый бизнес. Их первая империя. Их первый шаг к великим делам.
            </p>
            
            <div class="emoji-center">💰➡️💎➡️💰</div>
            
            <h3>💅 Маникюр — магия на кончиках пальцев</h3>
            <p>
                Годы шли. Ариша росла. И её страсть к созданию красоты росла вместе с ней. Бисер сменился кисточками. Браслеты — лаками. А <span class="highlight">маникюр стал её магией</span>.
            </p>
            <p>
                Это не просто хобби. Это — <span class="highlight">искусство</span>. Она берёт обычные ногти и превращает их в произведения искусства. В маленькие картины. В волшебные истории на кончиках пальцев. Цветы, звёзды, абстракции, милые зверьки — всё, что душе угодно.
            </p>
            <p>
                Когда Ариша делает маникюр, она забывает обо всём. Мир сужается до размера ногтевой пластины. И в этом маленьком пространстве она творит <span class="highlight">бесконечность</span>.
            </p>
            <p>
                А ещё она всё так же <span class="highlight">шебутная</span>. Всё так же полна энергии, словно внутри неё живёт маленький солнечный зайчик, который никогда не устаёт прыгать. Позовёшь её куда-нибудь — и она тут же согласится. Намекнёшь на приключение — и она уже готова. Она — <span class="highlight">двигатель</span>, который никогда не останавливается.
            </p>
        </div>
        
        <div class="divider">✦ ✧ ✦</div>
        
        <!-- ГЛАВА 5 -->
        <div class="chapter">
            <h2>Глава пятая: Война невест</h2>
            
            <h3>⚔️ Когда грянул гром</h3>
            <p>
                Но в каждой сказке бывают и тёмные страницы. Были у них и ссоры — как у всех, кто любит друг друга по-настоящему. Потому что когда ты открываешь кому-то своё сердце, этот кто-то иногда может случайно наступить на него.
            </p>
            <p>
                Однажды они <span class="highlight">поругались так сильно</span>, что даже не помнили, из-за чего началось. Слово за слово, обида за обидой — и вот уже они стоят на противоположных берегах реки, а между ними — <span class="highlight">целый океан молчания</span>.
            </p>
            <p>
                Ариша уехала. В Хабаровск, в посёлок Чёрная речка. А подруга осталась в деревне. Они жили в одном городе, но это был <span class="highlight">самый далёкий город на свете</span>.
            </p>
            
            <h3>🌑 Полгода тишины</h3>
            <p>
                Полгода. <span class="highlight">Целых полгода</span>. Сто восемьдесят дней. Четыре тысячи триста двадцать часов. Они не разговаривали. Ни слова. Ни взгляда. Ничего.
            </p>
            <p>
                Словно две звезды, случайно оказавшиеся в разных галактиках. Словно две половинки одного яблока, разломанные и брошенные в разные стороны. Словно <span class="highlight">Рапунцель и её волосы</span>, которые кто-то безжалостно отрезал.
            </p>
            <p>
                Но знаете, что самое страшное в ссоре с близким человеком? Не злость. Не обида. А <span class="highlight">пустота</span>. Когда ты хочешь поделиться чем-то смешным — а не с кем. Когда тебе грустно — а некому обнять. Когда происходит что-то важное — а рядом нет того единственного человека, который поймёт.
            </p>
            
            <h3>🎂 28 апреля — день чуда</h3>
            <p>
                Но судьба — хитрая штука. Она любит драматические повороты. И в тот день, <span class="highlight">28 апреля</span>, в день рождения Ариши, когда солнце встало особенно ярко, а птицы пели особенно громко, случилось чудо.
            </p>
            <p>
                Подруга шла мимо торгового центра к автобусной остановке. Обычный день. Обычная улица. Обычная суета. Они жили в разных концах города — она в центре, Ариша в Чёрной речке. Шанс встретиться был <span class="highlight">один на миллион</span>.
            </p>
            <p>
                Но вот она. <span class="highlight">Ариша</span>. Стоит там, на улице, в свой день рождения, в тот самый день, когда они не разговаривали полгода. Светлая, как всегда. Солнечная, как всегда. С теми самыми изумрудными глазами, в которых отражается всё небо.
            </p>
            
            <div class="memory-box">
                <span class="quote-mark">"</span>
                <p style="font-size: 1.2em; color: #e8c4a0;">
                    И что произошло? Они увидели друг друга.<br>
                    И как ни в чём не бывало — всё забыли.
                </p>
            </div>
            
            <p>
                Вся обида — растворилась, словно дым. Вся злость — улетучилась, словно роса под утренним солнцем. Вся гордость — разбилась о тепло их объятий. Они бросились друг к другу, и в тот момент стало ясно: <span class="highlight">невозможно забыть человека, которого любишь всей душой</span>.
            </p>
            <p>
                Это была не просто встреча. Это было <span class="highlight">чудо</span>. Как в сказке. Как в фильме «Война невест» — когда две подруги, разделённые обстоятельствами, в конце концов понимают, что ничто не сможет разрушить их связь. Потому что настоящая дружба — это не просто слова. Это <span class="highlight">клятва</span>, данная сердцем.
            </p>
            <p>
                И в тот момент подруга поняла: как бы сильно они ни ругались, как бы долго ни молчали — <span class="highlight">она любит её</span>. Вне зависимости от всего. Вне зависимости от ситуации. Вне зависимости от обид. Любит так сильно, что это чувство не помещается ни в одно слово.
            </p>
        </div>
        
        <div class="divider">✦ ✧ ✦</div>
        
        <!-- ГЛАВА 6 -->
        <div class="chapter">
            <h2>Глава шестая: Рапунцель нашего времени</h2>
            
            <h3>👸 Принцесса из сказки</h3>
            <p>
                Ариша — <span class="highlight">блондинка с зелёными глазами</span>. Прямо как из сказки. Как Рапунцель, запертая в башне, только её башня — это не каменные стены, а её собственная светлая душа, из которой она никогда не хотела выбираться.
            </p>
            <p>
                Её волосы — как солнечные лучи, которые кто-то собрал и сплёл в косу. Её глаза — как два изумрудных озера, в которых можно утонуть, но утонешь с улыбкой. Её улыбка — как первый снег: чистая, свежая, <span class="highlight">делающая мир лучше</span> просто тем, что существует.
            </p>
            <p>
                Когда она входит в комнату — <span class="highlight">светлеет</span>. Когда она смеётся — <span class="highlight">светлеет</span>. Когда она просто сидит рядом, молча, — <span class="highlight">всё равно светлеет</span>. Потому что она — солнце в человеческом обличье.
            </p>
            
            <h3>☀️ Оптимизм, который не сломить</h3>
            <p>
                Она <span class="highlight">всегда позитивна</span>. Всегда. Это не значит, что ей никогда не грустно. Это значит, что даже когда ей грустно, она находит в этом что-то хорошее.
            </p>
            <p>
                Никогда не бывает в минусе. Только плюсы. Только солнце. Только радуга. Когда мир кажется серым, Ариша находит в нём цвет. Когда дождь льёт, она видит в нём музыку. Когда всё идёт не так, она улыбается и говорит: <span class="highlight">«Ну, зато какая история получится!»</span>
            </p>
            <p>
                Она — тот человек, который заходит в комнату с плохим настроением и <span class="highlight">выходит с хорошим</span>. Потому что она не просто приносит свет — она <span class="highlight">зажигает</span> его в других.
            </p>
            
            <h3>🤝 На все тысячу процентов</h3>
            <p>
                Она знает свою подругу на <span class="highlight">все тысячу процентов</span>. Знает, когда смеяться, а когда молчать. Знает, когда обнять, а когда дать пространство. Знает, что сказать, когда слова нужны, и знает, как промолчать, когда слова лишние.
            </p>
            <p>
                Всегда поддерживает. Всегда рядом. Даже когда физически далеко — она рядом. Потому что настоящая близость измеряется не километрами, а <span class="highlight">сердцебиениями</span>.
            </p>
            
            <h3>🏙️ Хабаровск — город, который их связал</h3>
            <p>
                Сейчас они живут в одном городе — <span class="highlight">Хабаровске</span>. Огромном, шумном, прекрасном. Они работают, учатся, бегут по своим делам. Время — злой вор, который крадёт минуты, которые можно было бы провести вместе.
            </p>
            <p>
                Они видятся раз в месяц. Иногда чаще, иногда реже. Но этот <span class="highlight">раз в месяц — самый важный день в месяце</span>. Потому что когда они встречаются, время останавливается. Годы отступают. И они снова — две маленькие девочки из села Чля, которые строят домики на деревьях и поют Глюкозу на центральной улице.
            </p>
            
            <h3>💛 Джаным</h3>
            <p>
                Она — <span class="highlight">Джаным</span>. Дорогая. Любимая. Самая близкая. Аришка. Ариша. Принцесса. Нищенка. Подруга. Сестра. Как только её ни называли за эти годы. Но суть одна: <span class="highlight">она — самое светлое, что есть в этой жизни</span>.
            </p>
            <p>
                И когда подруга называет её Джаным — в этом слове столько тепла, столько нежности, столько лет дружбы, что хочется плакать. Но не от грусти. От <span class="highlight">счастья</span>.
            </p>
        </div>
        
        <div class="divider">✦ ✧ ✦</div>
        
        <!-- ГЛАВА 7 -->
        <div class="chapter">
            <h2>Глава седьмая: Мелочи, из которых состоит вечность</h2>
            
            <p>
                На самом деле вся их жизнь — это <span class="highlight">очень много всяких мелких вещей</span>. Не грандиозных событий. Не голливудских сцен. А мелочей. Тёплых, смешных, дорогих сердцу мелочей.
            </p>
            
            <h3>🌸 Мелочи</h3>
            <div class="memory-box">
                <p>✦ Как они ругались, как и все люди — потому что настоящая дружба не стерильна</p>
                <p>✦ Как подруга, вспыльчивая по натуре, иногда говорила лишнего — а Ариша прощала</p>
                <p>✦ Как они смеялись до слёз над своими же шутками</p>
                <p>✦ Как молчали вместе — и это молчание было уютнее любых слов</p>
                <p>✦ Как делили всё: секреты, еду, мечты, страхи</p>
                <p>✦ Как ни разу не было главной и второй — они были всегда наравне</p>
                <p>✦ Как одна была светленькая, а другая тёмненькая — и вместе они были идеальной картинкой</p>
                <p>✦ Как пекли пиццу, которая стала легендой — и соседская собака до сих пор вспоминает тот день</p>
            </div>
            
            <h3>🌟 Что особенно ценно</h3>
            <p>
                Подруга безумно ценит Аришу за её характер. За её постоянный оптимизм. За то, что она никогда не бывает в минусе. За то, что она — <span class="highlight">всегда плюс</span>. За то, что даже в самый чёрный день она найдёт лучик света.
            </p>
            <p>
                Она ценит её за то, что Ариша — <span class="highlight">опора</span>. За то, что можно прийти к ней с разбитым сердцем, и она не будет говорить банальности. Она просто будет рядом. А этого — <span class="highlight">достаточно</span>.
            </p>
            <p>
                Она ценит её за то, что Ариша помнит. Помнит все их истории. Помнит НИФИФИФУФУ. Помнит домик на четырёх деревьях. Помнит змею-червяка. Помнит, как они пели на улице. Помнит, как продавали бисер. Помнит пиццу и собаку. Помнит всё — потому что <span class="highlight">всё это — их общее сокровище</span>, которое не стирается со временем, не тускнеет, не ржавеет. Оно лежит в самом тайном ящичке сердца, и стоит его открыть — и сразу становится тепло.
            </p>
        </div>

        <div class="divider">✦ ✧ ✦</div>

        <!-- ГЛАВА 8 — НОВАЯ -->
        <div class="chapter">
            <h2>Глава восьмая: Двадцать три года спустя</h2>

            <h3>⏳ Сколько всего было</h3>

            <div class="years-counter">
                <div class="year-item">
                    <span class="num">23</span>
                    <span class="label">года дружбы</span>
                </div>
                <div class="year-item">
                    <span class="num">∞</span>
                    <span class="label">смеха</span>
                </div>
                <div class="year-item">
                    <span class="num">1</span>
                    <span class="label">пицца-катастрофа</span>
                </div>
                <div class="year-item">
                    <span class="num">0</span>
                    <span class="label">сожалений</span>
                </div>
            </div>

            <p>
                Двадцать три года. Это звучит как большая цифра. Но когда они вместе — кажется, будто прошло только вчера. Вчера они строили домик на деревьях. Вчера пели Глюкозу. Вчера сожгли пиццу и накормили собаку. Время ведёт себя странно рядом с человеком, которого любишь — оно то растягивается в вечность, то сжимается в один-единственный счастливый миг.
            </p>
            <p>
                Они обе изменились. Конечно. Так бывает — люди меняются, взрослеют, становятся другими версиями себя. Но есть что-то, что не меняется никогда. <span class="highlight">Суть</span>. Та самая, которую они увидели друг в друге ещё тогда, когда были маленькими девочками в селе Чля. Та самая, которая сказала им: «Эти двое — вместе навсегда».
            </p>
            <p>
                Ариша по-прежнему <span class="highlight">солнечная</span>. По-прежнему шебутная. По-прежнему та, которая первой скажет «поехали!» и уже стоит у двери с ключами. По-прежнему видит красоту там, где другие видят только обычный день. Это не наивность. Это — <span class="highlight">дар</span>.
            </p>

            <h3>📸 Что осталось навсегда</h3>
            <p>
                У них нет совместных фотографий из детства — не то время было, не те возможности. Но у них есть кое-что лучше. У них есть <span class="highlight">воспоминания, которые живее любой фотографии</span>. Которые пахнут горелым тестом и лимонадом «Буратина». Которые звучат детским смехом на центральной улице. Которые тёплые, как бабушкины пироги.
            </p>
            <p>
                Иногда они встречаются — и вдруг кто-то произносит одно слово. Одно. И обе уже смеются. Потому что у них свой язык. Их собственный, никому больше не понятный. Язык, в котором одно слово значит целую историю. Целое лето. Целое детство.
            </p>

            <div class="golden-rule">
                <p>
                    <span class="wish-star">⭐</span> &nbsp;
                    <span class="magic-word">НИФИФИФУФУ!</span>
                    &nbsp; <span class="wish-star">⭐</span><br>
                    <span style="color: #d4a5a5; font-size: 0.85em; font-style: italic;">
                        — так говорят, когда мир слишком прекрасен, чтобы молчать
                    </span>
                </p>
            </div>
        </div>

        <div class="divider">✦ ✧ ✦</div>

        <!-- ГЛАВА 9 — НОВАЯ: ПИСЬМО -->
        <div class="chapter">
            <h2>Глава девятая: Письмо, которое давно хотелось написать</h2>

            <p>
                Есть вещи, которые очень трудно сказать вслух. Не потому что их стыдишься. А потому что они такие большие, что их сложно уместить в обычные слова. Их хочется написать. Красиво. Медленно. С чувством.
            </p>
            <p>
                Поэтому — вот письмо. Не деловое, не короткое. Настоящее. Такое, какие писали раньше — долго, на нескольких страницах, у окна, при свечах. Только вместо свечей — звёзды. И вместо чернил — всё, что накопилось за двадцать три года.
            </p>

            <div class="letter-box">
                <p>Аришка, Джаным, принцесса моя светлоглазая.</p>
                <p>Я не умею говорить красиво вслух — ты знаешь. Я скорее буркну что-то невнятное и сделаю вид, что всё нормально. Но сегодня — твой день. И сегодня я скажу.</p>
                <p>Спасибо тебе за то, что ты такая. За солнце, которое ты несёшь в себе и раздаёшь всем вокруг, даже когда тебе самой не очень. За то, что ты никогда не считала меня виноватой дольше, чем нужно. За то, что ты помнишь всё — каждую глупость, каждое приключение, каждый момент, который мы прожили вместе.</p>
                <p>За пиццу. Боже, за пиццу особенно. За то, что мы с тобой смогли превратить абсолютную катастрофу в лучшую историю нашей жизни.</p>
                <p>За то, что ты была рядом, когда было нужно. И за то, что не была рядом, когда мне надо было самой разобраться — ты чувствовала это каким-то чудом.</p>
                <p>Ты — моя константа. Всё меняется: города, люди, обстоятельства. Ты — остаёшься. И это самое прекрасное, что может быть.</p>
                <p>С днём рождения, Джаным. Расти большой. Хотя ты и так уже большая — просто не перестай быть собой.</p>
                <p style="text-align: right; color: #ffd700; font-style: normal;">Твоя тёмненькая подруга 🖤</p>
            </div>
        </div>

        <div class="divider">✦ ✧ ✦</div>

        <!-- ФИНАЛЬНАЯ ГЛАВА -->
        <div class="chapter">
            <h2>Глава десятая и последняя: Долго и счастливо</h2>

            <p>
                В настоящих сказках всегда так заканчивается: <span class="highlight">«И жили они долго и счастливо»</span>. Но знаете, в чём секрет? Это не конец. Это — <span class="highlight">начало</span>. Каждый раз, когда кто-то произносит эти слова, начинается новая история. Потому что долго и счастливо — это не финальная точка. Это ежедневный выбор.
            </p>
            <p>
                Они выбирают это каждый день. Выбирают друг друга. Выбирают звонить, когда хочется промолчать. Выбирают встречаться, даже когда устали. Выбирают смеяться над старыми историями про пиццу, вместо того чтобы копить обиды. Выбирают быть рядом — по-настоящему, душой, — даже когда разделяет целый город.
            </p>

            <div class="final-poem">
                Две девочки из маленького Чля —<br>
                одна как солнце, и другая — тень её —<br>
                нашли секрет, которого не знают все:<br>
                что счастье — это просто быть вдвоём.<br><br>
                Сквозь годы, ссоры, пиццу и смешное,<br>
                сквозь «не звоню» и «снова помирились» —<br>
                одно осталось главным и родным:<br>
                они друг другу попросту случились.
            </div>

            <p>
                И это, пожалуй, самое точное слово. <span class="highlight">Случились</span>. Не договорились, не назначили, не решили по расчёту. Просто однажды оказались рядом — две маленькие девочки под одним небом — и поняли, что это навсегда.
            </p>
            <p>
                А небо над Чля в тот апрельский день, когда родилась принцесса Ариша, было таким синим, таким чистым, таким бесконечным. Словно оно специально приготовилось. Словно знало. Словно хотело сказать: <span class="highlight">смотрите, сегодня рождается тот, кто будет нужен кому-то очень важному</span>.
            </p>
            <p>
                И небо не ошиблось.
            </p>
        </div>

        <!-- КОНЦОВКА -->
        <div class="ending">
            <span class="age-badge">23</span>
            <h2>С днём рождения, Ариша! <span class="heart">♥</span></h2>

            <div class="confetti-line">🎂 🎉 🌟 🎈 ✨</div>

            <p style="margin-bottom: 18px;">
                Пусть этот год будет таким же ярким, как ты сама.<br>
                Пусть в нём будет всё: смех, солнце, маникюр-шедевр,<br>
                новые приключения — и ни одной подгоревшей пиццы<br>
                (ну или хотя бы одна, для легенды).
            </p>

            <p style="margin-bottom: 18px; color: #ffd700;">
                Ты — 23 года назад изменила одну жизнь.<br>
                Просто тем, что родилась. Просто тем, что <strong>ты — это ты</strong>.
            </p>

            <div class="memory-box" style="max-width: 480px; margin: 25px auto;">
                <p style="color: #ffd700; font-size: 1.2em;">Три вещи, которые не изменятся никогда:</p>
                <p>☀️ &nbsp; Ариша будет солнечной</p>
                <p>🍕 &nbsp; Пицца-легенда будет жить вечно</p>
                <p>💛 &nbsp; Дружба — тоже</p>
            </div>

            <p style="font-size: 1.5em; margin-top: 30px;">
                <span class="magic-word">НИФИФИФУФУ!</span>
            </p>
            <p style="color: #d4a5a5; font-style: italic; font-size: 1em; margin-top: 5px;">
                — потому что ты существуешь, и это офигительно
            </p>

            <div class="signature">
                с любовью, твоя тёмненькая 🖤
            </div>
        </div>

    </div>

    <script>
        // Создаём звёзды
        const starsContainer = document.getElementById('stars');
        for (let i = 0; i < 200; i++) {
            const star = document.createElement('div');
            star.className = 'star';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            star.style.animationDelay = Math.random() * 3 + 's';
            star.style.animationDuration = (2 + Math.random() * 3) + 's';
            star.style.opacity = Math.random() * 0.7 + 0.1;
            const size = Math.random() * 2.5 + 0.5;
            star.style.width = size + 'px';
            star.style.height = size + 'px';
            starsContainer.appendChild(star);
        }

        // Падающие звёзды
        for (let i = 0; i < 5; i++) {
            const shooting = document.createElement('div');
            shooting.className = 'shooting-star';
            shooting.style.top = Math.random() * 60 + '%';
            shooting.style.left = Math.random() * 40 + '%';
            shooting.style.animationDelay = (i * 5 + Math.random() * 8) + 's';
            shooting.style.animationDuration = (3 + Math.random() * 3) + 's';
            starsContainer.appendChild(shooting);
        }

        // Плавное появление глав при скролле
        const chapters = document.querySelectorAll('.chapter, .ending');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateX(0)';
                }
            });
        }, { threshold: 0.08 });

        chapters.forEach(ch => {
            ch.style.opacity = '0';
            ch.style.transform = 'translateX(-20px)';
            ch.style.transition = 'opacity 0.7s ease, transform 0.7s ease';
            observer.observe(ch);
        });
    </script>
</body>
</html>
