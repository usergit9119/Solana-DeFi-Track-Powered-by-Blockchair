 <h1>RU</h1>
 <h1>Инструменты для работы с DeFi и ценами токенов на Solana</h1>
    <h2>Обзор</h2>
    <p>Этот репозиторий содержит два инструмента для взаимодействия с децентрализованными финансовыми протоколами (DeFi) и децентрализованными биржами (DEX) на блокчейне Solana. Проект включает два основных компонента:</p>
    <ul>
        <li><strong>Инструмент для получения статистики аккаунта в DeFi</strong> (Задача 1): Получает информацию о средствах, заблокированных в различных протоколах DeFi на Solana, а также данные о доходах и убытках.</li>
        <li><strong>Инструмент для получения цен токенов с DEX</strong> (Задача 2): Получает актуальные цены токенов непосредственно с децентрализованных бирж (DEX) на Solana без использования сторонних сервисов, таких как CoinGecko или CoinMarketCap.</li>
    </ul>
    <h2>Особенности</h2>
    <h3>Задача 1 - Статистика аккаунта в DeFi</h3>
    <ul>
        <li>Получает статистику аккаунта в популярных протоколах DeFi на Solana (Hubble, Solend).</li>
        <li>Данные включают количество заблокированных средств и информацию о доходах и убытках.</li>
        <li>Использует Solana Node API для взаимодействия с блокчейном.</li>
        <li>Ответы возвращаются в формате JSON с подробной статистикой по протоколам для аккаунта.</li>
    </ul>
    <p><strong>Пример запроса:</strong></p>
    <pre><code>curl localhost/?account=5iC1yoXYmUGsGBBLSKTgedya4cjQokaD3DxYoUTozz3c</code></pre>
    <p><strong>Пример ответа:</strong></p>
    <pre><code>{
  "hubble_protocol": {
    "deposited": {"USD": 5000, "SOL": 3500},
    "earned": {"USD": 100, "SOL": 50}
  }
}</code></pre>
    <h3>Задача 2 - Цены токенов с Solana DEX</h3>
    <ul>
        <li>Получает актуальные цены токенов с популярных DEX на Solana (Raydium, Jupiter).</li>
        <li>Использует только Solana Node API и данные протоколов DEX.</li>
        <li>Ответ в формате JSON содержит тикеры токенов, цены и информацию о десятичных знаках для каждого DEX.</li>
    </ul>
    <p><strong>Пример запроса:</strong></p>
    <pre><code>curl localhost/?token0=USDH</code></pre>
    <p><strong>Пример ответа:</strong></p>
    <pre><code>{
 "phoenix": {
    "token0": "USDH", 
    "token1": "USDT", 
    "price0": 1000005, 
    "price1": 999985, 
    "decimals0": "18", 
    "decimals1": 18
 }
}</code></pre>
    <h2>Технологии</h2>
    <ul>
        <li><strong>Язык программирования:</strong> Python 3</li>
        <li><strong>Solana Node API</strong> для взаимодействия с блокчейном</li>
        <li><strong>PostgreSQL</strong> для хранения данных (опционально)</li>
        <li><strong>Docker</strong> для контейнеризации и развертывания</li>
    </ul>
    <h2>Структура проекта</h2>
    <pre><code>/solana-defi-tool
│
├── /src
│   ├── /api                   # API для взаимодействия с Raydium и другими DEX
│   ├── /services              # Логика обработки данных
│   ├── /models                # Модели данных и DTO
│   ├── /db                    # Логика подключения к базе данных (если используется)
│   └── app.py                 # Основной файл приложения
│
├── /config                    # Конфигурационные файлы
│   └── config.py              # API ключи и настройки окружения
│
├── /tests                     # Модульные и интеграционные тесты
├── /docker                    # Dockerfile для настройки контейнера
├── README.md                  # Описание проекта и инструкции по запуску
└── requirements.txt           # Зависимости для Python
</code></pre>
    <h2>Настройка и запуск</h2>
    <p>1. Клонируйте репозиторий:</p>
    <pre><code>git clone git@github.com:usergit9119/Solana-DeFi-Track-Powered-by-Blockchair.git
cd solana-defi-tool</code></pre>
    <p>2. Установите зависимости:</p>
    <pre><code>pip install -r requirements.txt</code></pre>
    <p>3. Запустите приложение локально:</p>
    <pre><code>python src/app.py</code></pre>
    <p>4. Для запуска через Docker:</p>
    <pre><code>docker build -t solana-defi-tool .
docker run -p 80:80 solana-defi-tool</code></pre>
    <h2>Тестирование</h2>
    <p>Для запуска тестов:</p>
    <pre><code>pytest</code></pre>

<h2>EN</h2>
<h1>Solana DeFi Stats and Token Price Tools</h1>
    <h2>Overview</h2>
    <p>This repository contains two tools for interacting with decentralized finance (DeFi) protocols and decentralized exchanges (DEX) on the Solana blockchain. The project consists of two main components:</p>
    <ul>
        <li><strong>DeFi Account Statistics Tool</strong> (Task 1): Retrieves information about how much money is locked in various DeFi protocols on Solana and provides data on income and losses.</li>
        <li><strong>Token Price Retrieval Tool from DEX</strong> (Task 2): Fetches token prices directly from decentralized exchanges (DEX) on Solana without relying on third-party services like CoinGecko or CoinMarketCap.</li>
    </ul>
    <h2>Features</h2>
    <h3>Task 1 - DeFi Account Statistics</h3>
    <ul>
        <li>Retrieves account statistics across popular DeFi protocols on Solana (Hubble, Solend).</li>
        <li>The data includes the amount of funds locked in each protocol, as well as earnings and losses.</li>
        <li>Uses the Solana Node API to interact with the blockchain.</li>
        <li>Responses are returned in JSON format with detailed protocol statistics for the account.</li>
    </ul>
    <p><strong>Example Request:</strong></p>
    <pre><code>curl localhost/?account=5iC1yoXYmUGsGBBLSKTgedya4cjQokaD3DxYoUTozz3c</code></pre>
    <p><strong>Example Response:</strong></p>
    <pre><code>{
  "hubble_protocol": {
    "deposited": {"USD": 5000, "SOL": 3500},
    "earned": {"USD": 100, "SOL": 50}
  }
}</code></pre>
    <h3>Task 2 - Token Prices from Solana DEX</h3>
    <ul>
        <li>Retrieves current token prices from popular DEXes on Solana (Raydium, Jupiter).</li>
        <li>Uses only the Solana Node API and the DEX protocol data.</li>
        <li>The JSON response includes token tickers, prices, and decimals for each DEX.</li>
    </ul>
    <p><strong>Example Request:</strong></p>
    <pre><code>curl localhost/?token0=USDH</code></pre>
    <p><strong>Example Response:</strong></p>
    <pre><code>{
 "phoenix": {
    "token0": "USDH", 
    "token1": "USDT", 
    "price0": 1000005, 
    "price1": 999985, 
    "decimals0": "18", 
    "decimals1": 18
 }
}</code></pre>
    <h2>Technologies</h2>
    <ul>
        <li><strong>Programming language:</strong> Python 3</li>
        <li><strong>Solana Node API</strong> for blockchain interaction</li>
        <li><strong>PostgreSQL</strong> for data storage (optional)</li>
        <li><strong>Docker</strong> for containerization and deployment</li>
    </ul>
    <h2>Project Structure</h2>
    <pre><code>/solana-defi-tool
│
├── /src
│   ├── /api                   # API interaction (Raydium and other DEX)
│   ├── /services              # Data processing logic
│   ├── /models                # Data models and DTOs
│   ├── /db                    # Database connection logic (if used)
│   └── app.py                 # Main application file
│
├── /config                    # Configuration files
│   └── config.py              # API keys and environment settings
│
├── /tests                     # Unit and integration tests
├── /docker                    # Dockerfile for container setup
├── README.md                  # Project description and setup instructions
└── requirements.txt           # Python dependencies
</code></pre>
    <h2>Setup and Running</h2>
    <p>1. Clone the repository: git clone git@github.com:usergit9119/Solana-DeFi-Track-Powered-by-Blockchair.git</p>
    <pre><code>git clone 
cd solana-defi-tool</code></pre>
    <p>2. Install dependencies:</p>
    <pre><code>pip install -r requirements.txt</code></pre>
    <p>3. Run the application locally:</p>
    <pre><code>python src/app.py</code></pre>
    <p>4. To run using Docker:</p>
    <pre><code>docker build -t solana-defi-tool .
docker run -p 80:80 solana-defi-tool</code></pre>
    <h2>Testing</h2>
    <p>To run tests:</p>
    <pre><code>pytest</code></pre>
