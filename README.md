# MindSquared
Aplicația MindSquared este un program care are ca scop organizarea timpului elevilor dar și al
profesorilor oferind comoditate, o structură ierarhizată inteligent și ușor de utilizat, un instrument
digital ce în timp poate deveni indispensabil chiar și persoanelor care sunt mai puțin acomodate cu
tehnologia din ziua de azi, și nu în ultimul rând oferă performanță.
La deschiderea aplicației utilizatorul e direcționat la pagina de login, unde se poate conecta sau
să-și creeze un cont nou. Pentru partea de login, ne vom folosi de modulul Authentication al aplicatiei
Google Firebase. Acesta stocheaza pentru fiecare utilizator o adresa de email si o parola care este
protejata, detinatorul bazei de date neputand sa o acceseze.
La deschiderea aplicatiei, utilizatorul isi poate crea un nou cont. Pentru aceasta operatiune ne
vom folosi de modulele Authentication si Realtime Database ale Google Firebase. La crearea unui nou
cont, utilizatorul trebuie sa ofere informatii despre adresa sa de email, nume, prenume si sa isi aleaga o
parola. Ne vom folosi de modulul Authentification pentru ca utilizatorul sa se poate conecta de pe orice
dispozitiv doreste si pentru ca baza de date sa nu stocheze parole necriptate. In toate celelalte
operatiuni din cadrul aplicatiei folosim modulul Realtime Database, asa ca la creearea unui nou cont de
utilizator trebuie sa introducem datele despre acestea in baza de date, exceptand parola. In plus, pe
parcursul utilizarii, in baza de date vom atribui fiecarui elev clasele in care se afla.
Odată conectat la baza de date a aplicației, utilizatorul este redirecționat către pagina principală
- Dashboard, aceasta fiind și pagina de home. Aici se regăsesc 4 card view-uri, fiecare având o
funcționalitate aparte:
- Chat;
- Quiz;
- Calendar;
- Clase.
În partea de jos a aplicației se regăsește bara de navigare care are 3 butoane:
- Task-uri;
- Home;
- Notificări.
Clase:
Primul lucru pe care îl va face utilizatorul odată intrat în aplicație va fi următorul:
Dacă tipul utilizatorului este profesor, va accesa această rubrică pentru a crea numărul de clase
la care predă, generând astfel un id al acestor clase. De aici profesorul va avea un meniu cu toate clasele
date, de unde va fi capabil să vadă toți elevii care sunt în această clasă și eventual scorurile lor la teste,
evoluția lor etc. Profesorul va avea la îndemână o listă ierarhică în funcție de scorurile elevilor la teste, și
să observe statisticile fiecărui elev în parte și în comparație cu ceilalți. La această rubrică, va fi și un
buton de creare de grupuri care va împărți elevii în mod automat în funcție de scorurile pe care le au
aceștia la disciplina dată (pentru a exista egalitatea între echipe) și creează un chat nou pentru fiecare
utilizator cu membrii echipei sale.
Dacă tipul utilizatorului este elev, va trebui să intre în clasele create de profesori prin
intermediul unui link de invitație sau id-ul și parola clasei. Un meniu asemănător cu cel al profesorilor
vor avea și elevii, doar că ei nu vor avea o listă de clase ci o listă de discipline.
În baza de date, obiectul de clasă stochează o listă cu toți userii participanți, numele clasei, id-ul
generat, parola. Pentru fiecare user sunt stocate atributele pe care le are în acel grup, cum ar fi tipul
contului (administrator, elev, prof), scorurile elevilor etc.
Quiz:
Dacă tipul utilizatorului este profesor, el/ea va trebui să creeze teste de tip grilă cu 4-5 variante
de răspuns, numărul de întrebări fiind la discreția profesorului. În această rubrică, profesorul va avea un
buton pentru a putea vizualiza toate testele pe care le-a creat până la acel moment și eventual să
examineze elevii cu acel test oricând dorește el/ea. Tot în această rubrică, profesorul va avea un buton
prin care va putea vizualiza rezultatele elevilor, putând să analizeze rezultatele acestora, să observe
întrebările la care au greșit / au răspuns corect și eventual, selectând un elev anumit, să poată observe
rezultatele acestuia în comparație cu alte teste pe care le-a dat pe aceeași platformă la disciplina dată.
Dacă tipul utilizatorului este elev, acesta va trebui să intre într-un test prin intermediul unui cod
transmis de profesor la toată clasa. Elevul va avea un buton pentru a vizualiza care sunt rezultatele sale
la teste, iar la întrebările la care a răspuns greșit să vadă care este răspunsul corect iar eventual și o
explicație.
Task-uri (buton stânga meniu de jos):
În această rubrică, utilizatorul își poate fixa toate sarcinile pe care le are de făcut, anexând un
titlu, o descriere și un deadline al sarcinii, care ulterior va fi transmis calendarului.
Calendar:
Aceasta este o rubrică în care utilizatorul poate să vadă toate task-urile sale organizate vizual
(care au fost preluate din rubrică Task-uri). Când utilizatorul face tap pe un task, acesta poate seta un
reminder când să primească notificare înainte de task.
Notificări (buton dreapta meniu de jos):
Utilizatorul primește o notificare când:
- Un membru al unui grup din care face parte utilizatorul îndeplinește un task;
- Un task are un reminder setat de el pe calendar;
- A fost menționat de către alt utilizator într-o conversație din Chat;
Chat:
Atunci când aplicația împarte clasa în grupe, în chat pentru fiecare utilizator apare un grup cu
membrii echipei sale unde aceștia vor putea discuta între ei pentru a împărți sarcinile, stabili întâlniri
etc.
Chat-ul poate fi folosit și pentru a trimite mesaje private unui anumit utilizator. Tot prin chat,
elevii pot discuta cu profesorii în caz că au întrebări legate de proiecte / despre disciplina la care predă
profesorul.
