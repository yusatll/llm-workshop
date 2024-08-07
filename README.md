# LLM - LangChain Workshop - [Yazılım Academy](https://www.linkedin.com/posts/altudev_nodejs-yapayzeka-react-activity-7222170290942803968-6yLM?utm_source=share&utm_medium=member_desktop)

Bu proje, Yazılım Academy tarafından 3 - 4 Ağustos 2024 tarihinde düzenlenen **"Fullstack Yapay Zeka Workshop"** unda geliştirilen örnek bir uygulamadır. Proje, **Node.js** ve **Hono** kullanarak backend geliştirme, **React 18.3** ile frontend oluşturma ve **Ollama** kullanarak yapay zeka modellerini ,**LLama3** ve **Gemma2:2b**, lokal makinede kullanarak txt ve pdf dosyaları üzerinde yapay zeka ile chat yapma konularını kapsamaktadır.

## Proje Yapısı
Proje aşağıdaki ana klasörlerden oluşmaktadır:

### hono-ollama-backend

Node.js ve Hono kullanılarak backend web API geliştirilmiştir.
 * src/index.ts: Backend'in ana giriş dosyası.
 * message_history.json: Mesaj geçmişini saklamak için JSON dosyası.

### langchain-hono-backend

LangChain konusunu ele alan ve Hono kullanarak geliştirilmiş backend.
 * src/index.ts: Backend'in ana giriş dosyası.
 * data: Gerekli veri dosyalarını saklamak için klasör.

### react-ollama-frontend

React 18.3 ile geliştirilmiş interaktif frontend.
 * src/: Tüm frontend bileşenlerinin ve stil dosyalarının bulunduğu klasör.
 * assets: Statik varlıklar.
 * components: React bileşenleri.
 * App.tsx, main.tsx: Ana uygulama dosyaları.

### Kurulum ve Çalıştırma
Projenin her bir bileşeni için bağımlılıkları kurmak ve projeyi çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

#### Backend (hono-ollama-backend ve langchain-hono-backend)
1. Klasöre gidin:
````bash
cd hono-ollama-backend
# veya
cd langchain-hono-backend
````

2. Bağımlılıkları yükleyin:

````bash
npm install
````

3. Uygulamayı başlatın:
````bash
npm run dev
````

Program başarıyla çalıştıktan sonra, terminalde port numarasını görebilirsiniz.

##### GET ve POST İşlemleri
* GET /:
Basit bir yanıt döndürür.
    - Cevap: "Hello Hono!"

* GET /loadTextEmbeddings:
Metin dosyasından embeddingleri yükler.
    - Cevap: { "message": "Text embeddings loaded successfully." }

* GET /loadPdfEmbeddings: PDF dosyasından embeddingleri yükler.
    - Cevap: { "message": "PDF embeddings loaded successfully." }

* POST /ask: Kullanıcının sorduğu soruya göre embeddingler üzerinden yanıt döner.
    - Gönderilen veri: { "question": "kullanıcının sorusu" }
    - Cevap: { "answer": "yapay zekanın cevabı" }


#### Frontend (react-ollama-frontend)
1. Klasöre gidin:
````bash
cd react-ollama-frontend
````

2. Bağımlılıkları yükleyin:

````bash
npm install
````

3. Uygulamayı başlatın:
````bash
npm run dev
````
Arayüzü çalıştırdıktan sonra, arayüzü açmak için tarayıcıdan localhost açıp, port numarasıyla bağlanabilirsiniz. 

### Postman Üzerinden Ollama Kullanımı
Postman'ı çalıştırdıktan sonra, GET ve POST istekleri ile ollama'da yüklediğiniz yapay zeka modeline prompt gönderebilirsiniz. 

GET: 
````bash
http://localhost:3002/loadTextEmbeddings
# veya
http://localhost:3002/loadPdfEmbeddings
````

POST:
````bash
http://localhost:3002/ask
````


## Kullanılan Teknolojiler
 * **Node.js**: Backend geliştirme için.
 * **Hono**: Hızlı ve hafif bir web framework.
 * **React 18.3**: Frontend geliştirme için.
 * **LangChain**: Doküman zincirleme ve vektör veri tabanı yönetimi.
 * **Ollama**: Lokal yapay zeka modeli çalıştırma.

