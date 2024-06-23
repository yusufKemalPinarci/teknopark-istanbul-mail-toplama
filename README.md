Genel Bakış
Bu depo, Teknopark İstanbul web sitesinden şirket e-postalarını çıkarmak ve bu şirketlere iş başvuru e-postaları otomatize etmek için yazılmış betikleri içermektedir. Süreç, iletişim bilgilerini toplamak için web kazıma işlemlerini ve Python kullanarak kişiselleştirilmiş iş başvuru e-postalarını otomatikleştirmeyi içermektedir.

Şirket E-postalarının Kazınması
fetch_company_emails.py betiği, BeautifulSoup ve requests kütüphanelerini kullanarak Teknopark İstanbul web sitesinden şirket e-postalarını kazımak için kullanılır. Betik, kodlanmış e-postaları çıkarır, onları çözümler ve company_emails.txt dosyasına kaydeder. Aşağıda sürecin kısa açıklaması bulunmaktadır:

Çözümleme Fonksiyonu: decode_cf_email(encoded_email) Cloudflare tarafından şifrelenmiş e-postaları çözer.

Kazıma Mantığı: Ana fonksiyon olan fetch_company_emails() firmalar sayfasının HTML içeriğini alır, şirket bağlantılarını çıkarır, her şirketin sayfasına geçer, e-postaları çözer ve toplar, son olarak benzersiz e-postaları bir metin dosyasına yazar.

İş Başvuru E-postalarının Gönderilmesi
send_job_applications.py betiği, çıkarılan e-posta adreslerine otomatik iş başvuru e-postaları gönderme sürecini otomatikleştirir. İşleyiş şu şekildedir:

E-posta Gönderme Fonksiyonu: send_email() Gmail'in SMTP sunucusunu kullanarak bir iş başvuru e-postası gönderir. CV ekler ve her şirkete kişiselleştirilmiş bir e-posta gönderir.

E-posta İçeriği: E-posta şablonu, başvuru sahibinin arka planı hakkında detaylar içerir ve ilgili pozisyonlar için dikkate alınma talebinde bulunur.

İteratif Gönderme: Betik, company_emails.txt dosyasından şirket e-postalarını okur, yinelenen e-postaları önlemek için gönderilen e-postaları kontrol eder ve send_email() kullanarak e-postayı gönderir.

Kullanım
Bu depoyu kullanmak için:

Python'un ve gerekli kütüphanelerin (requests, BeautifulSoup, smtplib) kurulu olduğundan emin olun.
Gmail kimlik bilgilerinizi (sender_email ve sender_password) kendi bilgilerinizle değiştirin (güvenlik için ortam değişkenleri kullanmayı düşünün).
attachment_pathi CV dosyanızın yoluna göre ayarlayın.
send_job_applications.py içindeki e-posta şablonunu, niteliklerinize ve ilgi alanlarınıza uygun şekilde özelleştirin.
Güvenlik Notu
Gmail kimlik bilgilerinizin (sender_email ve sender_password) kod tabanında açığa çıkmamasına dikkat edin. Hassas bilgiler için ortam değişkenleri veya güvenli depolama yöntemleri kullanın.
