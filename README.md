import telebot
from telebot import types

# Токен бота (получается у BotFather)
bot = telebot.TeleBot('8310757502:AAGenh6vg-57S3U2BfX7mTcYwetIY7XJyBU')

btn = types.KeyboardButton("/start")
@bot.message_handler(commands=['start']) #команда
def start_message(message):#название команды
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    btn1 = types.KeyboardButton("Химбио")
    btn2 = types.KeyboardButton("Физмат")
    btn3 = types.KeyboardButton("Гуманитарный")
    btn4 = types.KeyboardButton("Социально-экономический")
    markup.add(btn1, btn2, btn3, btn4, btn) #создание кнопк

    bot.send_message(message.chat.id, 'Бот-помощник, который подберет подходящий университет. Выберите направление:', reply_markup=markup) #вывод надписи

    @bot.message_handler(content_types=['text'])#команда
    def handle_text(message):#название команды
        text = message.text
    #если текст "Химбио", "Химия", "Биология", "Химия или биология", "Физмат", "Математика", "Физика и Математика" выдает ниже сообщения
        if text in ("Химбио", "Химия", "Биология", "Химия или биология", "Физмат", "Математика", "Физика и Математика"):
            bot.send_message(message.chat.id, 'Брянский государственный университет имени академика И.Г. Петровского - химия и биология, физика и математика.  [Сайт](https://yandex.ru/maps/org/bryanskiy_gosudarstvenny_universitet_imeni_i_g_petrovskogo/1069505420/?ll=34.352519%2C53.272284&z=16/)', parse_mode='Markdown')
            bot.send_message(message.chat.id, 'Брянский государственный технический университет - химия и биология, физика и математика (частично). [Сайт](https://yandex.ru/maps/org/bryanskiy_gosudarstvenny_tekhnicheskiy_universitet/1694101942/?ll=34.304018%2C53.304648&z=14)', parse_mode='Markdown')
    # если текст Гуманитарный выдает институты по гуманетарному профилю
        elif text == "Гуманитарный":
            bot.send_message(message.chat.id, 'Брянский государственный университет имени академика И.Г. Петровского - широкий спектр гуманитарных специальностей. [Сайт](https://yandex.ru/maps/org/bryanskiy_gosudarstvenny_universitet_imeni_i_g_petrovskogo/1069505420/reviews/?ll=34.352519%2C53.272284&z=16)', parse_mode='Markdown')
            bot.send_message(message.chat.id, 'Брянский филиал Российского государственного университета правосудия - юридические направления. [Сайт](https://yandex.ru/maps/org/bryanskiy_gosudarstvenny_universitet_imeni_i_g_petrovskogo/1069505420/reviews/?ll=34.352519%2C53.272284&z=16)', parse_mode='Markdown')
            bot.send_message(message.chat.id, 'Брянский филиал Московского финансово-юридического университета - экономика, право, гуманитарные науки. [Сайт(https://yandex.ru/maps/org/finansovy_universitet_filial/39132074099/?ll=34.356476%2C53.261982&z=14)', parse_mode='Markdown')
            bot.send_message(message.chat.id, 'Брянский институт управления - гуманитарные направления. [Сайт](https://yandex.ru/maps/org/bryanskiy_institut_upravleniya_i_biznesa/201935619773/?ll=34.317387%2C53.238971&mode=search&sctx=ZAAAAAgBEAAaKAoSCcTuO4bHCEFAEQ8Ni1HXpkpAEhIJK1H2lnK%2BsD8RVFVoIJbNpD8iBgABAgMEBSgKOABAn4MGSAFqAnJ1nQHNzMw9oAEAqAEAvQENzNypwgEGvY20ovAFggJo0JHRgNGP0L3RgdC60LjQuSDQuNC90YHRgtC40YLRg9GCINGD0L%2FRgNCw0LLQu9C10L3QuNGPIC0g0LPRg9C80LDQvdC40YLQsNGA0L3Ri9C1INC90LDQv9GA0LDQstC70LXQvdC40Y%2BKAgCSAgCaAgxkZXNrdG9wLW1hcHM%3D&sll=34.317387%2C53.238971&source=serp_navig&sspn=0.348816%2C0.129348&text=Брянский%20институт%20управления%20-%20гуманитарные%20направления&z=12)', parse_mode='Markdown')
            bot.send_message(message.chat.id, 'Брянский филиал Современной гуманитарной академии - гуманитарные программы. [Сайт](https://yandex.ru/maps/org/sovremennaya_gumanitarnaya_akademiya_bryanskiy_filial/1439527635/?ll=34.347633%2C53.252614&z=16)', parse_mode='Markdown')
    # если текст Социально-экономический выдает институты по Социально-экономическискому профилю
        elif text == "Социально-экономический":
            bot.send_message(message.chat.id, 'Брянский государственный университет имени академика И.Г. Петровского - экономика и управление. [Сайт](https://yandex.ru/maps/191/bryansk/?ll=34.326765%2C53.264765&mode=routes&rtext=53.263005%2C34.296636~53.273894%2C34.353858&rtt=auto&ruri=ymapsbm1%3A%2F%2Fgeo%3Fdata%3DCgg1MzA1NTc2MRJ-0KDQvtGB0YHQuNGPLCDQkdGA0Y_QvdGB0LrQuNC5INGA0LDQudC-0L0sINCh0L3QtdC20YHQutC-0LUg0YHQtdC70YzRgdC60L7QtSDQv9C-0YHQtdC70LXQvdC40LUsINC_0L7RgdGR0LvQvtC6INCf0YPRgtGR0LLQutCwIgoNwi8JQhVRDVVC~ymapsbm1%3A%2F%2Forg%3Foid%3D208990149170&z=14.53)', parse_mode='Markdown')
            bot.send_message(message.chat.id, 'Брянский государственный технический университет - программы, связанные с экономикой и управлением. [Сайт](https://yandex.ru/maps/org/bryanskiy_gosudarstvenny_tekhnicheskiy_universitet/1694101942/?ll=34.304018%2C53.304648&z=14)', parse_mode='Markdown')
            bot.send_message(message.chat.id, 'Брянский филиал Российского экономического университета имени Г.В. Плеханова - экономика и финансы. [Сайт](https://yandex.ru/maps/org/rossiyskiy_ekonomicheskiy_universitet_imeni_g_v_plekhanova_bryanskiy_filial/85352088442/?ll=34.354523%2C53.270512&z=16)', parse_mode='Markdown')


bot.polling(none_stop=True) # Запуск бота
