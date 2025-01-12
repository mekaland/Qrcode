QR Code Generator

Bu proje, Python kullanarak bir QR kodu oluşturur. Bu QR kodu belirli bir URL'yi veya metni temsil eder ve bir PNG dosyası olarak kaydedilir.

Özellikler

QR kodu oluşturma.

QR kodunu PNG formatında kaydetme.

Gereksinimler

Projenin çalışabilmesi için aşağıdaki Python kütüphanelerinin yüklenmiş olması gerekir:

qrcode

Pillow (image modülü için)

Bu kütüphaneleri yüklemek için:

pip install qrcode[pil]

Kod

Aşağıdaki Python kodu bir QR kodu oluşturur ve "test.png" adıyla kaydeder:

import qrcode
import image

# QR Code nesnesini oluştur
qr = qrcode.QRCode(
    version=15,  # Versiyon, QR kodunun karmaşıklığını belirler
    box_size=10, # Her bir kutunun piksel boyutu
    border=5     # Kenarlık kalınlığı (kutu cinsinden)
)

data = "https://www.instagram.com/kadir._.dagli/" # QR kodunda yer alacak veri

qr.add_data(data)
qr.make(fit=True)

# QR kodunu oluştur ve renklerini ayarla
img = qr.make_image(fill="black", back_color="white")

# QR kodunu kaydet
img.save("test.png")

Nasıl Çalıştırılır

Yukarıdaki kodu bir Python dosyası (örneğin, qr_generator.py) olarak kaydedin.

Python yüklenmiş bir ortamda şu komutla çalıştırın:

python qr_generator.py

Kod çalıştığında proje dizininde test.png adında bir dosya oluşacaktır.

Oluşan test.png dosyasını açarak QR kodunu tarayabilirsiniz.

Parametreler

version: QR kodunun karmaşıklığını belirler. Daha yüksek bir değer, daha fazla veri saklanmasına izin verir.

box_size: QR kodundaki her bir kutunun piksel boyutunu belirler.

border: QR kodunun etrafındaki kenarlığın boyutunu belirler (kutu sayısı cinsinden).

QR Kodunun Temsil Ettiği Veri

Bu örnek kodda QR kodu, aşağıdaki Instagram profilini temsil etmektedir:
https://www.instagram.com/kadir._.dagli/
