import telebot
from telebot import types
bot = telebot.TeleBot('5723573421:AAH_ML9TkDbDXbcLuhdRh28QVVdt1z3Br-w')

@bot.message_handler(commands=['start'])
def start(message):
    mess = f'Hello, <b>{message.from_user.first_name} <u>{message.from_user.last_name}</u></b>'
    bot.send_message(message.chat.id, mess, parse_mode='html')

@bot.message_handler(content_types=['text'])
def get_user_text(message):
    if message.text == 'Hello':
        bot.send_message(message.chat.id, "Hello, how are you?", parse_mode='html')
    elif message.text == "id":
        bot.send_message(message.chat.id, f"It's your ID: {message.from_user.id}", parse_mode='html')
    elif message.text == "photo":
        photo = open('1011.png', 'rb')
        bot.send_photo(message.chat.id, photo)
    else:
        bot.send_message(message.chat.id, "I don't understand you", parse_mode='html')

@bot.message_handler(content_types=['photo'])
def get_user_photo(message):
    bot.send_message(message.chat.id, 'wow cool photo')

@bot.message_handler(commands=['website'])
def website(message):
    markup = types.InlineKeyboardMarkup()
    markup.add(types.InlineKeyboardButton('visit the website', url="https://google.com"))
    bot.send_message(message.chat.id, 'you can find all', reply_markup=markup)

@bot.message_handler(commands=['help'])
def website(message):
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True, row_width=1)
    website = types.KeyboardButton('website')
    start = types.KeyboardButton('start')
    markup.add(website, start)
    bot.send_message(message.chat.id, 'you can find all', reply_markup=markup)

bot.polling(none_stop=True )