#! /usr/bin/env python
# -*- coding: utf-8 -*-
import socket
import re
import random
from time import sleep


HOST = "irc.twitch.tv"
PORT = 6667
NICK = "TestTwitchBot"
PASS = "oauth:0j8l9g3kjzirj85773m7e6hj1urgk7"
CHAN = "tekkq"
RATE = (20 / 30)

oplist = {}


def mess(sock, message):
    sock.send("PRIVMSG #{} :{}\r\n".format(CHAN, message))


def main():
    print(u"\n\n\n\n\n\n\n\n\n\t\t\t\tБот успешно запущен")
    s = socket.socket()
    s.connect((HOST, PORT))
    s.send("PASS {}\r\n".format(PASS).encode("utf-8"))
    s.send("NICK {}\r\n".format(NICK).encode("utf-8"))
    s.send("JOIN #{}\r\n".format(CHAN).encode("utf-8"))

    chat_message = re.compile(r"^:\w+!\w+@\w+\.tmi\.twitch\.tv PRIVMSG #\w+ :")

    while True:
        response = s.recv(1024).decode("utf-8")
        if response == "PING :tmi.twitch.tv\r\n":
            s.send("POND :tmi.twitch.tv\r\n".encode("utf-8"))
        else:
            message = chat_message.sub("", response)

            if message.strip() == u"!инсайд":
                number = random.randint(1, 11)
                if number == 1:
                    mess(s, "Гитлер тоже пил воду, как и ты.")
                elif number == 2:
                    mess(s, "Дима не рыжий.")
                elif number == 3:
                    mess(s, "Дима фанат Пошлой Молли.")
                elif number == 4:
                    mess(s, "Кате 44 года.")
                elif number == 5:
                    mess(s, "Катя лучший стример.")
                elif number == 6:
                    mess(s, "Максим - женщина.")
                elif number == 7:
                    mess(s, "Максим забирает все деньги с донатов.")
                elif number == 8:
                    mess(s, "У Кати нет друзей. :(")
                elif number == 9:
                    mess(s, "У Максима жопа воняет.")
                elif number == 10:
                    mess(s, "Чтобы жизнь стала лучше - надо задонатить стримеру.")
                else:
                    mess(s, "Шутка про три арбуза не смешная.")
        sleep(1)


if __name__ == "__main__":
    main()
