```python
import pyperclip
import pyautogui
import time

def send(Msg):
	pyautogui.write(Msg)
	pyperclip.copy(Msg)
	pyautogui.hotkey("ctrl", "v")
	time.sleep(0.5)
	pyautogui.hotkey("ctrl","enter")

blessings = ["各位家长同学您好：",
						"祝您：",
						"位高权重责任轻",
						"钱多事少离家近",
						"每天睡到自然醒",
						"钞票领到手抽筋",
						"手下花钱你收礼",
						"别人加班你加薪",
						"公司日产进斗金",
						"有人打理你省心",
						"本程序由计算机智能自动化操作",
						"侵权即删",
						"此次程序随机抽取2000名微信好友1500名好友发送此次信息",
						"此次程序仅为测试"]

pyautogui.write("")
time.sleep(1)

pyperclip.copy("")
pyautogui.hotkey("ctrl","v")
pyautogui.press("enter")
time.sleep(1)
pyautogui.moveTo(x=400, y=960, duration=1)
pyautogui.click(x=400, y=960, clicks=1)
for msg in blessings:
	send(msg)
pyautogui.write("-----何胜海-----")
pyperclip.copy("-----何胜海--------------")
pyautogui.hotkey("ctrl", "v")
pyautogui.press("enter")
time.sleep(0.5)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzY0MTAyOTU2XX0=
-->