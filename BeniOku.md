C:\Users\ben\.freqtrade\config.json dosyasında ayarlar yapılıyor.

Daha sonra Docker Quickstart terminal'den:

docker run --rm -v ~/.freqtrade/config.json:/freqtrade/config.json -it freqtrade



localde çalıştırmak için:

virtualenv oluşturmakta fayda var:
python -m venv .env

sonra virtualenv aktif hale getirilip:
.env\scripts\activate

TA-Lib kurulumu yapılıyor:
pip install TA_Lib-0.4.17-cp37-cp37m-win_amd64.whl


hyperopt optimizasyonu için:
python freqtrade/main.py -c config.json hyperopt --customhyperopt SampleHyperOpts -e 5000 --spaces all --refresh-pairs-cached

Strateji için:

python freqtrade/main.py -c config_binance_full.json -s Scalp

seçmece whitelist:
"BQX/BTC"


https://github.com/binance-exchange/binance-official-api-docs/blob/master/rest-api.md

------------------------------------------------------------------------------------------------------------

klines(candle) data:

https://api.binance.com/api/v1/klines?symbol=BTCUSDT&interval=1h

Örnek:

[
  [
    1499040000000,      // Open time
    "0.01634790",       // Open
    "0.80000000",       // High
    "0.01575800",       // Low
    "0.01577100",       // Close
    "148976.11427815",  // Volume
    1499644799999,      // Close time
    "2434.19055334",    // Quote asset volume
    308,                // Number of trades
    "1756.87402397",    // Taker buy base asset volume
    "28.46694368",      // Taker buy quote asset volume
    "17928899.62484339" // Ignore.
  ]
]


------------------------------------------------------------------------------------------------------------
https://api.binance.com/api/v3/bookTicker?symbol=BTCUSDT

[
  [
0 :	1565132400000       // Open time
1 :	"11325.10000000"    // Open
2 :	"11515.00000000"    // High
3 :	"11292.73000000"    // Low
4 :	"11481.69000000"    // Close
5 :	"2664.59491400"     // Volume
6 :	1565135999999       // Close time
7 :	"30451933.57305016" // Quote asset volume
8 :	20831               // Number of trades
9 :	"1462.56498000"     // Taker buy base asset volume
10:	"16711940.60967501" // Taker buy quote asset volume
11:	"0"                 // Ignore.
  ]
]

------------------------------------------------------------------------------------------------------------
https://api.binance.com/api/v1/ticker/24hr?symbol=BATBTC

symbol				: "BATBTC"
priceChange			: "0.00000068"
priceChangePercent	: "3.600"
weightedAvgPrice	: "0.00001892"
prevClosePrice		: "0.00001889"
lastPrice			: "0.00001957"
lastQty				: "712.00000000"
bidPrice			: "0.00001956"
bidQty				: "487.00000000"
askPrice			: "0.00001960"
askQty				: "284.00000000"
openPrice			: "0.00001889"
highPrice			: "0.00001962"
lowPrice			: "0.00001829"
volume				: "11675932.00000000"
quoteVolume			: "220.94392167"
openTime			: 1565078992843
closeTime			: 1565165392843
firstId				: 12942949
lastId				: 12960046
count				: 17098
