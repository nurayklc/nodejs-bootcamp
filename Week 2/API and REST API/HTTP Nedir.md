# HTTP NEDİR?
**H**yper **T**ext **T**ransfer **P**rotocol ifadesinin kısaltmasıdır. İstemci ile sunucu arasındaki veri akışının kurallarını belirleyen protokoldür. İstek – Cevap (request, response) modeline göre çalışır.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/HTTP.jpeg](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/HTTP.jpeg)

### **REST Mimarisinde HTTP'nin Rolü**

REST mimarisinin prensiplerinden ilki istemci - sunucu çalışma modelidir. Biz bir istekte bulunuruz ve sunucu isteğimize karşılık olan durumu (state) bize bir sunum (presentation) olarak gönderir. HTTP protokolü burada bu sunum transferi için kurulan iletişimin kurallarını belirler. REST mimarisine uygun API'ların neredeyse tamamında HTTP protokolü kullanılır.

### **HTTP Request**

İstek (Request) yapısını belirtir. 4 bölümden oluşur.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/Request.png](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/Request.png)

Yapılan isteğin detayları belirtilir.

### **HTTP Response**

Cevap (Response) yapısını belirtir. 4 bölümden oluşur.

![https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/Response.png](https://raw.githubusercontent.com/Kodluyoruz/taskforce/main/rest-api/http-nedir/figures/Response.png)

Alınan cevabın detayları belirtilir.

## **HTTP Durum Kodları (Status Codes)**
Sunucu tarafından ilgili isteğin sonucunu belirten, 3 rakamdan oluşan sayısal ifadelerdir.

**Informational responses (Bidirimsel cevaplar) (100–199)**

- 100 Continue
- 102 Processing

**Successful responses (Başarılı cevaplar) (200–299)**

- 200 OK
- 201 Created
- 204 No Content

**Redirections (Yönlendirme cevapları) (300–399)**

- 300 Multiple Choice
- 301 Moved Permanently
- 304 Not Modified

**Client errors (İstemci Hataları) (400–499)**

- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 405 Method Not Allowed

**Server errors (Sunucu Hataları) (500–599)**

- 500 Internal Server Error
- 503 Service Unavailable

**GET**

- Verileri almak - listelemek için kullanılan istek metodudur.
- [http://api.example.com/users](http://api.example.com/users)
- [http://api.example.com/users/1](http://api.example.com/users/1)

**POST**

- Belirli bir kaynağa veri göndermek için kullanılır.
- [http://api.example.com/users](http://api.example.com/users)

**PUT**

- Belirli bir kaynaktaki verinin tamamının değiştirilmesi için kullanılan metodtur.
- [http://api.example.com/users/1](http://api.example.com/users/1)
- `{ “name": "Alex", "age": 23}`

**PATCH**

- Belirli bir kaynaktaki verilerin bir kısmının değiştirilmesi için kullanılan metodtur.
- [http://api.example.com/users/1](http://api.example.com/users/1)
- `{ "name": "Alex"}`

**DELETE**

- Belirli bir kaynaktaki verilerin silinmesi için kullanılan metodtur.
- [http://api.example.com/users/1](http://api.example.com/users/1)

**CONNECT - TRACE - OPTIONS - HEAD**

### **SAFE Metotlar**

GET – HEAD – OPTIONS : Sunucu “state” tarafında değişiklik oluşturmazlar. “Read-only” yapısındadırlar.

### **IDEMPOTENT Metotlar**

GET – HEAD - OPTIONS – DELETE – PUT – TRACE : Tekrar durumunda sunucu state yapısında herhangi bir yan etki bırakmazlar. Safe metodlar, idempotent'tır.

## **Endpoint (Sorgu Adresi)**

REST API kullanımında gönderilen istek ile verilen cevap için belirlenen buluşma noktasıdır.

Root(Base) /Path yapısından oluşur, isimler kullanılır, fiil ilgili HTTP metodu ile belirtilir. Dökümantasyon tarafından belirtilir.

- [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com/) /posts

Değişen değer için genelde (:) kullanılır.

- [https://jsonplaceholder.typicode.com/posts/1](https://jsonplaceholder.typicode.com/posts/1) => /posts/:id veya /posts/{{id}}
- [https://jsonplaceholder.typicode.com/posts/1/comments](https://jsonplaceholder.typicode.com/posts/1/comments)

Sorgu parametreleri için (?) kullanılır.

- Aslında sorgu parametreleri REST yapısının bir parçası değildir ancak sorgu adreslerinde sıkça rastlarız.
- [http://example.com/articles?sort=author&date=published](http://example.com/articles?sort=author&date=published)
