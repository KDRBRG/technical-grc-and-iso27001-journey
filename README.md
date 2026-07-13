
📘 Bölüm 1: Bilgi Güvenliği Politikası, Mekanizma ve Unsurları
1. Güvenlik Politikası (Security Policy)
Güvenlik politikası, bir organizasyonda hangi eylemlerin olumlu (uygun), hangilerinin olumsuz (uygunsuz) olduğunu belirleyen resmi bir beyandır.

Amaç: Kurumsal işleyişe sınırlar ve kurallar getirerek güvenliği belirli bir çerçevede yasal zemine oturtur.

Teori - Uygulama İlişkisi: Teori ile uygulama arasındaki boşluklar, sistemlerde güvenlik açıklarının (vulnerabilities) oluşmasına neden olur.

### 🛠️ Güvenlik Mekanizmaları
Kurumsal politikaların kağıt üzerinde kalmasını önlemek ve operasyonel işleyişi denetlemek adına kullanılan iki temel mekanizma bulunur:

```text
⚙️ Güvenlik Mekanizmaları
│
├── 💻 Teknik Mekanizmalar
│   ├── Kriptografi (Veri Şifreleme & Anahtar Yönetimi)
│   ├── Erişim Kontrolleri (VPN, Next-Gen Firewall)
│   ├── Uç Nokta Güvenliği (EDR / Antivirüs / XDR)
│   └── Dijital Doğrulama (e-İmza & Çok Faktörlü Kimlik Doğrulama)
│
└── 👔 Teknik Olmayan Mekanizmalar (İdari / Fiziksel)
    ├── Hukuki Altyapı (Gizlilik Sözleşmeleri - NDA, Arka Plan Taramaları)
    ├── Fiziksel Güvenlik (Biyometrik Geçiş Sistemleri, Sunucu Odası Kilitleri)
    └── Operasyonel Denetim (Fiziksel Çevre Bariyerleri)
## 🎯 3. Bilgi Güvenliğinin Çekirdek İlkeleri (CIA Triad & Ötesi)
```
### 🔺 CIA Üçlüsü Kurumsal Matrisi

| İlke | Teknik Tanım | Kurumsal Koruma Yöntemleri |
| :--- | :--- | :--- |
| **Gizlilik** *(Confidentiality)* | Bilginin yetkisiz kişilerin, süreçlerin veya sistemlerin eline geçmesinin kesin olarak engellenmesidir. | • Rol Tabanlı Erişim Kontrolleri (RBAC)<br>• Güçlü Şifreleme Algoritmaları (AES-256) |
| **Bütünlük** *(Integrity)* | Bilginin yetkisiz veya kazaen değiştirilmesinin, silinmesinin ya da bozulmasının önlenmesidir. | • Kriptografik Özet (Hash) Fonksiyonları<br>• Değişiklik Takip Sistemleri (Audit Logs) |
| **Erişilebilirlik** *(Availability)* | Yetkilendirilmiş kullanıcıların ihtiyaç duyduğu her an veriye ve sistemlere kesintisiz ulaşabilmesidir. | • Yedekleme Stratejileri (3-2-1 Kuralı)<br>• DDoS Koruma Sistemleri ve Yedekli Mimari |

---

### 💻 Teknik Laboratuvar: PowerShell ile Veri Bütünlüğü Doğrulaması

Kritik sistem konfigürasyonlarının veya log dosyalarının bütünlüğünü (Integrity) denetlemek amacıyla uygulanan pratik hash doğrulama adımları:

```powershell
# 1. Terminal üzerinde Masaüstü dizinine geçiş yapılır
cd Desktop

# 2. Üzerinde test gerçekleştirilecek 'Asil.txt' dosyası oluşturulur
New-Item Asil.txt

# 3. Dosya içerisine orijinal kurumsal veri enjekte edilir
Set-Content Asil.txt "Bu veri bilgi güvenliği bütünlük testine tabi tutulmuştur."

# 4. Dosyanın MD5 algoritması ile benzersiz hash değeri (parmak izi) hesaplanır
Get-FileHash Asil.txt -Algorithm MD5
[!TIP]
Siber Denetim Notu: Dosya içerisindeki tek bir bit veya noktalama işareti dahi değişse, üretilen yeni Hash değeri tamamen farklı olacaktır (Avalanche Effect). Denetim süreçlerinde bütünlük bu matematiksel kesinlikle doğrulanır.

👥 Genişletilmiş Güvenlik ve Erişim Yaklaşımları
Sorumlu Tutulabilirlik (Accountability): Sistemdeki her aktivitenin (Log ve Audit Trail mekanizmalarıyla) inkar edilemez şekilde belirli bir kullanıcı kimliğiyle eşleştirilmesi.

Kimlik Doğrulama (Authentication): Erişim talebinde bulunan kişinin gerçekte o kişi olduğunun kanıtlanması (MFA, Parola Politikaları, Biyometri).

Mahremiyet (Privacy): Kişisel verilerin (KVKK / GDPR) kontrolünün bireyde olması. Sektörel risk analizlerinde personellerin e-posta ihlalleri Have I Been Pwned gibi istihbarat ağları üzerinden simüle edilir.

Bilmesi Gereken İlkesi (Need-to-Know): Personelin yalnızca iş tanımı gereği kesinlikle görmesi gereken kritik verilere erişebilmesi.

En Az Haklar İlkesi (Least Privilege): Kullanıcılara sistem üzerinde sadece görevlerini tamamlamalarına yetecek en minimum yetki seviyesinin tanımlanması.

Görevler Ayrılığı (Segregation of Duties): Kritik finansal veya sistemsel operasyonların tek bir kişinin inisiyatifine bırakılmaması, sürecin farklı onay mekanizmalarına bölünmesi.

🏢 4. Kurumsal Yönetim Standartları ve ISO 27001:2022
🔍 Entegre Yönetim Sistemleri ve Denetim Fazları
Kurumlar küresel pazarda güvenilirlik kazanmak adına
ISO 9001 (Kalite),
ISO 14001 (Çevre),
ISO 45001 (İSG) ve
ISO 27001 (Bilgi Güvenliği) standartlarını entegre olarak işletirler.

 Bu yapılar 3 farklı fazda denetlenir:

1. Taraf Denetim (İç Denetim): Kurumun kendi iç denetçileri tarafından sistemin sağlığını ölçmek için yapılan öz değerlendirme döngüsüdür.

2. Taraf Denetim: Kurumun, kritik ekosistemini korumak adına mal/hizmet aldığı tedarikçilerini denetlemesidir.

3. Taraf Denetim: Bağımsız, akredite dış belgelendirme kuruluşları (Örn: TSE) tarafından yapılan resmi sertifikasyon denetimidir.

📊 ISO 27001:2022 Ek-A Kontrol Yapısı
Yeni güncelleme ile modern siber mimariye uyarlanan standart, kontrolleri 93 Maddeye indirmiş ve 4 ana başlıkta kategorize etmiştir:

┌────────────────────────────────────────────────────────────────────────┐
│                        ISO 27001:2022 KONTROLLERİ                      │
├───────────────────┬───────────────────┬────────────────┬───────────────┤
│    Örgütsel       │    Teknolojik     │    Fiziksel    │    İnsani     │
│   Controls        │    Controls       │    Controls    │   Controls    │
│  (Politika/Rol)   │ (Ağ/Şifreleme/EDR)│  (Veri Merkezi)│ (NDA/Eğitim)  │
└───────────────────┴───────────────────┴────────────────┴───────────────┘
🔄 Sürekli İyileştirme Döngüsü (PUKÖ)
BGYS süreçleri statik değil, dinamiktir; sürekli olarak Planla - Uygula - Kontrol Et - Önlem Al döngüsü işletilir. Denetimlerde çıkan eksiklikler iki tür bulguyla raporlanır:

Majör (Büyük) Uygunsuzluk: Standardın bir maddesinin veya kontrolünün tamamen yok sayılması/çökmesi (Sertifika alımına doğrudan engeldir).

Minör (Küçük) Uygunsuzluk: Sistemin genel olarak çalıştığı ancak operasyonel bazda düzeltilmesi gereken küçük iyileştirme alanları.

🛡️ 5. Katmanlı Siber Savunma (Defense in Depth)
Siber güvenlik mimarisinde tek bir güvenlik duvarına veya antivirüs yazılımına güvenilmez. Saldırganların işini zorlaştırmak ve riskleri dağıtmak adına iç içe geçmiş güvenlik katmanları inşa edilir:

🌐 [ İNTERNET ]
       │
       ▼
🔒 [ AĞ TRAFİĞİ GÜVENLİĞİ ] ─────────► Firewall, IDS / IPS Sistemleri
       │
       ▼
🌐 [ ÇEVRE VE DMZ GÜVENLİĞİ ] ───────► İzole Sunucu Blokları (DMZ Deployment)
       │
       ▼
🖥️ [ SUNUCU & UYGULAMA GÜVENLİĞİ ] ──► Web Uygulaması Güvenlik Duvarı (WAF), Yama Yönetimi
       │
       ▼
💻 [ SON KULLANICI GÜVENLİĞİ ] ──────► EDR, XDR, Antivirüs Ajanları
       │
       ▼
🗄️ [ VERİ GÜVENLİĞİ ÇEKİRDEĞİ ] ─────► Veri Kaybı Önleme (DLP), Güçlü Şifreleme
Zafiyet Odak Noktaları: Paket sızmaları, açık portlar, güncellenmemiş arka plan servisleri (daemon), zayıf kriptografik algoritmalar, içeriden gelen tehditler (Insider Threat) ve web uygulamalarındaki mantıksal kod hataları.

🗺️ 6. Küresel GRC & Siber Güvenlik Hedef Haritası
Teknik GRC, BT Yönetişimi ve Sızma Testi alanlarındaki uzmanlaşma yolculuğumda uzun vadede hedeflediğim küresel saygınlığa sahip sertifikasyonlar:

CISA (Certified Information Systems Auditor - ISACA): Bilgi sistemleri denetimi ve BT kontrol süreçlerinde küresel altın standart uzmanlık sertifikası.

CISSP (Certified Information Systems Security Professional - ISC²): İleri düzey siber güvenlik mimarisi, tasarımı ve kurumsal yönetişimi tescilleyen tepe yöneticilik belgesi.

CEH (Certified Ethical Hacker - EC-Council): Savunma hatlarını güçlendirmek amacıyla siber saldırganların teknik ve metodolojilerini (Beyaz/Siyah/Gri Şapka konseptleri) anlamayı sağlayan uygulamalı sertifika.

TSE Sızma Testi Uzmanı: Ulusal mevzuat, yerel sızma testi standartları ve kurumsal uyum süreçlerinde aranan en prestijli yerel otorite sertifikasyonu.

