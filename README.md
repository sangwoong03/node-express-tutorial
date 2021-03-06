## node.js express Stuyding

---

<br>

### ๐ why?

---

1. daily-planner repository์ ๋ก์ปฌ์คํ ๋ฆฌ์ง๋ฅผ ํตํ ๋ก๊ทธ์ธ ๋ฐ ์ผ์ ๊ด๋ฆฌ ๊ธฐ๋ฅ์ ์๋ฒ ํต์ ์ผ๋ก ๋ณ๊ฒฝ.
2. portfolio email ์ ์ก ๊ธฐ๋ฅ์ ์ถ๊ฐํ๊ธฐ ์ํจ.
3. Node.Js์ Non-blocking์ด๋ผ๋ ํน์ง.
   - ์ผ๋ฐ์ ์ธ ์ธ์ด๋ก ๊ตฌ์ฑ๋ ์๋ฒ์ ๋ค๋ฅด๊ฒ ์์ฒญ ์์๋ฅผ ์กฐ์ ํ์ฌ ์์ฒญ ์ค ์ค๋จ์ ๋ฉ์ถ์ง ์์.
     <br>  
     <br>

### ๐ Ref:

---

- ๊ณต์ ๋ฌธ์ [Express Mdn](https://developer.mozilla.org/ko/docs/Learn/Server-side/Express_Nodejs/Introduction)
- ๊นํ ์๋ฃ [parkjunyoung](https://github.com/parkjunyoung/express-online)
- ๋ธ๋ก๊ทธ [inu](https://inuplace.tistory.com/643?category=933545)
- ์ ํ๋ธ [์ฝ๋ฉ์ ํ](https://www.youtube.com/channel/UCSLrpBAzr-ROVGHQ5EmxnUg)
  <br>  
  <br>

### ๐ Index (Library and API):

---

1. express start (express-server.js)
   ```
   npm i express
   node ("main js file name").js
   ```
2. nodemon (express-server.js)
   ```
   npm i install -g nodemon
   nodemon -e js, html ("main js file name").js
   ```
3. Router (rotues/Admin.js, routes/README.md)
4. view engine (template/README.md, template/layout/base.html)
5. Middlewares (middleware/README.md)
6. Error handling (template/common/404, 500.html)
7. Macro (template/macro/link/html, template/layout/base.html)
8. Static files (uploads/README.md)
9. REST API (express-server.js, routes/Admin.js)
10. Method-override (express-server.js, template/admin/lists&edit.html)

```
npm install method-override

// in main js file
const methodOverride = require("method-override");
app.use(methodOverride("_method"));

// in other html (nunjucks templates)
<form action="/delete_?method=DELETE" method="POST"></form>
<form action="/edit_?method=PUT" method="POST"></form>
```

   <br>
   <br>

### ๐ Server:

---

<br>

- ์์ฒญ์ ํ๋ฉด ์์ฒญํ ๋ด์ฉ์ ๋ณด๋ด์ฃผ๋ ํ๋ก๊ทธ๋จ.
- ์ฝ๊ฒ ๋งํด ์๋นํ๋ ์ญํ ์ ํจ.
- ๋น์  ) ํด๋ผ์ด์ธํธ = ์๋น ์๋ / ์๋ฒ = ์๋น ์๋ฐ์
- HTTP ์์ฒญ ๋ฐฉ์ 4๊ฐ์ง
  1.  ์ฝ๊ธฐ (GET)
  2.  ์ฐ๊ธฐ (POST)
  3.  ์์  (PUT)
  4.  ์ญ์  (DELETE) >> AJAX๋ก ์ญ์ ์์ฒญ  
      <br>
      <br>

### ๐ REST API:

---

<br>

- ์น ๊ฐ๋ฐ ์ API (Application Programming Interface)

  - ์น ์๋ฒ์ ํด๋ผ์ด์ธํธ์ ์ํต ๋ฐฉ๋ฒ
  - ์์) get`("url", ...))`

- REST API (Representational State Transfer API, Roy Fielding):

  **[REST ์์น 6๊ฐ]**

  1.  Uniform Interface (์ค์)
      - ํ๋์ ์๋ฃ๋ ํ๋์ url.
      - ์์ธก ๊ฐ๋ฅ์ฑ
      - ์์ฒญ๊ณผ ์๋ต์ ์ ๋ณด๊ฐ ์ถฉ๋ถํ ๋ค์ด๊ฐ์์ด์ผ ํจ.
  2.  Client - Server ์ญํ  ๊ตฌ๋ถ
      - ๋ธ๋ผ์ฐ์ ๋ ์์ฒญ๋ง
      - ์๋ฒ๋ ์๋ต๋ง
  3.  Stateless
      - ์์ฒญ1, ์์ฒญ2 ์ฆ ๊ฐ๊ฐ์ ์์ฒญ๋ค์ ์์กด์ฑ์ด ์์ด์ผ ํจ.
  4.  Cacheable
      - ์๋ฒ์์ ๋ณด๋ด์ฃผ๋ ์ ๋ณด๋ค์ ์บ์ฑ์ด ๊ฐ๋ฅํด์ผ ํจ.
      - ์บ์ฑ์ ์ํ ๋ฒ์  ๊ด๋ฆฌ๋ ์ํด์ผ ํจ. (๋ธ๋ผ์ฐ์  ์ญ)
  5.  Layered System
      - ์ปดํฌ๋ํธ์ ๊ทธ๋ฃนํ ๋ฐ ๊ณ์ธต ๊ตฌ์กฐํ
  6.  Code on Demand - ํด๋ผ์ด์ธํธ์ ์์ฒญ์ ๋ฐ๋ฅธ ์ํต์ด ํ์  
      <br>
      <br>
      **[์ด๋ฆ์ง๊ธฐ ์์น]**

  - url์ ๋ช์ฌ๋ก ์์ฑ
  - ํ์ ๋ฌธ์๋ฅผ ๋ช์ํ  ๋ /ํ์ผํ์ฅ์(.html) ์ฐ์ง ์๊ธฐ
  - ๋์ด์ฐ๊ธฐ๋ ๋์(-) ์ด์ฉ
  - ์๋ฃ ํ๋ ๋น ํ๋์ url
    <br>
    <br>

### ๐ MongoDB:

---

<br>

- ๊ด๊ณํ ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ฌ์ฉ (MySQL, Oracle ...)
  - ํ๊ณผ ์ด๋ก ์ ์ฅ๋จ.
  - SQL์ด๋ผ๋ ์ธ์ด๋ฅผ ์ฌ์ฉํด์ผํจ. (์์ ํจ์)
- **MongoDB** ๋ SQL์ธ์ด๋ฅผ ์ฌ์ฉํ์ง ์๊ณ , ํ์ผ ๋ด์ ์ ๋ณด๊ฐ ๊ฐ์ฒด ํํ๋ก ์ ์ฅ๋จ.

  - DB๋ฅผ ์ค์  ์ปดํจํฐ์ ์ค์นํ๊ธฐ๋ ํ์ง๋ง ๋ฐฐํฌ ์ ๋ณด์ ์ ์ง๋ฅผ ์ํด ํด๋ผ์ฐ๋ ์๋น์ค๋ฅผ ์ด์ฉํ๋ ๊ฒ์ด ์์ .
  - ์ ์ ์๋๊ฐ ๋น ๋ฅด๋ฉฐ, ๋ฐฑ์๊ณผ ํธ๋ํฝ ๊ด๋ฆฌ์ ์ ๊ฒฝ์ ๋ ์จ๋ ๋จ.  
    <br>

- **MongoDB Settings** (๋ฌด๋ฃ ํธ์คํ)

  1.  [MobgoDB Atlas](https://www.mongodb.com/cloud/atlas/lp/try2?https://www.mongodb.com/cloud/atlas/lp/try2-aterms&utm_source=google&utm_campaign=gs_apac_south_korea_search_core_brand_atlas_desktop&utm_term=mongodb%20atlas&utm_medium=cpc_paid_search&utm_ad=e&utm_ad_campaign_id=12212624365&adgroup=115749706543&gclid=CjwKCAjw3cSSBhBGEiwAVII0Z_VbB0FGyTHppv24KCVIr-Kn7ARePSG0yPsoPpFvJrOaZAznxERkahoCoKsQAvD_BwE) ์ ์
  2.  ๊ตฌ๊ธ ์์ด๋ ๋ก๊ทธ์ธ
  3.  ๋ฌด๋ฃํฐ์ด ๋ฐ ํด๋ผ์ฐ๋ (aws - seoul) ์ ํ
  4.  Database Access - accout/pw
  5.  Network Access - IP (access from anywhere)
  6.  Database - Browse Collections - Add my Own Data - database name (woong_app), collection name (post)
  7.  ์ค์น ๋ฐ ์ฐ๋

      ```
         npm install mongodb
      ```

      ```javascript
      const MongoClient = require("Mongodb").MongoClient;

      MongoClient.connect(
      	"mongodb+srv://DB๊ณ์ ์์ด๋:DB๊ณ์ ํจ์ค์๋@cluster0-qaxa3.mongodb.net/๋ฐ์ดํฐ๋ฒ ์ด์ค์ด๋ฆ?retryWrites=true&w=majority",
      	(err, client) => {
      		// ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ ์ ํ ์คํํ  ์ฝ๋ ์์ฑ
      	},
      );
      ```

  8.  ์ค์  ํ์ผ ์ ์ฉ >> routes/Admin.js ๋ฐ express-server.js ํ์ผ ์ฐธ๊ณ . (์ถํ README ๋ณ๊ฒฝ!!!!!!!!!!)
      <br>
      <br>

### ๐ AJAX:

---

<br>

- ์๋ฒ์ ์์ฒญํ๋ ๊ฒ์ ๋์์ฃผ๋ Javascript ๋ฌธ๋ฒ.
- ํ์ด์ง ์๋ก๊ณ ์นจ ์์ด ์๋ฒ์ ์์ฒญํ๋ ๊ฒ์ ๋์์ค.
- ๊ธฐ๋ณธ ๋ฌธ๋ฒ
  ```javascript
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    // npm instatll jquery๋ก ๋์ฒด ๊ฐ๋ฅ
    <script>
      $.ajax({
        method: "",
        url: "",
        data: "",
      }).done((result) => {
        // ์์ฒญ ์ฑ๊ณต ์ ์คํ ํ  ํจ์
      }).fail((result) => {
        // ์์ฒญ ์คํจ ์ ์คํ ํ  ํจ์
      })
    </script>
  ```
- **nunjucks์์ ์ ์ฉ์ด ์๋๋ ๊ฑด์ง ๋ด๊ฐ ๋ชปํ๋ ๊ฑด์ง ๋ชจ๋ฅด๊ฒ ๋๋ฐ,,, ๋ค๋ฅธ ๋ฐฉ์์ผ๋ก ๋ฐ์ดํฐ๋ฅผ ๋ค๋ฃธ.**
