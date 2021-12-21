# Clean Code (Temiz Kod) 
Clean Code kavramı Robert C. Martin Clean Code kitabıyla özdeşleşmiş durumdadır. 

Kodun temiz olması, kodu yazan geliştiricinin dışındaki geliştiriciler tarafından kodun kolay okunabilmesi, geliştirme yapması açısından zaman ve maliyet konusunda avantaj sağlar.
#### Clean Code Prensipleri
- Readability, (Okunabilirlik)
- Changeability, (Değiştirebilirlik)
- Extensibility (Genişletebilirlik)
- Maintainability. (Sürdürebilirlik)

## CLEAN CODE (TEMİZ KOD)
#### Genel Kurallar
- Standart yaklaşımları uygula
- Kodu basit tutmaya çalış, Olabildiğince kompleks yapılardan uzak dur
- Kodu bulduğunuzdan daha temiz halde bırakın.
- Her zaman sorunun kaynağına odaklanın. Problemin ana kaynağını bulmaya çalışın
#### Tasarım Kuralları
- Yapılandırılabilir verileri kodun içerisinde rahat erişilebilen, değiştirilebilen kısımda bulundur.
- If/else veya switch/case koşulları yazmak yerine polymorphism tercih et.
- Multi-threading kodları ayrıştır.
- Her kod yapısını yapılandırılabilir ve dinamik hale getirmekten kaçının.
- Dependency Injection (Bağımlılık Enjekte Etmeyi) kullanın.
- Law of Demeter: Bir sınıf doğrudan sadece bağımlılıklarını bilmelidir yasasını takip et.
#### Anlaşılabilirlik İpuçları
- Tutarlı ol. Bir işi bir yöntemle yapıyorsan, her yerde aynı yöntemi kullan.
- Açıklayıcı değişken isimleri kullan.
- Kod içerisindeki değişkenlerin tuttuğu (primitif ve object) türemiş verilerin veya kod akışının sınıf koşullarını kapsayacak şekilde encapsulate edin. Sınır koşullarını takip etmek zor olduğundan bu tarz işlemleri tek bir yerden gerçekleştirin.
- Object Türler yerine Primitif Türleri tercih edin. (Immutable)
- Mantıksal bağımlılıklardan kaçının. Aynı sınıf içerisinde başka bir takım şeylere bağımlılığı olan metodlar yazmayın.
- Negative koşullardan sakının.
#### İsimlendirme Kuralları
- Açıklayıcı ve kafa karışıklığına neden olmayacak isimlendirmeler kullanın.
- İsimlendirmeler ile anlamlı ayrımlar oluşturun.
- Telefazu kolay isimlendirmeler bulun.
- Aradığınızda kolay şekilde bulunabilecek ve erişebilecek isimlendirmeler seçin.
- Kodun içerisinde gizli rakamlar ve sabitlerden kaçının.
- İsimlendirmede kodlammalardan kaçının ve değişkenlerin önüne ön ek takmayın.
#### Fonksiyon Kuralları
- Küçük olmalı.
- Bir tek iş yapmalı
- İsmi açıklayıcı olmalı
- Olabildiğince az argüman almalı
- Side Effect içermemeli
- Flag (true/false) argümanlarını parametre olarak koda geçirilip bu method içerisinde farklı metod çağrımları yapılmamalı.
#### Yorum Satırı Kuralları
- Olabildiğince kendinizi kod içerisinde anlatmaya çalışın,
- Gereksiz yorum ekleme
- Başlangıç bitiş kodu ayırma amaçlı yorum satırları eklemeyin.
- Kodu yorum satırı haline getirip bekletmeyin. Gereksiz kodları silin.
- Yorumu yazma nedeninizi açıklayın.
- Kodun açıklaması olarak kullanın.
- Sonuçların uyarısı olarak kullanın.
#### Source Kod Yapısı
- Kavramları dikey olarak ayır.
- Birbiri ile ilişkili kodlar dikey yoğunlukta görüntülenmeli.
- Değişkenleri kullanım alanlarına yakın tanımla.
- Birbirine yakın fonksiyonları birbirine yakın tanımla.
- Benzer işleri yapan fonksiyonlar birbirine yakın olmalı.
- Fonksiyonları aşağı yönlü akacak şekilde yerleştirin.
- Kod satırlarını kısa tutun.
- Yatay hizalama yapmayın. (üstteki, alttaki satır ile hizalama)
- Boşluk kullanarak ilişkili şeyleri birbirine yakın, ilişkisizleri uzaklaştır.
- Kodun oluşturduğu girintileri bozmayın.
#### Objeler ve Veri Yapıları
- Kodun iç yapısını gizleyin.
- Veri yapılarını, dillerin hazır Collection yapılarını tercih edin.
- Hibrid yapılardan kaçının.
- Olabildiğince küçük olun.
- Tek bir sey yapın.
- Küçük sayıdaki değişkenlerle çalışın.
- Temel sınıf, kendisinden türeyenler hakkında hiçbir şey bilmemelidir.
- Fonksiyona bir takım parametreler geçirerek bunların istenen davranışa göre şekillenmesindense, bir çok sade fonksiyona sahip olmak daha iyidir.
- Static metodları tercih etme.
#### Testler
- Her test için bir assert olmalı.
- Test okunabilir olmalı.
- Test hızlı çalışabilir olmalı.
- Test bağımsız olmalı.
- Test tekrar edebilir olmalı.
