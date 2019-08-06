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

hata mesajı:
