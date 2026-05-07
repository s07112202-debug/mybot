from telegram import Update
from telegram.ext import Application, CommandHandler, ContextTypes

TOKEN = "8720760354:AAEAovHYcXyxJHl2i1hsDUcGVv7g9FWdPBE"

VIDEO_ID = "BAACAgIAAxkBAAFI9i5p--4edSZsT-nePc8J4HMY3cDcDAACpKMAAqOi4UuZwlGTJcvWGzsE"

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_video(
        video=VIDEO_ID,
        caption="✅ البوت يعمل"
    )

app = Application.builder().token(TOKEN).build()

app.add_handler(CommandHandler("start", start))

print("✅ Bot Started")

app.run_polling()
