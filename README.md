# Disciplină — aplicație de rutină zilnică

O aplicație web (PWA) simplă: adaugi task-uri zilnice, le bifezi, primești remindere repetate până le faci, și vezi rapoarte săptămânale/lunare. Toate datele stau doar pe telefonul tău (nu există server, nu există cont).

## Ce conține folderul
- `index.html` — toată aplicația (interfață + logică)
- `manifest.webmanifest` — permite „Adaugă pe ecranul principal” pe iPhone
- `sw.js` — permite funcționarea offline
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — iconițele aplicației

## Pas 1 — Pune aplicația pe internet, gratis, cu GitHub Pages

1. Creează un cont pe [github.com](https://github.com) dacă nu ai.
2. Apasă **New repository** (buton verde). Dă-i un nume, ex: `disciplina`. Lasă-l **Public**. Nu bifa „Add README" (avem deja unul).
3. Pe pagina repo-ului nou, apasă **uploading an existing file** (sau `Add file → Upload files`).
4. Trage toate cele 6 fișiere din acest folder (`index.html`, `manifest.webmanifest`, `sw.js`, cele 3 iconițe, `README.md`) și apasă **Commit changes**.
5. Mergi la **Settings → Pages** (în meniul din stânga al repo-ului).
6. La **Source**, alege **Deploy from a branch**, branch **main**, folder **/ (root)**, apoi **Save**.
7. Așteaptă 1–2 minute. Reîncarcă pagina Settings → Pages; sus va apărea un link de forma:
   `https://<numele-tau-de-utilizator>.github.io/disciplina/`

Acesta e link-ul aplicației tale, accesibil din orice browser, de oriunde.

## Pas 2 — Instaleaz-o pe iPhone

1. Deschide link-ul de mai sus **din Safari** pe iPhone (obligatoriu Safari, nu Chrome — altfel „Add to Home Screen" nu instalează o aplicație completă).
2. Apasă butonul **Partajează** (pătratul cu săgeata în sus, din bara de jos).
3. Alege **Adaugă pe ecranul principal** (Add to Home Screen).
4. Apasă **Adaugă**.

Acum ai o iconiță pe ecranul principal, ca orice altă aplicație. Deschide-o de acolo (nu din Safari) — abia așa funcționează corect notificările și modul offline.

## Pas 3 — Activează notificările

Prima dată când deschizi aplicația (din iconița de pe ecran, nu din Safari), mergi la tab-ul **Setări** și apasă **Activează** lângă „Notificări". iOS o să-ți ceară confirmarea o singură dată.

### Important de știut despre notificări pe iPhone
Safari/iOS trimite notificări din aplicații web **doar cât timp aplicația a fost deschisă recent** (rulează în fundal o vreme, dar nu la nesfârșit, ca o aplicație nativă din App Store). Aplicația verifică singură, cât e deschisă sau redeschisă, dacă ai task-uri nebifate și trimite remindere repetate la intervalul pe care îl setezi. Dacă vrei remindere garantate 100% chiar cu telefonul complet inactiv zile la rând, varianta e o aplicație nativă (Swift) cu notificări locale programate de sistem — pot să-ți pregătesc și asta dacă ajungi la un Mac, sau găsim un serviciu care trimite notificări push de pe un server, ceea ce e un pas în plus (cont gratuit pe un serviciu de genul, ex. OneSignal).

## Cum actualizezi aplicația mai târziu
Dacă vrei să modific ceva (culori, funcții noi), îți dau fișierul `index.html` actualizat — îl reîncarci în GitHub (Add file → Upload files, suprascrie fișierul vechi) și e live în câteva secunde. Datele tale (task-uri, istoric) nu se pierd, pentru că stau salvate local pe telefon, nu în cod.

## Backup-ul datelor tale
Din **Setări → Salvează backup** poți exporta tot istoricul într-un fișier. Ține-l undeva (Files, email către tine) — dacă vreodată ștergi din greșeală aplicația sau schimbi telefonul, îl restaurezi din **Setări → Restaurează backup**.
