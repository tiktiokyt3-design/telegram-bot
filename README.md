# telegram-bot

from telegram.ext import Updater, CommandHandler

# Твій токен від BotFather
TOKEN = "7377335524:AAHM1DfWje4UoiR0e6BqZfxlz1oXHBJs5e4"

# Функція відповіді на /start
def start(update, context):
    update.message.reply_text("Привіт 👋 Я твій перший бот!")

# Функція відповіді на /help
def help_command(update, context):
    update.message.reply_text("Команди:\n/start - почати\n/help - допомога")

def main():
    updater = Updater(TOKEN, use_context=True)
    dp = updater.dispatcher

    # Команди
    dp.add_handler(CommandHandler("start", start))
    dp.add_handler(CommandHandler("help", help_command))

    # Запуск
    updater.start_polling()
    updater.idle()

if __name__ == "__main__":
    main()
