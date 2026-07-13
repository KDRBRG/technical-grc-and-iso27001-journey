📑 Bilgi Güvenliği ve Teknik GRC Temelleri Çalışma Notları
Bu döküman; bilgi güvenliği politikalarından teknik kontrol mekanizmalarına, ISO 27001:2022 standartlarından kurumsal denetim süreçlerine kadar uzanan temel ve ileri düzey siber güvenlik konseptlerini içermektedir.

📘 Bölüm 1: Bilgi Güvenliği Politikası, Mekanizma ve Unsurları
1. Güvenlik Politikası (Security Policy)
Güvenlik politikası, bir organizasyonda hangi eylemlerin olumlu (uygun), hangilerinin olumsuz (uygunsuz) olduğunu belirleyen resmi bir beyandır.

Amaç: Kurumsal işleyişe sınırlar ve kurallar getirerek güvenliği belirli bir çerçevede yasal zemine oturtur.

Teori - Uygulama İlişkisi: Teori ile uygulama arasındaki boşluklar, sistemlerde güvenlik açıklarının (vulnerabilities) oluşmasına neden olur.

2. Güvenlik Mekanizmaları
Politikaların kağıt üzerinde kalmaması ve zorunlu tutulması için kullanılan araç, yöntem ve izleme süreçleridir. İki ana gruba ayrılır:

A. Teknik Mekanizmalar:

Kriptografi: Verilerin şifrelenmesi ve anahtar yönetimi.

Erişim Kontrolleri: Sanal Özel Ağlar (VPN), Güvenlik Duvarları (Firewall).

Zararlı Yazılım Koruması: Virüs koruma (Antivirüs/EDR) yazılımları.

Dijital İmza (e-İmza): Kimlik ve bütünlük doğrulama araçları.

B. Teknik Olmayan (Yönetimsel/Fiziksel) Mekanizmalar:

Dokümantasyon ve Sözleşmeler: İşe alım süreçlerinde imzalatan gizlilik sözleşmeleri (NDA) ve arka plan kontrolleri.

Fiziksel Güvenlik: Sunucu odalarının kilitleri, biyometrik geçiş sistemleri ve fiziksel bariyerler.

🎯 Bölüm 2: Bilgi Güvenliği İlkeleri (CIA Triad ve Diğer Unsurlar)
1. Temel Üçlü (CIA Triad)
Bilgi varlıklarının güvenliğini sağlamanın temelini oluşturan üç ana unsur:

Gizlilik (Confidentiality): Bilginin yetkisiz kişilerin eline geçmesinin engellenmesidir. (Örn: Veri tabanı şifrelemesi, yetkilendirme).

Bütünlük (Integrity): Bilginin yetkisiz veya yetkili kişilerce izinsiz/hatalı olarak değiştirilmesinin önlenmesidir.

Erişilebilirlik (Availability): Bilginin yetkili kullanıcılar tarafından ihtiyaç duyulduğu her an ulaşılabilir olmasıdır. (Örn: Yedekleme sistemleri, DDoS koruması).

💻 Teknik Laboratuvar: PowerShell ile Veri Bütünlüğü Doğrulaması
Sistemlerdeki verilerin veya konfigürasyon dosyalarının Bütünlük (Integrity) ilkesini koruyup korumadığını kontrol etmek için kriptografik özet (Hash) algoritmaları kullanılır.

Senaryo Uygulaması:

Yeni Dosya Oluşturma: cd Desktop ile masaüstüne geçilir ve yeni bir metin belgesi oluşturulur:

PowerShell
New-Item Asil.txt
Dosya İçeriğini Doldurma: Dosyanın içerisine orijinal veri yazılır:

PowerShell
Set-Content Asil.txt "Dosyanın İçeriği"
Orijinal Hash Değerini Alma: MD5 algoritması kullanılarak dosyanın benzersiz hash değeri üretilir:

PowerShell
Get-FileHash Asil.txt -Algorithm MD5
Bütünlük Kontrolü: Dosya içeriğinde küçük bir değişiklik (Data Alteration) yapıldığında veya dışarıdan bir saldırgan dosyaya müdahale ettiğinde hash değeri tamamen değişir. Sistem bu iki değeri kıyaslayarak bütünlüğün bozulduğunu tespit ve kontrol eder.

2. Diğer Bilgi Güvenliği Unsurları
Sorumlu Tutulabilirlik (Accountability): Sistemde kimin, ne zaman, hangi işlemi yaptığının (Log/Kayıt mekanizmaları ile) inkar edilemez şekilde tutulmasıdır.

Kimlik Doğrulama (Authentication): Sisteme girmeye çalışan kişinin iddia ettiği kişi olduğunun kanıtlanmasıdır (Parola, MFA, Biyometri).

Mahremiyet (Privacy): Kişilerin kendilerine ait verilerin kontrolünü, nerede ve nasıl saklandığını bilme ve koruma hakkıdır.

Güvenlik Notu: Kişisel verilerinizin sızdırılıp sızdırılmadığını kontrol etmek için kurumsal süreçlerde Have I Been Pwned gibi global veri ihlali istihbarat servisleri simüle edilebilir.

3. Bilgi Güvenliğinde Kritik Erişim Yaklaşımları
Bilmesi Gereken İlkesi (Need-to-Know): Bir personelin sadece görevi gereği bilmesi gereken verilere erişebilmesi, fazlasını görememesidir.

En Az Haklar İlkesi (Least Privilege): Kullanıcılara işlerini yapabilmeleri için ihtiyaç duydukları en minimum yetkilerin tanımlanmasıdır.

Görevler Ayrılığı (Segregation of Duties): Kritik bir sürecin (Örn: Finansal onay veya sunucu silme) tek bir kişinin inisiyatifine bırakılmaması, sürecin farklı rollere bölünmesidir.

🏢 Bölüm 3: Kurumsal Bilgi Güvenliği ve ISO Standartları
1. Kurumsal Yönetim Sistemleri Standartları
Şirketlerin küresel pazarda güvenilirlik kazanmak için uyum sağladığı temel standart aileleri:

ISO 9001: Kalite Yönetim Sistemi

ISO 14001: Çevre Yönetim Sistemi

ISO 45001: İş Sağlığı ve Güvenliği Yönetim Sistemi

ISO 27001 / 27002: Bilgi Güvenliği Yönetim Sistemi (BGYS) ve Güvenlik Kontrolleri

2. Denetim Türleri (Audit Types)
Şirketlerin sistemlerini denetleme ve belgelendirme süreçleri üç aşamada incelenir:

1. Taraf Denetim (İç Denetim): Şirketin kendi iç denetçileri tarafından yapılan öz değerlendirme sürecidir.

2. Taraf Denetim: Şirketin mal aldığı tedarikçileri veya iş ortaklarını denetlemesidir.

3. Taraf Denetim (Belgelendirme): Bağımsız, akredite dış kurumlar tarafından yapılan resmi sertifikasyon denetimidir.

3. ISO 27001:2022 Güncellemesi ve Ek-A Kontrolleri
ISO 27001 standardının 2005 ve 2013 versiyonlarındaki kontrol maddeleri, modern siber tehditler göz önüne alınarak ISO 27001:2022 versiyonunda 93 Kontrol Maddesine düşürülmüş ve 4 ana başlık altında kategorize edilmiştir:

Örgütsel Kontroller (Organizational)

Teknolojik Kontroller (Technological)

Fiziksel Kontroller (Physical)

İnsani Kontroller (People)

4. Sürekli İyileştirme (PUKÖ Döngüsü)
BGYS'nin sürdürülebilirliği PUKÖ (Planla - Uygula - Kontrol Et - Önlem Al) döngüsüne dayanır. Denetimler esnasında tespit edilen eksiklikler sistemde iki tür bulgu olarak kayda geçer:

Majör (Büyük) Uygunsuzluk: Sistemin temel bir maddesinin tamamen çökmesi veya uygulanmamasıdır. (Sertifika alımına engeldir).

Minör (Küçük) Uygunsuzluk: Sistemin işlediği ancak küçük operasyonel eksikliklerin bulunduğu durumlardır. (İyileştirme planı ile kapatılır).

🔒 Bölüm 4: Katmanlı Siber Savunma ve Profesyonel Sertifikalar
1. Güvenlik Kademeleri (Katmanlı Savunma / Defense in Depth)
Bir kurumu korurken tek bir güvenlik aracına güvenilmez. Saldırganın işini zorlaştırmak için iç içe geçmiş güvenlik katmanları (soğan modeli) kurulur:

[ İnternet ] 
     ↓
[ Ağ Trafiği Güvenliği (Firewall / IDS / IPS) ]
     ↓
[ Kurumsal Çevre Güvenliği / DMZ ]
     ↓
[ Sunucu / Uygulama Güvenliği (WAF) ]
     ↓
[ Son Kullanıcı / Cihaz Güvenliği (EDR / Antivirüs) ]
     ↓
[ Veri Kaybı Önleme (DLP - Data Loss Prevention) ] -> En İçteki Veri Çekirdeği
Zafiyet Kaynakları: Paket sızmaları, port açıklıkları, servis/daemon açıkları, zayıf şifreleme algoritmaları ve web uygulamalarındaki mantıksal hatalar.

2. Siber Güvenlik ve GRC Alanındaki Profesyonel Sertifikalar
Kariyer yolculuğunda hedeflenebilecek ulusal ve uluslararası saygın sertifikasyonlar:

CISA (Certified Information Systems Auditor): ISACA tarafından verilen, IT ve Bilgi Sistemleri denetçiliğinin küresel standart sertifikasıdır.

CISSP (Certified Information Systems Security Professional): ISC² tarafından sağlanan, ileri düzey tecrübeli siber güvenlik yöneticilerini hedefleyen tepe sertifikadır.

CEH (Certified Ethical Hacker): EC-Council tarafından verilen, saldırgan gözüyle savunma yapmayı öğreten beyaz şapkalı hacker sertifikasıdır (Beyaz/Siyah/Gri Şapka konseptleri).

TSE Sızma Testi Uzmanı: Türkiye genelinde geçerliliği olan, sızma testi ve yerel uyum süreçlerinde aranan ulusal sertifikadır.
