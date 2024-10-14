# grammY Telegram Bot Starter

This is a starter project for creating Telegram bots using the grammY framework, with easy deployment to Zeabur.

## Features

- Built with grammY framework
- Middleware for response time measurement
- Session management
- Robust error handling for both webhook and long polling modes
- Interactive counter with inline keyboard
- Easy deployment to Zeabur

## Getting Started

1. Clone this repository
2. Install dependencies:
   ```
   npm install
   ```
3. Create a `.env` file in the root directory and add your Telegram Bot Token:
   ```
   BOT_TOKEN=your_bot_token_here
   ```
4. Run the bot in development mode:
   ```
   npm run dev
   ```

## Project Structure

- `src/bot.js`: Main bot file with command handlers and error handling
- `src/middleware/logger.js`: Custom middleware for response time measurement
- `.env`: Environment variables (don't commit this file)
- `Procfile`: For Zeabur deployment

## Available Commands

- `/start`: Welcome message
- `/help`: List available commands
- `/count`: Display an interactive counter with inline keyboard
- `/error`: Test error handling (throws a test error)

## Interactive Counter

The `/count` command displays an interactive counter with the following inline keyboard buttons:

- `+`: Increment the counter
- `-`: Decrement the counter
- `🔄 Reset`: Reset the counter to 0

## Deployment to Zeabur

1. Create a new project on Zeabur
2. Connect your GitHub repository
3. Set the following environment variables in Zeabur:
   - `BOT_TOKEN`: Your Telegram Bot Token
   - `NODE_ENV`: Set to "production"
4. Deploy your project

Note: The host URL is automatically provided by Zeabur. You don't need to set it manually. Zeabur will handle the webhook setup for you.

## Error Handling

This starter includes robust error handling for both webhook and long polling modes:

- In production (webhook mode):

  - Errors are logged but don't stop the bot
  - The server always responds with a 200 status to acknowledge receipt of the update

- In development (long polling mode):
  - Errors are logged
  - The bot stops on critical errors (GrammyError or HttpError) to prevent infinite error loops

To test error handling, use the `/error` command when interacting with the bot.

## Customization

To add new features or commands to your bot:

1. Add new command handlers in `src/bot.js`
2. Create new middleware functions in `src/middleware/` if needed
3. Update the README with any new commands or features

## Contributing

Feel free to submit issues or pull requests if you have suggestions for improvements or find any bugs.

## License

This project is open-source and available under the MIT License.

## Русская версия (Russian Version)

Это стартовый проект для создания Telegram-ботов с использованием фреймворка grammY и простым развертыванием на Zeabur.

### Особенности

- Построен на фреймворке grammY
- Промежуточное ПО для измерения времени отклика
- Управление сессиями
- Надежная обработка ошибок для режимов webhook и long polling
- Интерактивный счетчик с встроенной клавиатурой
- Простое развертывание на Zeabur

### Начало работы

1. Клонируйте этот репозиторий
2. Установите зависимости:
   ```
   npm install
   ```
3. Создайте файл `.env` в корневой директории и добавьте ваш токен Telegram-бота:
   ```
   BOT_TOKEN=ваш_токен_бота_здесь
   ```
4. Запустите бота в режиме разработки:
   ```
   npm run dev
   ```

### Доступные команды

- `/start`: Приветственное сообщение
- `/help`: Список доступных команд
- `/count`: Отображение интерактивного счетчика с встроенной клавиатурой
- `/error`: Тестирование обработки ошибок (вызывает тестовую ошибку)

Для получения дополнительной информации о структуре проекта, развертывании и настройке, пожалуйста, обратитесь к английской версии README выше.
