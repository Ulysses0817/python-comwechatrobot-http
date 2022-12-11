```
from wechatrobot import WeChatRobot

ip = '127.0.0.1'
port = 18888
socket_ip = '0.0.0.0'
socket_port = 10808
BASE_PATH = 'C:\\Users\\user\\My Documents\\WeChat Files'

bot = WeChatRobot(ip = ip, port = port, socket_ip = socket_ip, socket_port = socket_port, BASE_PATH = BASE_PATH)

@bot.on("friend_msg")
def on_friend_msg(msg):
    bot.SendText(wxid = msg['sender'], msg = msg['message'])

@bot.on("group_msg")
def on_group_msg(msg):
    print(f"on_group_msg: {msg}")

@bot.on("self_msg")
def on_self_msg(msg):
    print(f"on_self_msg: {msg}")

bot.run()
```
