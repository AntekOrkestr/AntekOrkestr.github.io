> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Онлайн Чат-Рулетка</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
            color: white;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
        }
        
        .container {
            max-width: 900px;
            width: 100%;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            overflow: hidden;
        }
        
        header {
            text-align: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 2px solid rgba(255, 255, 255, 0.2);
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
        }
        
        .tagline {
            font-size: 1.1rem;
            opacity: 0.8;
        }
        
        .main-content {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .video-container {
            position: relative;
            width: 100%;
            height: 400px;
            background: #000;
            border-radius: 10px;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .video-feed {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 10px;
        }
        
        .searching-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 10;
        }
        
        .searching-text {
            font-size: 1.8rem;
            margin-bottom: 20px;
            animation: pulse 1.5s infinite;
        }
        
        .loader {
            width: 60px;
            height: 60px;
            border: 5px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top-color: #fdbb2d;
            animation: spin 1s linear infinite;
        }
        
        .controls {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-top: 20px;
        }
        
        .btn {
            padding: 12px 25px;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .btn-primary {
            background: #fdbb2d;
            color: #1a2a6c;
        }
        
        .btn-primary:hover {
            background: #ffa500;
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(253, 187, 45, 0.4);
        }
        
        .btn-secondary {
            background: rgba(255, 255, 255, 0.2);
            color: white;
        }
        
        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: translateY(-3px);

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
}
        
        .btn-danger {
            background: #b21f1f;
            color: white;
        }
        
        .btn-danger:hover {
            background: #8a1919;
            transform: translateY(-3px);
        }
        
        .chat-container {
            background: rgba(0, 0, 0, 0.5);
            border-radius: 10px;
            padding: 15px;
            height: 200px;
            display: flex;
            flex-direction: column;
        }
        
        .chat-messages {
            flex: 1;
            overflow-y: auto;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 5px;
            background: rgba(255, 255, 255, 0.1);
        }
        
        .message {
            margin-bottom: 10px;
            padding: 8px 12px;
            border-radius: 15px;
            max-width: 80%;
            animation: fadeIn 0.3s ease;
        }
        
        .user-message {
            background: rgba(253, 187, 45, 0.3);
            margin-left: auto;
            border-bottom-right-radius: 5px;
        }
        
        .bot-message {
            background: rgba(26, 42, 108, 0.5);
            margin-right: auto;
            border-bottom-left-radius: 5px;
        }
        
        .chat-input {
            display: flex;
            gap: 10px;
        }
        
        .chat-input input {
            flex: 1;
            padding: 12px 15px;
            border: none;
            border-radius: 25px;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            font-size: 1rem;
        }
        
        .chat-input input:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.15);
        }
        
        .chat-input button {
            padding: 12px 20px;
            border: none;
            border-radius: 25px;
            background: #1a2a6c;
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .chat-input button:hover {
            background: #2538a0;
        }
        
        .user-count {
            text-align: center;
            margin-top: 15px;
            font-size: 0.9rem;
            opacity: 0.7;
        }
        
        .bot-indicator {
            display: inline-block;
            background: rgba(178, 31, 31, 0.7);
            padding: 2px 8px;
            border-radius: 10px;
            font-size: 0.7rem;
            margin-left: 5px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        @keyframes pulse {
            0% { opacity: 0.6; }
            50% { opacity: 1; }
            100% { opacity: 0.6; }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes slideIn {
            from { transform: translateX(-100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        
        @media (max-width: 768px) {
            .video-container {
                height: 300px;
            }
            
            h1 {
                font-size: 2rem;
            }
            
            .controls {
                flex-wrap: wrap;
            }
            
            .btn {
                padding: 10px 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Онлайн Чат-Рулетка</h1>
            <p class="tagline">Общайтесь с случайными собеседниками со всего мира!</p>
        </header>
        
        <div class="main-content">
            <div class="video-container">

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
<div class="searching-overlay" id="searchingOverlay">
                    <div class="searching-text">Поиск собеседника...</div>
                    <div class="loader"></div>
                </div>
                <video class="video-feed" id="videoFeed" autoplay muted></video>
            </div>
            
            <div class="controls">
                <button class="btn btn-primary" id="startBtn">
                    <span>Начать поиск</span>
                </button>
                <button class="btn btn-secondary" id="nextBtn" disabled>
                    <span>Следующий</span>
                </button>
                <button class="btn btn-danger" id="stopBtn" disabled>
                    <span>Завершить</span>
                </button>
            </div>
            
            <div class="chat-container">
                <div class="chat-messages" id="chatMessages">
                    <div class="message bot-message">
                        Добро пожаловать в чат-рулетку! Нажмите "Начать поиск", чтобы найти собеседника.
                    </div>
                </div>
                <div class="chat-input">
                    <input type="text" id="messageInput" placeholder="Введите сообщение..." disabled>
                    <button id="sendBtn" disabled>Отправить</button>
                </div>
            </div>
            
            <div class="user-count">
                Онлайн: <span id="onlineCount">1,247</span> пользователей
            </div>
        </div>
    </div>

    <script>
        // Элементы DOM
        const startBtn = document.getElementById('startBtn');
        const nextBtn = document.getElementById('nextBtn');
        const stopBtn = document.getElementById('stopBtn');
        const searchingOverlay = document.getElementById('searchingOverlay');
        const videoFeed = document.getElementById('videoFeed');
        const chatMessages = document.getElementById('chatMessages');
        const messageInput = document.getElementById('messageInput');
        const sendBtn = document.getElementById('sendBtn');
        const onlineCount = document.getElementById('onlineCount');

        // Состояние приложения
        let isConnected = false;
        let currentBot = null;
        let messageCount = 0;

        // Список ботов с их характеристиками
        const bots = [
            {
                name: "Анна",
                age: 24,
                country: "Россия",
                interests: ["путешествия", "фотография", "кофе"],
                video: "anna",
                messages: [
                    "Привет! Как твои дела?",
                    "Я из Москвы, а ты откуда?",
                    "Люблю путешествовать. Была уже в 15 странах!",
                    "У тебя есть хобби?",
                    "Я работаю дизайнером, очень нравится творческая работа.",
                    "Какую музыку ты слушаешь?",
                    "Сегодня отличная погода, не правда ли?",
                    "Ты часто пользуешься чат-рулеткой?",
                    "У меня есть кот, его зовут Барсик :)",
                    "Что ты планируешь на выходные?"
                ]
            },
            {
                name: "Максим",
                age: 29,
                country: "Украина",
                interests: ["спорт", "технологии", "автомобили"],
                video: "maxim",
                messages: [
                    "Приветствую! Рад познакомиться.",
                    "Я из Киева, красивый город!",
                    "Увлекаюсь спортом, особенно футболом.",
                    "Как прошел твой день?",
                    "Работаю в IT-сфере, программистом.",
                    "Люблю смотреть фильмы в свободное время.",
                    "Был недавно в Карпатах, очень красиво там!",

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
"У тебя есть машина?",
                    "Слушаю в основном рок-музыку.",
                    "Какие у тебя планы на будущее?"
                ]
            },
            {
                name: "София",
                age: 21,
                country: "Беларусь",
                interests: ["искусство", "литература", "йога"],
                video: "sofia",
                messages: [
                    "Привет! Очень рада встрече!",
                    "Я из Минска, у нас тут красиво.",
                    "Люблю читать книги, особенно классику.",
                    "Занимаюсь йогой уже два года.",
                    "Учусь в университете на филолога.",
                    "Обожаю посещать художественные выставки.",
                    "Как ты провел сегодняшний день?",
                    "У тебя есть любимый писатель?",
                    "Мечтаю побывать в Париже.",
                    "Что для тебя важно в жизни?"
                ]
            }
        ];

        // Функция для обновления счетчика онлайн пользователей
        function updateOnlineCount() {
            const baseCount = 1247;
            const randomChange = Math.floor(Math.random() * 21) - 10; // -10 to +10
            onlineCount.textContent = (baseCount + randomChange).toLocaleString();
            
            // Обновляем каждые 10 секунд
            setTimeout(updateOnlineCount, 10000);
        }

        // Функция для поиска собеседника
        function findPartner() {
            if (isConnected) return;
            
            // Показываем анимацию поиска
            searchingOverlay.style.display = 'flex';
            startBtn.disabled = true;
            
            // Имитируем поиск в течение 2-5 секунд
            const searchTime = 2000 + Math.random() * 3000;
            
            setTimeout(() => {
                // Выбираем случайного бота
                currentBot = bots[Math.floor(Math.random() * bots.length)];
                
                // Скрываем анимацию поиска
                searchingOverlay.style.display = 'none';
                
                // В реальном приложении здесь бы подключалось видео
                // Для демо мы просто показываем статичное изображение с именем бота
                videoFeed.innerHTML = 
                    <div style="width:100%; height:100%; display:flex; flex-direction:column; justify-content:center; align-items:center; background:linear-gradient(135deg, #1a2a6c, #b21f1f); color:white; font-size:24px;">
                        <div style="font-size:3rem; margin-bottom:20px;">📹</div>
                        <div>${currentBot.name}, ${currentBot.age}</div>
                        <div style="font-size:16px; margin-top:10px;">${currentBot.country}</div>
                        <div class="bot-indicator" style="margin-top:15px;">БОТ</div>
                    </div>
                ;
                
                // Активируем кнопки
                nextBtn.disabled = false;
                stopBtn.disabled = false;
                messageInput.disabled = false;
                sendBtn.disabled = false;
                
                isConnected = true;
                
                // Добавляем приветственное сообщение от бота
                setTimeout(() => {
                    addBotMessage(currentBot.messages[0]);
                }, 1000);
                
            }, searchTime);
        }

        // Функция для добавления сообщения от бота
        function addBotMessage(text) {
            const messageElement = document.createElement('div');
            messageElement.classList.add('message', 'bot-message');
            messageElement.textContent = text;
            chatMessages.appendChild(messageElement);
            chatMessages.scrollTop = chatMessages.scrollHeight;
