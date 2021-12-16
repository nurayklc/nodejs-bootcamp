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
- `{ “name": "Gurcan", "age": 40}`

**PATCH**

- Belirli bir kaynaktaki verilerin bir kısmının değiştirilmesi için kullanılan metodtur.
- [http://api.example.com/users/1](http://api.example.com/users/1)
- `{ "name": "Gurcan"}`

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


### **JSON vs JavaScript**

**JavaScript** web uygulamalarında sıklıkla kullanılan dinamik bir programlama dilidir. **JSON** ise bir söz dizim olarak JavaScript'in bir alt kümesi olarak düşünülebilir. Bu nedenle uygun JSON formatındaki bir içerik JavaScript ifadesine (expression) denk gelir.

```
{
    "id":1,
    "title": "Matrix",
    "actors": ["Keanu Reeves", "Carrie Anne Moss"],
    "published_year": 1999,
    "genre": {
      "id": 6,
      "name": "Action"
    },
    "rating": 7.9
}

```

şeklindeki JSON söz dizimini bir JavaScript değişkenine atadığımızda, değişken değer olarak bir JavaScript nesnesini almış olur. JSON formatında **key** ifadelerin çift tırnak içerisine alınması zorunludur. Her ne kadar JSON söz dizimi olarak kendisine JavaScript'i örnek aldıysa da kullanımı bir çok programlama dili tarafında yaygındır.

### **JSON vs XML**

### **XML**

e**X**tensible **M**arkup **L**anguage ifadesinin kısaltmasıdır. Veri depolamak ve iletmek için kullanılan bir script dilidir. 1998 yılında **W3C** tarafından standartlaştırılmıştır.

```
<breakfast_menu><food><name>Belgian Waffles</name><price>$5.95</price><description>
        Two of our famous Belgian Waffles with plenty of real maple syrup
     </description><calories>650</calories></food>
</breakfast_menu>

```

Genel olarak ağaç yapısına (tree structure) sahiptir. Veriler açılış ve kapanış etiketlerinin içerisinde bulunur. Dıştaki etiket, içtekinin "parent"ı, içteki etiket ise dıştakinin "child"ı şeklinde düşünülür.

**JSON** formatının **XML** formatına göre en büyük avantajı, doğalında bir nesne modeline sahip olmasıdır. Bu özellik sayesinde birçok programlama dili JSON verileri daha kolay bir şekilde işleyebilir.
