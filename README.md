# Discord Kayıt ve İstatistik Yönetim Botu

Bu Discord botu, **sunucu üyelik yönetimini** daha kolay ve verimli hale getirmek için tasarlandı. Bot, kullanıcıların kayıt işlemlerini, istatistiklerini ve ranklarını takip etmelerine olanak sağlar. Aynı zamanda sunucu yöneticilerinin veya moderatörlerin, kullanıcı aktivitelerini kolayca izlemelerini ve ödüllendirmelerini sağlar.

## 🚀 Temel Özellikler

### 1. **Kayıt Sistemi**
   - **Erkek/Kadın Kayıt**: Yöneticiler ve moderatörler, `.erkek` ve `.kadin` komutlarıyla yeni üyeleri kaydedebilir.
   - **Otomatik Rol Verme**: Kullanıcıya, kayıt esnasında **erkek** veya **kadın** rolleri otomatik olarak atanır.
   - **Puan Kazanma**: Kayıt eden kullanıcı, her başarılı kayıt işleminden sonra belirli miktarda **coin** (puan) kazanır.

### 2. **İstatistik Sistemi**
   - **Kayıt İstatistikleri**: Kullanıcılar, `.stat` komutuyla kayıt ettikleri kişilerin sayısını ve kazandıkları puanları (coin) görüntüleyebilir.
   - **Rank Sistemi**: Kullanıcılar, kazandıkları puanlarla **rank** seviyelerini yükseltir. Her seviyeye belirli bir rol atanır.
   - **Gerekli Puan**: Kullanıcılar, mevcut **rank** seviyelerini ve bir sonraki seviye için gereken puan miktarını öğrenebilir.

### 3. **Yönetici ve Yetkili Kontrolü**
   - **Rol Bazlı Erişim**: `.erkek`, `.kadin`, ve `.stat` gibi komutlar yalnızca belirli bir role sahip **yöneticiler** ve **moderatorler** tarafından kullanılabilir.
   - **Yetki Kontrolü**: Bot, kullanıcının sahip olduğu rol veya izinlere göre komutları çalıştırmalarını sağlar.

### 4. **Veritabanı ve API Bağlantıları**
   - **MongoDB ile Entegrasyon**: Kullanıcıların kazandığı puanlar ve kayıt bilgileri MongoDB veritabanında saklanır.
   - **Dinamik Veri Yönetimi**: Kullanıcılar, botun komutları aracılığıyla veritabanındaki bilgilerini görüntüleyebilir ve güncelleyebilir.

---

## ⚙️ Nasıl Kurulur?

1. Bu projeyi klonlayın:
   ```bash
   git clone https://github.com/kullaniciadi/v14-coin-wasty.git

2. Gerekli bağımlılıkları yükleyin:
   ```bash
   cd v14-coin-wasty
   npm install
3. `.env` dosyasını oluşturun ve Discord bot token'ınızı ekleyin:
   ```bash
   DISCORD_TOKEN=your-bot-token
   MONGODB_URI=your-mongo-db-uri
4. Sunucunuzda botu çalıştırın:
   ```bash
   node index.js

  ## 🛠️ Ekstra Özellikler

### 1. **Özel Ödüller**
   - Kullanıcılar, belirli puan seviyelerine ulaştıklarında ödüller kazanabilirler. Bu ödüller **roller** veya **özel görevler** şeklinde olabilir.
   - Örnek:
     - **500 puan** kazanan bir kullanıcıya **VIP** rolü verilebilir.
     - **1000 puan** kazanan bir kullanıcı, **Yönetici** rolüne terfi edebilir.

### 2. **Aktivite İzleme ve Ekstra Puanlar**
   - Kullanıcıların **sesli kanal aktiviteleri** veya **mesaj gönderimleri** izlenebilir ve **ekstra puanlar** verilebilir.
   - Örneğin:
     - **Sesli Kanal Aktivitesi**: 10 dakika boyunca sesli kanalda kalan bir kullanıcıya **2 puan** verilebilir.
     - **Mesaj Aktivitesi**: Aktif bir mesaj kanalında, 10 mesaj gönderen bir kullanıcıya **1 puan** verilebilir.
   
   - Bu özellik, sunucudaki etkileşimi arttırmak ve kullanıcıların aktif kalmalarını sağlamak için mükemmel bir yöntemdir.

---

## 📜 Komutlar

### `.erkek @etiket isim`
- Yeni bir erkek üyeyi kaydeder. Kullanıcıya **erkek** rolü verilir ve adı belirlenir. Kayıt eden kişi **1 puan** kazanır.

### `.kadin @etiket isim`
- Yeni bir kadın üyeyi kaydeder. Kullanıcıya **kadın** rolü verilir ve adı belirlenir. Kayıt eden kişi **1 puan** kazanır.

### `.stat`
- Kullanıcı kendi kayıt istatistiklerini görüntüler: Kaç kişi kaydettikleri ve ne kadar puan kazandıkları.

### `.profil`
- Kullanıcıların profilini görüntüler. Profil, kullanıcının kaydettiği kişi sayısını (puan) ve diğer temel bilgilerini içerir.

---

## 🔑 Konfigürasyon

Botun bazı özellikleri, **`config.json`** dosyasına göre yapılandırılabilir. Bu dosyada şu ayarlar yer alır:

- **Rol ID'leri**: `.erkek` ve `.kadin` komutlarında hangi rolün atanacağı gibi ayarlar yapılabilir.
- **Puan Sistemleri**: Kayıt ve invite işlemleri sonucunda kazanılan puanlar, bu dosyada tanımlı kurallara göre verilir.
- **Yetki Kontrolleri**: Hangi rollerin komutları kullanabileceği de `config.json` dosyasından ayarlanabilir.
