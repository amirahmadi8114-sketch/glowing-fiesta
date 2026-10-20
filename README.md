import os
import telebot

TOKEN = os.environ.get("BOT_TOKEN")
bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=["start"])
def start(message):
    bot.reply_to(
        message,
        "سلام! به فروشگاه بین‌المللی ما خوش آمدی 🌍\n"
        "Welcome to our international marketplace!\n\n"
        "برای دیدن محصولات /products را بزن.\n"
        "Send /products to browse products."
    )

@bot.message_handler(commands=["products"])
def products(message):
    bot.reply_to(
        message,
        "🛍️ برای ثبت محصول یا درخواست مشاوره با مدیریت تماس بگیر.\n"
        "Contact the admin to list a product or request consultation."
    )

bot.infinity_polling()
