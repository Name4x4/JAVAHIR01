import requests 
import json 
url = "https://nbu.uz/en/exchange-rates/json/"
def send_req(url):
    base = requests.get(url)
    return base
def makeJson(base):
    madeJson = json.loads(base.content)
    return madeJson
def get_uzbsom(data: list):
    calc = data[8]
    summa = calc('nbu_buy_price')
    euro = int(input("euro kiriting: "))
    calculator = float(summa)*euro
    return calculator
requested_data = send_req(url)
makeJS = makeJson(requested_data)
summa = get_uzbsom(makeJS)
