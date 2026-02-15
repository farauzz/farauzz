
import telebot

API_TOKEN = "8401761833:AAFm4jSsYZ8d6eCAfIkpAe_J9ONC-OWyfWA"

bot = telebot.TeleBot(API_TOKEN)

@bot.message_handler(commands=['start'])
def start_message(message):
    bot.send_message(message.chat.id, "Salom! Bot ishlayapti!")

# Kichik xatolik bo‘lsa, doim qayta urinadi
while True:
    try:
        bot.polling(none_stop=True)
    except Exception as e:
        print("Xato:", e)