# Session report

Тестер: Saraanaa

Огноо: 2026-11-19, 01:55–02:55 (60 мин)  
Charter commit: 01:54:30 (session эхлэхээс өмнө)  
Session report хадгалсан: 02:56 (session дууссаны дараа)

Mission: Уншлагын жагсаалт аппын чанарыг шинжлэх

Charter: [charter.md](./charter.md)-д заасан Supermodel, Saboteur, Fed-Ex аяллууд.

## Тэмдэглэл

- 01:55 — **Оролт:** `node app/app.js`, Chrome 142.0.7444.60-д `http://localhost:3000`. **Бодит үр дүн:** нүүр хуудас болон эхний 3 ном харагдав.
- 02:03 — **Оролт:** `GET /api/books`, `GET /api/stats`, `Хуучин хувилбар`. **Бодит үр дүн:** stats `total=4`, жагсаалт 3; `/old` HTTP 500.
- 02:12 — **Оролт:** `title=""`, `author=""`, `year=""`, дараа нь `999`, `2101`, `abc`. **Бодит үр дүн:** validation-гүй мөрүүд нэмэгдэв; BUG-05/06 screenshot хадгалав.
- 02:22 — **Оролт:** хайлт `clean`, дараа нь `Clean Code`. **Бодит үр дүн:** эхнийх хоосон, хоёр дахь нь үр дүнтэй; BUG-03 screenshot хадгалав.
- 02:32 — **Оролт:** `Clean Code` / `Robert C. Martin`-ийг яг хуулж нэмээд delete хийв. **Бодит үр дүн:** duplicate нэмэгдэж, delete feedback `Ном нэмэгдлээ` хэвээр байв; BUG-07/08 screenshot хадгалав.
- 02:42 — **Оролт:** `curl.exe -i -X POST http://localhost:3000/api/books -H "Content-Type: application/json" --data-binary "@invalid.json"`, body `{ "title":`. **Бодит үр дүн:** HTTP 200 OK, `{"result":"OK"}`; raw output-ийг `Tee-Object`-оор хадгалав.
- 02:50 — **Оролт:** BUG-01–BUG-08-ийн алхам, үр дүн, attachment-уудыг тулгав. **Бодит үр дүн:** UI bug бүр screenshot-той, BUG-04 бүтэн curl output-той болсон.

## Саадуудад

## Шинэ chronology-correct session (charter commit-ийн дараа)

Charter commit: `9bf5d1a`, 2026-11-20 02:16:29 +08:00. Session window: 02:16–03:16 +08:00.

- 02:16 — **Оролт:** `http://localhost:3000/` нээв. **Бодит үр дүн:** нүүр хуудас ажиллаж, initial жагсаалт болон статистикийн мөр харагдав.
- 02:22 — **Оролт:** session-ийн одоогийн явцыг шалгав. **Бодит үр дүн:** session үргэлжилж байна; 03:16-д дуусгаж, дараа нь commit хийнэ.
- 02:23 — **Оролт:** `http://localhost:3000/old` руу орлоо. **Бодит үр дүн:** `Internal Server Error`, browser console-д HTTP 500 бүртгэгдэв; BUG-02 screenshot шинэчилсэн.
- 02:24 — **Оролт:** хайлтад `clean` оруулж `Хайх` дарлаа. **Бодит үр дүн:** жагсаалт шүүгдээгүй, `Clean Code`-ийн мөрүүд хэвээр үлдэв; BUG-03 screenshot шинэчилсэн.

- Өгөгдөл зөвхөн санах ойд хадгалагддаг тул серверийг дахин асаахад нэмсэн ном устдаг. Энэ нь даалгаврын өгсөн хязгаарлалт бөгөөд persistence-ийн bug гэж тооцоогүй.

## Цагийн зарцуулалт

Setup 10% · Тестийн дизайн ба гүйцэтгэл 65% · Согог судлах 25%

## Илэрсэн согогууд

BUG-01–BUG-08 тайлангуудыг [bugs/](./bugs/) хавтсанд хадгалсан. Буруу JSON-ийн бүтэн HTTP гаралт [evidence/bug-04-curl.txt](./evidence/bug-04-curl.txt)-д байна.

