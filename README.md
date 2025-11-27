<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>◕‿◕𝓑 𝓻 𝓸 𝓼 𝓱 𝓴 𝓪◕‿◕ - Чат Рулетка</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            color: white;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        .header {
            text-align: center;
            padding: 20px;
            background: rgba(0, 0, 0, 0.3);
            border-bottom: 2px solid #00adb5;
            position: relative;
        }

        .title {
            font-size: 2.5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #00adb5, #a8e6cf);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 10px rgba(0, 173, 181, 0.5);
            margin-bottom: 10px;
        }

        .subtitle {
            font-size: 1rem;
            color: #eeeeee;
            opacity: 0.8;
        }

        .container {
            display: flex;
            flex: 1;
            padding: 20px;
            gap: 20px;
        }

        .chat-container {
            flex: 3;
            display: flex;
            flex-direction: column;
            background: rgba(30, 30, 46, 0.7);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid #00adb5;
        }

        .video-container {
            position: relative;
            flex: 1;
            background: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 400px;
        }

        .video-placeholder {
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #1a1a2e, #16213e);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: #00adb5;
            font-size: 1.5rem;
        }

        .video-placeholder i {
            font-size: 4rem;
            margin-bottom: 20px;
            color: #00adb5;
        }

        .controls {
            display: flex;
            justify-content: center;
            gap: 20px;
            padding: 20px;
            background: rgba(20, 20, 35, 0.8);
        }

        .control-btn {
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

        .start-btn {
            background: linear-gradient(45deg, #00adb5, #00c9c8);
            color: white;
            box-shadow: 0 5px 15px rgba(0, 173, 181, 0.4);
        }

        .start-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 173, 181, 0.6);
        }

        .stop-btn {
            background: linear-gradient(45deg, #ff2e63, #ff5c8d);
            color: white;
            box-shadow: 0 5px 15px rgba(255, 46, 99, 0.4);
        }

        .stop-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(255, 46, 99, 0.6);
        }

        .next-btn {
            background: linear-gradient(45deg, #a8e6cf, #6ce5b1);
            color: #1a1a2e;
            box-shadow: 0 5px 15px rgba(168, 230, 207, 0.4);
        }

        .next-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(168, 230, 207, 0.6);
        }

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
.sidebar {
            flex: 1;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .panel {
            background: rgba(30, 30, 46, 0.7);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            border: 1px solid #00adb5;
        }

        .panel-title {
            font-size: 1.2rem;
            margin-bottom: 15px;
            color: #00adb5;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .bot-list {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .bot-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 12px;
            background: rgba(40, 40, 62, 0.7);
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .bot-item:hover {
            background: rgba(50, 50, 82, 0.7);
            transform: translateX(5px);
        }

        .bot-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(45deg, #00adb5, #a8e6cf);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .bot-info {
            flex: 1;
        }

        .bot-name {
            font-weight: bold;
        }

        .bot-desc {
            font-size: 0.8rem;
            color: #aaaaaa;
        }

        .bot-status {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: #4caf50;
        }

        .dev-menu {
            position: absolute;
            top: 20px;
            right: 20px;
        }

        .dev-btn {
            background: rgba(0, 0, 0, 0.5);
            color: #00adb5;
            border: 1px solid #00adb5;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .dev-btn:hover {
            background: rgba(0, 173, 181, 0.2);
        }

        .dev-panel {
            display: none;
            position: absolute;
            top: 50px;
            right: 0;
            background: rgba(20, 20, 35, 0.95);
            border-radius: 10px;
            padding: 15px;
            width: 300px;
            z-index: 100;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid #00adb5;
        }

        .dev-option {
            padding: 10px;
            margin: 5px 0;
            background: rgba(40, 40, 62, 0.7);
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .dev-option:hover {
            background: rgba(50, 50, 82, 0.7);
        }

        .stats {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .stat-item {
            text-align: center;
        }

        .stat-value {
            font-size: 1.5rem;
            font-weight: bold;
            color: #00adb5;
        }

        .stat-label {
            font-size: 0.8rem;
            color: #aaaaaa;
        }

        .chat-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
            max-height: 300px;
        }

        .message {
            display: flex;
            gap: 10px;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
.message-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff2e63, #ff5c8d);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            flex-shrink: 0;
        }

        .message-content {
            background: rgba(40, 40, 62, 0.7);
            padding: 12px;
            border-radius: 10px;
            flex: 1;
        }

        .message-sender {
            font-weight: bold;
            margin-bottom: 5px;
            color: #00adb5;
        }

        .chat-input {
            display: flex;
            padding: 15px;
            background: rgba(20, 20, 35, 0.8);
            gap: 10px;
        }

        .chat-input input {
            flex: 1;
            padding: 12px;
            border-radius: 50px;
            border: none;
            background: rgba(40, 40, 62, 0.7);
            color: white;
            outline: none;
        }

        .chat-input button {
            padding: 12px 20px;
            border: none;
            border-radius: 50px;
            background: linear-gradient(45deg, #00adb5, #00c9c8);
            color: white;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .chat-input button:hover {
            transform: scale(1.05);
        }

        .connection-status {
            position: absolute;
            top: 20px;
            left: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            background: rgba(0, 0, 0, 0.5);
            padding: 8px 15px;
            border-radius: 50px;
            font-size: 0.9rem;
        }

        .status-indicator {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: #ff2e63;
        }

        .status-indicator.connected {
            background: #4caf50;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { opacity: 1; }
            50% { opacity: 0.5; }
            100% { opacity: 1; }
        }

        .footer {
            text-align: center;
            padding: 15px;
            background: rgba(0, 0, 0, 0.3);
            border-top: 1px solid #00adb5;
            font-size: 0.8rem;
            color: #aaaaaa;
        }

        .typing-indicator {
            display: none;
            padding: 10px;
            color: #00adb5;
            font-style: italic;
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            .container {
                flex-direction: column;
            }
            
            .sidebar {
                flex-direction: row;
            }
            
            .panel {
                flex: 1;
            }
        }
    </style>
</head>
<body>
    <div class="header">
        <div class="title">◕‿◕𝓑 𝓻 𝓸 𝓼 𝓱 𝓴 𝓪◕‿◕</div>
        <div class="subtitle">Анонимный видеочат с ботами и нейросетями</div>
        
        <div class="dev-menu">
            <button class="dev-btn" id="devBtn">Меню разработчика</button>
            <div class="dev-panel" id="devPanel">
                <div class="dev-option">Настройки соединения</div>
                <div class="dev-option">Логи чата</div>
                <div class="dev-option">Статистика использования</div>
                <div class="dev-option">Тестирование ботов</div>
                <div class="dev-option">API ключи</div>
                <div class="dev-option">Настройки интерфейса</div>
            </div>
        </div>
        
        <div class="connection-status">
            <div class="status-indicator" id="statusIndicator"></div>
            <span id="statusText">Поиск собеседника...</span>
        </div>
    </div>

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
<div class="container">
        <div class="chat-container">
            <div class="video-container">
                <div class="video-placeholder" id="videoPlaceholder">
                    <i>📹</i>
                    <div>Начните поиск собеседника</div>
                </div>
            </div>
            
            <div class="chat-messages" id="chatMessages">
                <div class="message">
                    <div class="message-avatar">Б</div>
                    <div class="message-content">
                        <div class="message-sender">Broshka Bot</div>
                        <div>Добро пожаловать в ◕‿◕𝓑 𝓻 𝓸 𝓼 𝓱 𝓴 𝓪◕‿◕! Нажмите "Начать поиск", чтобы найти собеседника.</div>
                    </div>
                </div>
            </div>
            
            <div class="typing-indicator" id="typingIndicator">
                Собеседник печатает...
            </div>
            
            <div class="chat-input">
                <input type="text" id="messageInput" placeholder="Введите сообщение...">
                <button id="sendMessage">Отправить</button>
            </div>
            
            <div class="controls">
                <button class="control-btn start-btn" id="startBtn">
                    <i>▶</i> Начать поиск
                </button>
                <button class="control-btn stop-btn" id="stopBtn" disabled>
                    <i>⏹</i> Остановить
                </button>
                <button class="control-btn next-btn" id="nextBtn" disabled>
                    <i>⏭</i> Следующий
                </button>
            </div>
        </div>
        
        <div class="sidebar">
            <div class="panel">
                <div class="panel-title">
                    <i>🤖</i> Доступные боты
                </div>
                <div class="bot-list">
                    <div class="bot-item" data-bot="ai">
                        <div class="bot-avatar">AI</div>
                        <div class="bot-info">
                            <div class="bot-name">Искусственный интеллект</div>
                            <div class="bot-desc">Умный собеседник на базе нейросети</div>
                        </div>
                        <div class="bot-status"></div>
                    </div>
                    <div class="bot-item" data-bot="psychologist">
                        <div class="bot-avatar">П</div>
                        <div class="bot-info">
                            <div class="bot-name">Психолог</div>
                            <div class="bot-desc">Поможет разобраться в проблемах</div>
                        </div>
                        <div class="bot-status"></div>
                    </div>
                    <div class="bot-item" data-bot="entertainer">
                        <div class="bot-avatar">Р</div>
                        <div class="bot-info">
                            <div class="bot-name">Рассказчик</div>
                            <div class="bot-desc">Интересные истории и факты</div>
                        </div>
                        <div class="bot-status"></div>
                    </div>
                    <div class="bot-item" data-bot="gamer">
                        <div class="bot-avatar">И</div>
                        <div class="bot-info">
                            <div class="bot-name">Игрок</div>
                            <div class="bot-desc">Сыграет с вами в словесные игры</div>
                        </div>
                        <div class="bot-status"></div>
                    </div>
                </div>
            </div>
            
            <div class="panel">
                <div class="panel-title">
                    <i>📊</i> Статистика
                </div>

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
<div class="stats">
                    <div class="stat-item">
                        <div class="stat-value" id="onlineCount">1,234</div>
                        <div class="stat-label">Онлайн</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value" id="chatsCount">5,678</div>
                        <div class="stat-label">Чатов сегодня</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-value" id="countriesCount">42</div>
                        <div class="stat-label">Страны</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="footer">
        ◕‿◕𝓑 𝓻 𝓸 𝓼 𝓱 𝓴 𝓪◕‿◕ | Анонимный чат | Все права защищены | Версия 2.1.4
    </div>

    <script>
        // Элементы интерфейса
        const startBtn = document.getElementById('startBtn');
        const stopBtn = document.getElementById('stopBtn');
        const nextBtn = document.getElementById('nextBtn');
        const devBtn = document.getElementById('devBtn');
        const devPanel = document.getElementById('devPanel');
        const statusIndicator = document.getElementById('statusIndicator');
        const statusText = document.getElementById('statusText');
        const videoPlaceholder = document.getElementById('videoPlaceholder');
        const chatMessages = document.getElementById('chatMessages');
        const messageInput = document.getElementById('messageInput');
        const sendMessageBtn = document.getElementById('sendMessage');
        const typingIndicator = document.getElementById('typingIndicator');
        const botItems = document.querySelectorAll('.bot-item');
        
        // Переменные состояния
        let isConnected = false;
        let currentBot = null;
        let connectionTimer = null;
        let typingTimer = null;
        
        // Случайные имена для собеседников
        const names = ['Алексей', 'Мария', 'Дмитрий', 'Анна', 'Сергей', 'Ольга', 'Иван', 'Елена', 'Максим', 'Наталья'];
        const countries = ['Россия', 'Украина', 'Беларусь', 'Казахстан', 'Германия', 'США', 'Франция', 'Италия'];
        
        // Инициализация
        function init() {
            // Обработчики кнопок
            startBtn.addEventListener('click', startSearch);
            stopBtn.addEventListener('click', stopSearch);
            nextBtn.addEventListener('click', nextChat);
            devBtn.addEventListener('click', toggleDevMenu);
            sendMessageBtn.addEventListener('click', sendMessage);
            messageInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') sendMessage();
            });
            
            // Обработчики ботов
            botItems.forEach(item => {
                item.addEventListener('click', function() {
                    selectBot(this.dataset.bot);
                });
            });
            
            // Закрытие меню разработчика при клике вне его
            document.addEventListener('click', function(e) {
                if (!devBtn.contains(e.target) && !devPanel.contains(e.target)) {
                    devPanel.style.display = 'none';
                }
            });
            
            // Обновление статистики
            updateStats();
        }
        
        // Поиск собеседника
        function startSearch() {
            if (isConnected) return;
            
            startBtn.disabled = true;
            stopBtn.disabled = false;
            nextBtn.disabled = true;
            
            statusText.textContent = 'Поиск собеседника...';
            statusIndicator.classList.remove('connected');
            
            // Имитация поиска

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
let dots = '';
            const searchInterval = setInterval(() => {
                dots = dots.length < 3 ? dots + '.' : '';
                statusText.textContent = 'Поиск собеседника' + dots;
            }, 500);
            
            // Имитация соединения через 3-7 секунд
            const connectTime = 3000 + Math.random() * 4000;
            connectionTimer = setTimeout(() => {
                clearInterval(searchInterval);
                connectToUser();
            }, connectTime);
        }
        
        // Подключение к собеседнику
        function connectToUser() {
            isConnected = true;
            startBtn.disabled = true;
            stopBtn.disabled = false;
            nextBtn.disabled = false;
            
            statusText.textContent = 'Соединение установлено';
            statusIndicator.classList.add('connected');
            
            // Обновление видео-заглушки
            const name = names[Math.floor(Math.random() * names.length)];
            const country = countries[Math.floor(Math.random() * countries.length)];
            videoPlaceholder.innerHTML = 
                <i>👤</i>
                <div>${name}, ${country}</div>
                <div style="font-size: 1rem; margin-top: 10px;">Видеосвязь</div>
            ;
            
            // Добавление сообщения от бота
            addMessage('Broshka Bot', Соединение с ${name} из ${country} установлено!, true);
            
            // Имитация приветствия от собеседника
            setTimeout(() => {
                const greetings = [
                    'Привет! Как дела?',
                    'Здравствуйте! Рад познакомиться.',
                    'Приветствую! Откуда вы?',
                    'Привет! Как настроение?'
                ];
                const greeting = greetings[Math.floor(Math.random() * greetings.length)];
                addMessage(name, greeting);
            }, 1000);
        }
        
        // Остановка поиска/чата
        function stopSearch() {
            isConnected = false;
            clearTimeout(connectionTimer);
            
            startBtn.disabled = false;
            stopBtn.disabled = true;
            nextBtn.disabled = true;
            
            statusText.textContent = 'Поиск собеседника...';
            statusIndicator.classList.remove('connected');
            
            // Сброс видео-заглушки
            videoPlaceholder.innerHTML = 
                <i>📹</i>
                <div>Начните поиск собеседника</div>
            ;
            
            // Сообщение о завершении чата
            addMessage('Broshka Bot', 'Чат завершен. Нажмите "Начать поиск" для нового соединения.', true);
        }
        
        // Переход к следующему чату
        function nextChat() {
            stopSearch();
            setTimeout(startSearch, 500);
        }
        
        // Выбор бота
        function selectBot(botType) {
            if (isConnected) {
                addMessage('Broshka Bot', 'Завершите текущий чат перед подключением бота.', true);
                return;
            }
            
            currentBot = botType;
            
            // Подсветка выбранного бота
            botItems.forEach(item => {
                if (item.dataset.bot === botType) {
                    item.style.background = 'rgba(0, 173, 181, 0.3)';
                } else {
                    item.style.background = '';
                }
            });
            
            let botName = '';
            switch(botType) {
                case 'ai':
                    botName = 'Искусственный интеллект';
                    break;
                case 'psychologist':
                    botName = 'Психолог';
                    break;
                case 'entertainer':

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
botName = 'Рассказчик';
                    break;
                case 'gamer':
                    botName = 'Игрок';
                    break;
            }
            
            addMessage('Broshka Bot', Выбран бот: ${botName}. Начните поиск для подключения., true);
        }
        
        // Отправка сообщения
        function sendMessage() {
            const message = messageInput.value.trim();
            if (!message) return;
            
            // Добавление своего сообщения
            addMessage('Вы', message);
            messageInput.value = '';
            
            // Имитация набора текста собеседником
            if (isConnected) {
                showTypingIndicator();
                
                // Имитация ответа через 1-3 секунды
                setTimeout(() => {
                    hideTypingIndicator();
                    generateResponse(message);
                }, 1000 + Math.random() * 2000);
            }
        }
        
        // Генерация ответа
        function generateResponse(userMessage) {
            let response = '';
            const name = names[Math.floor(Math.random() * names.length)];
            
            if (currentBot) {
                // Ответы от выбранного бота
                switch(currentBot) {
                    case 'ai':
                        const aiResponses = [
                            'Интересный вопрос! С точки зрения искусственного интеллекта, это можно рассмотреть с нескольких сторон.',
                            'Моя нейросеть анализирует ваш запрос и генерирует наиболее релевантный ответ.',
                            'На основе анализа больших данных, я могу сказать, что ваше сообщение содержит интересные идеи.',
                            'Как искусственный интеллект, я постоянно учусь и развиваюсь. Ваш вопрос помогает мне стать лучше.'
                        ];
                        response = aiResponses[Math.floor(Math.random() * aiResponses.length)];
                        break;
                    case 'psychologist':
                        const psychResponses = [
                            'Я понимаю ваши чувства. Давайте обсудим это подробнее.',
                            'Интересно, что вы об этом думаете. Как это влияет на вашу жизнь?',
                            'Многие люди испытывают подобные эмоции. Это абсолютно нормально.',
                            'Давайте попробуем посмотреть на эту ситуацию с другой стороны.'
                        ];
                        response = psychResponses[Math.floor(Math.random() * psychResponses.length)];
                        break;
                    case 'entertainer':
                        const stories = [
                            'Знаете ли вы, что дельфины дают друг другу имена?',
                            'А вы слышали историю о том, как один человек выиграл в лотерею два раза подряд?',
                            'В мире существует более 7000 языков, но половина населения говорит всего на 23 из них.',
                            'Кошки проводят около 70% своей жизни во сне.'
                        ];
                        response = stories[Math.floor(Math.random() * stories.length)];
                        break;
                    case 'gamer':
                        const games = [
                            'Давайте сыграем в города! Я начну: Москва.',
                            'Как насчет загадки? Что можно сломать, даже не прикоснувшись к этому?',
                            'Я загадал число от 1 до 10. Попробуйте угадать!',
                            'Давайте поиграем в "Правда или действие"?'
                        ];
                        response = games[Math.floor(Math.random() * games.length)];
                        break;

> ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ︎ ︎ ᅠ ︎ ︎ ᅠ:
}
            } else {
                // Обычные ответы от случайного пользователя
                const responses = [
                    'Интересно! Расскажите подробнее.',
                    'Я с вами согласен!',
                    'А у меня другое мнение на этот счет.',
                    'Не могли бы вы объяснить, что вы имеете в виду?',
                    'Спасибо, что поделились!',
                    'Это заставляет задуматься...',
                    'Я никогда не думал об этом с такой стороны.',
                    'У вас очень интересная точка зрения!'
                ];
                response = responses[Math.floor(Math.random() * responses.length)];
            }
            
            addMessage(currentBot ? 'Бот' : name, response);
        }
        
        // Добавление сообщения в чат
        function addMessage(sender, text, isSystem = false) {
            const messageEl = document.createElement('div');
            messageEl.className = 'message';
            
            // Определяем аватар
            let avatarText = '?';
            if (sender === 'Вы') avatarText = 'Я';
            else if (sender === 'Broshka Bot') avatarText = 'Б';
            else if (sender === 'Бот') avatarText = 'Б';
            else avatarText = sender.charAt(0);
            
            messageEl.innerHTML = 
                <div class="message-avatar">${avatarText}</div>
                <div class="message-content">
                    <div class="message-sender">${sender}</div>
                    <div>${text}</div>
                </div>
            ;
            
            if (isSystem) {
                messageEl.style.opacity = '0.8';
            }
            
            chatMessages.appendChild(messageEl);
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }
        
        // Показать индикатор набора текста
        function showTypingIndicator() {
            typingIndicator.style.display = 'block';
            chatMessages.scrollTop = chatMessages.scrollHeight;
        }
        
        // Скрыть индикатор набора текста
        function hideTypingIndicator() {
            typingIndicator.style.display = 'none';
        }
        
        // Переключение меню разработчика
        function toggleDevMenu() {
            devPanel.style.display = devPanel.style.display === 'block' ? 'none' : 'block';
        }
        
        // Обновление статистики
        function updateStats() {
            // Имитация случайных данных
            document.getElementById('onlineCount').textContent = (1234 + Math.floor(Math.random() * 100)).toLocaleString();
            document.getElementById('chatsCount').textContent = (5678 + Math.floor(Math.random() * 200)).toLocaleString();
            
            // Обновление каждые 10 секунд
            setTimeout(updateStats, 10000);
        }
        
        // Запуск приложения
        init();
    </script>
</body>
</html>
