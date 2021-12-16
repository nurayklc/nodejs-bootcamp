
### **REST API Nedir?**
Representational state transfer; İlgili isteğe karşılık gelen verinin JSON / XML gibi dosya formatlarında gönderilmesidir. REST API, REST mimarisinin prensiplerine taşıyan API’lardır. Tüm prensiplerin karşılanması durumunda RESTful API olarak da adlandırılır.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-api-nedir/figures/RestApi.png](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-api-nedir/figures/RestApi.png)

Özetle, bir uygulamada gerçekleştirmek istediğimiz ek bir işlemi, o işlemi sağlayan başka bir uygulamadan API kullanarak gerçekleştirebiliriz.

### **REST Prensipleri**

- İstemci – Sunucu: (Client – Server)
- Tek Tip Arayüz: (Uniform Interface)
- Durumsuzluk: (Statelessness)
- Önbelleklenebilir: (Cacheable)
- Katmanlı Sistem: (Layered System)
- İsteğe Bağlı Kod: (Code On Demand - Optional)

### **İstemci - Sunucu (Client - Server) Prensibi**

İstemci isteği gönderen, sunucu da ilgili cevabı veren durumundadır. Birbirlerinin sorumluluk alanlarına girmezler. Birbirlerinden bağımsız programlama dilleri ve teknolojiler kullanabilirler.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/ReqRes.png](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/ReqRes.png)

### **Tek Tip Arayüz (Uniform Interface) Prensibi**

Aynı kaynağa yönelik olan tüm istekler, isteğin nereden geldiğinden bağımsız olarak aynı şekilde görünmelidir. Bu aynı zamanda istemci – sunucu bağımsızlığını da destekler. 4 temel özelliği bulunmaktadır.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/UniformInterface.jpg](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-I/figures/UniformInterface.jpg)

### **Durumsuzluk (Statelessness) Prensibi**

### **STATE**

- Söz konusu veriyi - durumu belirtir, örneğin bir veritabanı için düşünürsek veritabanında o an için bulunan veridir. Bir React uygulamasını düşünürsek herhangi bir component’ın o an ki durumu. Modal’ın açık veya kapalı olması, kullanıcının giriş, çıkış durumu gibi.
- **Stateful** ( Durum bilgisi olan ) vs **Stateless** ( Durum bilgisi olmayan ) İstemci tafından gerçekleştirilen her istek birbirinden bağımsızdır ve sunucu bu isteklerin her birini bağımsız olarak değerlendirir. Sunucu istemci tarafından kendisine gönderilen bilgileri tutmamalıdır. Örneğin bir isteğimiz kimlik doğrulama (Authentication) işlemi gerektiriyorsa ilgili tüm bilgiler (token vs..) istemci tarafından sunucuya devamlı olarak gönderilmelidir.
### **Önbelleklenebilir ( Cacheable ) Prensibi**

Sunucu gelen isteklere verilen cevapların önbelleklenebilir olup olmadığını belirtmelidir. Örneğin “Cache-Control”, “Expires” gibi HTTP başlıkları önbellek ile ilgili bilgiler taşır.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-II/figures/Cacheable.jpg](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-II/figures/Cacheable.jpg)

### **Katmanlı Sistem ( Layered System ) Prensibi**

İstemci – sunucu arasındaki ilişki katmanlara ayrılabilir, ve bileşenler sadece ilişkili oldukları katmanlara karşı sorumlu olurlar.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-II/figures/Layered.jpeg](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/rest-prensipleri-II/figures/Layered.jpeg)

### **İsteğe Bağlı Kod ( Code On Demand - Optional ) Prensibi**

Sunucu, istemci tarafına istemcinin işlevini genişletecek ek kodlar gönderebilir. Bu özellik istemci tarafında yapılması gereken işlemleri hafifletir.

Örneğin sunucu, istemci tarafına döneceği HTML dökümanın içerisine JavaScript kodları ekleyebilir.
