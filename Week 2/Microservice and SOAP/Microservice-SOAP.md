# Monolithic Architecture (Monolitik Mimari) 
Monolitik bir uygulama, birden fazla modül içeren tek bir kod tabanına sahiptir. Modüller, fonksiyonel veya teknik özelliklerine göre ayrılmıştır. Tüm uygulamayı build eden tek bir derleme sistemine sahiptir. Ayrıca tek bir çalıştırılabilir veya deploy edilebilir dosyaya sahiptir.

Sunucu Katmanları ana hatları ile şu şekilde olacaktır:
- **Presentation Layer (Sunum Katmanı):** HTTP hizmetlerini yerine getirmekten ve mesaj formatı HTML, JSON ya da XML gibi notasyonlar ile sağlanan mesajlaşmadan sorumludur.
- **Business Layer (İş Katmanı):** Uygulamanın iskeletidir. Akış ve koordinasyondan sorumludur.
- **Database Access Layer (Veri Tabanı Katmanı):** Uygulamanın veri tabanına bağlandığı ve veri tabanı işlemlerinin yapıldığı katmandır.

### Monolotik Mimaride Ölçeklendirme 
Sunucu kaynakları yetersiz gelmeye başladığında veya veri tabanı, sorgulara isteklere yetişememeye başladığında monolotik mimaride ölçeklendirmeye gidilir.
Ölçeklendirme yatay olarak gerçekleşmek ile birlikte, **Loadbalancer** kullanarak sunuculardaki trafik paylaştırılır.

### Avantajları
- Geliştirmesi kolaydır.
- Test edilebilirliği kolaydır.
- Deployment oldukça kolaydır.
- Ölçeklendirme kolaydır

### Dezavantajları
- Proje büyüdükçe bakımı zorlaşır.
- Uygulamanın boyutu başlama süresini yavaşlatır.
- Uygulana güncelleneceği zaman tüm uygulamayı tekrardan deploy etmek gerekir.
- Monolitik uygulamalar ölçekleneceği zaman bazen sorun çıkartabilir.
- Ölçeklendirme tüm proje genelinde yapılır.
- Güvenirlik/Sağlamlık/Dayanıklılık


# SOA(Service Oriented Architecture)
- Servislerin ayrı yarı tasarlanıp, bir yapı oluşturmasını sağlar.
- Loose coupling: Yapılar birbirinden bağımsız olarak çalışabilirler.
- Birden çok sistemin yer aldığı yapılarda kullanılır.
- Birden çok birleşeni vardır:
    - Policies, Contracts, Services, etc.
- Dağıtık yazılım sistemleri kalitesini arttırmayı hedefler
    - Terkrar Kullanılabilirlik (Reusability)
    - Uyumluluk(Adaptability)
    - Bakım (Maintainability)
- SOA'nın kendi içerisinde kurduğu veya dış bağlantılar için kurduğu iletişimde web servisler (SOAP,WDSL) kullanır.
- Enterprise Bus Service(EBS) client tarafından gelen isteği kontrol ederek SOA ile iletişim kuran katmandır.

### Avantajları 
- Servisler tekrar kullanılabilir.
- Servislerin bakım ve onarımı kolaydır.
- Güvenilirlik/Dayanıklılık
- Up Time oranları yüksektir.
- Ulaşılabilirlik yüksektir.
- Yatak ve dikey ölceklendirme mümkündür.
- Platform bağımsızdır.
- Üretkenlik artar

### Dezavantajları
- Overload
- Yüksek maliyet
- Yüksek bant genişliği

# Microservice Architecture (Mikro Servis Mimarisi)
- SOA'nın farklı bir bakış açısı ile yorumlanmış halidir.
- Büyük servisleri küçük servisler olarak sunmayı hedefler.
- Servisler kendine ait server stackleri(sunucu) vardır.
- Her servisin kendine ait Database'i vardır.
- Microservice'lerin hedefi sadece bir küçük işi çok iyi yapmaktır.
- Microservice'ler kendi aralarında API Gateway üzerinden iç ve dış dünya ile iletişim kurarlar.
- Herhangi bir teknoloji ve dile ait bir kısıtlama yoktur.
- Stateless yapılardır.
- Kolay ölceklendirilme yapılır. (Yatay olarak ölçeklendirilir.)

### Avantajları
- Çok dilli mimaridir.
- Kolay ölçeklendirme yapılır.
- Daha iyi bir takım yönetimi gerçekleşir.
- Yenilik yapmak daha kolaydır.
- Microservislerin kendine ait veritabanları vardır.
- Daha odaklı yapısı vardır.
- Implement edilirken diğer servisler etkilenmez.

### Dezavantajları
- Implement kolay değildir. (Network calls, Service discovery)
- Debug kolay değildir.
- Hata yönetimi kolay değildir.
