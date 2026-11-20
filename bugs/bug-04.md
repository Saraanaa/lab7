# BUG-04: Буруу JSON хүсэлт 400 биш 200 OK буцаана

Орчин: Уншлагын жагсаалт v2.0, curl.exe/Node.js, 2026-11-19

## Дахин гаргах алхам

1. `invalid.json` файлд яг `{ "title":` гэж бичнэ.
2. `curl.exe -i -X POST http://localhost:3000/api/books -H "Content-Type: application/json" --data-binary "@invalid.json" | Tee-Object -FilePath evidence/bug-04-curl.txt` ажиллуулна.
3. Бүтэн HTTP гаралтыг `evidence/bug-04-curl.txt`-оос шалгана.

Хүлээгдэж байсан: HTTP 400 болон ойлгомжтой алдааны мэдээлэл.

Бодит үр дүн: HTTP 200, `{"result":"OK"}`; ном нэмэгдээгүй ч хүсэлт амжилттай мэт харагдана.

Ноцтой байдал: Critical — API-ийн алдааны contract зөрчигдөж байна.

Олсон аялал: Saboteur.  
Хавсралт: [evidence/bug-04-curl.txt](../evidence/bug-04-curl.txt)

