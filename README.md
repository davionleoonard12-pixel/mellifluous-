import telebot
import random

TOKEN = "8548437636:AAFz72vRxwrs54-7FPsdOkbwv9WQEoO9xcw"

bot = telebot.TeleBot(TOKEN)

commands = {

"whgy":"CAACAgUAAxkBAAJtbWmm1_qH0KCY53nSXzE8J7LiKk-UAAKMGgACrnaQV5zEucC9eTC5OgQ",
"oehk":"CAACAgUAAxkBAAJtb2mm2DRAhpKGV6gPG6lkmsFwRT9sAAIvHAAConGZV0ZEzoFGjTsCOgQ",
"rchg":"CAACAgUAAxkBAAJtcWmm2O_c--1IeIZ8-MkKDFiCru9DAAJsGwACZ6eZV8AqczoFx_OJOgQ",
"tqdh":"CAACAgUAAxkBAAJtc2mm2RLYd6yKyGT_iPhgvWpG_ta9AALcGgACseeYVz5EwNXs0s4COgQ",
"ykjp":"CAACAgUAAxkBAAJtdWmm2Tp9I52hm2NKPU_WdGXYhBiMAAK8HQACQDqQVxZDx2KEKtLROgQ",
"phy":"CAACAgUAAxkBAAJtd2mm2gq6IKl7Um0WwwMPnWN1n3w5AALtHQACfCSYV_oYEc6GS5_jOgQ",
"uixv":"CAACAgUAAxkBAAJteWmm2i6FpUkb4v-Jqj7KF-US_gUQAAKZHgACMjGZVz59DLtsyIEOOgQ",
"gvf":"CAACAgUAAxkBAAJtf2mm2yVJKD5HbGJ8zMGiYBCT-QlZAAI2HwACtwMwVU2sd8nU7v2BOgQ",
"okuh":"CAACAgUAAxkBAAJtgWmm27Bq_OKUQ44E-e8xcVyliTNOAALnHQAD_zlVab70UBOFULc6BA",
"pgh":"CAACAgUAAxkBAAJtjWmm3HgHVaXFPobef9jxOHlJ-UXQAAJyGgACxFYwVfny7mxIU6QlOgQ",
"kohj":"CAACAgUAAxkBAAJtk2mm3U2m6jp79C06uB16YNBbZTqnAALvHQACYCWRVyMXKpUxNiNcOgQ",
"kjy":"CAACAgUAAxkBAAJtlWmm3XAWdRcwQDLS9nNY1dZqowaPAALTGwAC5SuZVzffAuUEQnhvOgQ",
"powh":"CAACAgUAAxkBAAJtl2mm3ZOsnrif-4A8-wTrL70oHwstAAJWIQACCK6QVwFVmiL82NQnOgQ",
"hvsyh":"CAACAgUAAxkBAAJtmWmm3fvc0aiJA4enCKbjbQ0u4ydrAAJ3JAACZIyZV3t12J45zMglOgQ",
"bhs":"CAACAgUAAxkBAAJtm2mm3hmG9KW4cUsoWl8-KiedfssUAALrHQACt2ORV-vW34cz97t6OgQ",
"mna":"CAACAgUAAxkBAAJtnWmm3kSW9EKiSRYon3e_CDrdNUHuAALQGQAC50qRV_Nl4SOUJ0kdOgQ",
"qdt":"CAACAgUAAxkBAAJtn2mm3mS2bayL3oHINFrvqQlnAzslAAIkIQACyNCQV4JUJnnEtaQcOgQ",
"hjg":"CAACAgUAAxkBAAJtoWmm3okgwBc2jtvM7rbWe8NTc3x8AAIXIAACdMQ4VVlQBT-l0ko0OgQ",
"rtg":"CAACAgUAAxkBAAJto2mm3rakF5J-C8wDTnz6D4NUeKDHAAIpIgAC61kJVXkqvfJcHoHaOgQ",
"vcg":"CAACAgUAAxkBAAJtp2mm4HsaUJUFjfZIV1p5WMh43oU6AAImMAACc-g5VQnlLjehPeIuOgQ",
"gdh":"CAACAgUAAxkBAAJtqWmm4K4g01Em9zA3Pvdw4vg5AmnAAAIkIQACFxEJVeOlkLEzUHy-OgQ",
"jjg":"CAACAgUAAxkBAAJtq2mm4NPogbUcfDPLA0nhr0sgUpMKAALIGwACrD05VQsRgbg5RZx4OgQ",
"chg":"CAACAgUAAxkBAAJtrWmm4PH3AkGOYZZejwMKUb1copirAAIxIgACE9c5VR3XFMvIeRJxOgQ",
"cdt":"CAACAgUAAxkBAAJtr2mm4RIZ4ED9faU5lIdv-xjvZtPFAAJgHQAClogJVdHkWtmwg2mnOgQ",
"cpo":"CAACAgUAAxkBAAJtsWmm4UIayPyF2L07eOVWB2J-659xAAIxGQACz5A5VaIDAq0mgmrNOgQ",
"qtyk":"CAACAgUAAxkBAAJts2mm4WdzzjCOgVTKGRtLb2FopBwKAAKWHgACM9YIVYvFG9kDeGl5OgQ",
"chgu":"CAACAgUAAxkBAAJtpWmm4GdxiR2Pv-uH18qwzZqJDPdIAAIPHQACzJUwVYFu18ZwznfnOgQ",
"dsh":"CAACAgUAAxkBAAJtt2mm4gy04W8w9BYzRZ2Ivt4KXBsrAAJGHwACaeoJVemzc_rY7KGVOgQ",
"khj":"CAACAgUAAxkBAAJtuWmm4iZhu7JDM5Gxj-JfZ0WRCTafAAJ6HAACnqEIVUmLTKYnd5GqOgQ",
"pqrj":"CAACAgUAAxkBAAJta2mm16a0BNAalIGpxSjKGaHAhRG1AALJGgACpoyZVwpG3R8jGIpFOgQ",
"jrm":"CAACAgUAAxkBAAJusWmn6vkm-3xmM2A369H_AvRUl-6sAAKSGwAC0qsIVY1mBj8HX-hROgQ"

}

bot_reply = [
"Apa manggil manggil?",
"Kangen ya?",
"Aku disini kok",
"Ada apa?",
"iya sayang",
"adek lagi sibuk!",
"ihh manggil terus *cemberut",
"Iya?"
]

def get_cmd(text):
    return text.split()[0].lower()

@bot.message_handler(func=lambda m: m.text and m.text.startswith("."))
def handler(message):

    cmd = get_cmd(message.text[1:])

    if cmd == "bot":
        bot.reply_to(message, random.choice(bot_reply))
        return

    if cmd == "list":
        text = "\n".join(commands.keys())
        bot.reply_to(message,text)
        return

    if cmd in commands:

        data = commands[cmd]

        if data.startswith("CAAC"):
            bot.send_sticker(message.chat.id,data)
        else:
            bot.send_message(message.chat.id,data)

bot.infinity_polling()
