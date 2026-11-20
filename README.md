# Lab 07 — Session-Based Test Management

Оюутан: Г. Саранчимэг B232274001

Код: `node app/app.js`

Node хувилбар: `v22.19.0`

Browser: Google Chrome `142.0.7444.60` (Chromium engine)

Апп: `http://localhost:3000`

Энэ repository нь өгсөн `app.js` дээр хийсэн exploratory testing-ийн charter, session report, нотолгоо болон bug report-уудыг агуулна. Аппын эх кодыг өөрчлөөгүй.

## Файлын бүтэц

- [charter.md](./charter.md) — session эхлэхээс өмнө бичсэн charter
- [session-report.md](./session-report.md) — туршилтын явц, саад, цагийн зарцуулалт
- [bugs/](./bugs/) — тус бүрдээ нэг үндэслэлтэй согогийн тайлан
- [evidence/](./evidence/) — API туршилтын бүтэн гаралт
- [screenshots/](./screenshots/) — UI нотолгооны зураг (BUG-01, BUG-02, BUG-03, BUG-05, BUG-06, BUG-07, BUG-08)

## Дүгнэлт

Saboteur аялал хамгийн өндөр үр дүнтэй байсан: буруу JSON хүсэлт 200 OK авч байгаа нь API-ийн тодорхой зөрчил болохыг curl-ийн бүтэн гаралт баталсан. Supermodel аяллаар `/old` холбоосын 500 алдаа болон устгасны дараах буруу мессеж ажиглагдсан. Fed-Ex аяллаар статистикийн тоо бодит жагсаалттай нийцэхгүй, мөн давхардсан ном нэмэгдэх боломжтойг илрүүлсэн. Charter-аас гадуур он талбарын баталгаажуулалт болон case-sensitive хайлт ажиглагдсан. Charter commit нь session эхлэхээс өмнө хийгдэж, 01:55–02:55-ийн 60 минутын session-ийн оролт, бодит үр дүн, screenshot болон raw API evidence-ийг тайлангуудтай холбосон.

