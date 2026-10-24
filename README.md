UniEvents — Universitet Tədbirlərinin İdarə Edilməsi və Qeydiyyat Sistemi
1. Layihə haqqında

Layihənin adı: Universitet Tədbirlərinin İdarə Edilməsi və Qeydiyyat Sistemi (University Event Management and Registration System)

Fənn: Proqramlaşdırma texnologiyaları

Layihənin növü: Web tətbiq

İstifadə məqsədi: Universitetdə keçirilən elmi konfransların, seminarların, təlimlərin, müsabiqələrin və digər tədbirlərin idarə olunması.

UniEvents universitet tədbirləri haqqında məlumatların yaradılması, göstərilməsi, redaktə edilməsi, silinməsi və iştirakçı qeydiyyatının idarə olunması üçün hazırlanmış web tətbiqidir. Sistem, həmçinin tədbirlərin statistik təhlilini, iştirakçı siyahısının ixracını və tədbir dolduqda gözləmə siyahısının idarə edilməsini təmin edir.

Layihənin əsas məqsədi universitet tədbirlərinin idarə edilməsini sadələşdirmək, qeydiyyat prosesini avtomatlaşdırmaq və tədbirlər haqqında məlumatları istifadəçilər üçün əlçatan etməkdir.

2. Layihənin əsas funksiyaları
2.1. Tədbirlərin idarə edilməsi
Yeni tədbir yaratmaq.
Mövcud tədbirlərin məlumatlarını redaktə etmək.
Tədbirləri silmək.
Tədbirin adını, təsvirini, kateqoriyasını, tarixini, saatını, keçirilmə yerini və maksimum iştirakçı sayını saxlamaq.
Keçmiş və gələcək tədbirləri fərqləndirmək.
Tədbirlərin siyahısını kartlar şəklində göstərmək.
2.2. Axtarış və filtrasiya
Tədbirləri adına görə axtarmaq.
Keçirilmə yerinə görə axtarış aparmaq.
Kateqoriyaya görə filtr tətbiq etmək.
Keçmiş və gələcək tədbirləri ayırmaq.
Axtarış nəticəsi olmadıqda istifadəçiyə məlumat göstərmək.
Filtrləri sıfırlamaq.
2.3. İştirakçı qeydiyyatı
İstifadəçinin tədbirə qeydiyyatdan keçməsi.
Eyni istifadəçinin eyni tədbirə təkrar qeydiyyatının qarşısının alınması.
Tədbirin maksimum iştirakçı sayının yoxlanılması.
Tutum dolduqda istifadəçinin gözləmə siyahısına əlavə edilməsi.
Qeydiyyatın və gözləmə siyahısına müraciətin ləğvi.
Qeydiyyatdan keçmiş iştirakçıların sayının göstərilməsi.
2.4. Gözləmə siyahısı — Waitlist

Gözləmə siyahısı layihənin əlavə funksiyalarından biridir.

Tədbirin iştirakçı limiti dolduqda yeni müraciət edən istifadəçi gözləmə siyahısına əlavə edilir. İştirakçılardan biri qeydiyyatını ləğv etdikdə və boş yer yarandıqda siyahının ilk iştirakçısı avtomatik olaraq əsas qeydiyyat siyahısına keçirilir.

Bu mexanizm FIFO (First In, First Out) prinsipinə əsaslanır. Yəni gözləmə siyahısına daha əvvəl əlavə edilmiş iştirakçıya üstünlük verilir.

2.5. İştirakçı siyahısı və davamiyyət
Tədbir üzrə qeydiyyatdan keçmiş iştirakçıların siyahısını göstərmək.
İştirakçıların qeydiyyat tarixini göstərmək.
İştirakçının davamiyyət statusunu dəyişmək.
Gözləmə siyahısını ayrıca göstərmək.
2.6. CSV formatında ixrac

İştirakçı siyahısını CSV formatında fayla ixrac etmək mümkündür. İxrac olunan məlumatlara istifadəçi ID-si, ad-soyad, qeydiyyat tarixi və davamiyyət statusu daxildir.

CSV formatı məlumatların elektron cədvəl proqramlarında açılmasına və əlavə təhlil edilməsinə imkan verir.

2.7. İdarəetmə paneli və statistika

İdarəetmə panelində aşağıdakı göstəricilər təqdim olunur:

Ümumi tədbirlərin sayı.
Ümumi qeydiyyatların sayı.
Gözləmə siyahısındakı müraciətlərin sayı.
Tədbirlərin ümumi tutumuna əsasən doluluq nisbəti.
Kateqoriyalar üzrə tədbirlərin paylanması.
Ən çox iştirakçısı olan tədbirlər.

Statistik qrafiklər Chart.js kitabxanası vasitəsilə yaradılır.

3. İstifadə olunan texnologiyalar
Texnologiya	İstifadə məqsədi
HTML5	Səhifələrin və interfeys elementlərinin strukturu
CSS3	Vizual tərtibat və səhifələrin görünüşü
Tailwind CSS	Responsive dizayn və hazır utility sinifləri
JavaScript (ES6+)	Biznes məntiqi və interaktivlik
Chart.js	Statistik qrafiklərin yaradılması
Font Awesome	İkonların göstərilməsi
LocalStorage	Məlumatların brauzerdə saxlanılması
Git və GitHub	Versiyaların idarə edilməsi və mənbə kodunun saxlanılması
ChatGPT	Layihənin planlaşdırılması, kodun izahı və test ssenarilərinin hazırlanmasına kömək
Texnologiyaların seçilməsinin əsaslandırılması

HTML5 səhifənin semantik strukturunu qurmaq üçün, Tailwind CSS isə interfeysin daha sürətli və uyğunlaşan formada hazırlanması üçün seçilmişdir.

JavaScript tədbirlərin idarə olunması, qeydiyyat yoxlamaları, axtarış, filtrasiya, statistika və istifadəçi ilə qarşılıqlı əlaqə üçün istifadə edilir.

Chart.js statistik göstəriciləri vizual formada təqdim etməyə imkan verir. LocalStorage isə prototipdə məlumatların səhifə yeniləndikdən sonra da brauzerdə saxlanılmasını təmin edir.

Texniki məhdudiyyət: Hazırkı versiyada ayrıca backend texnologiyası və server verilənlər bazası (məsələn, MySQL və ya PostgreSQL) inteqrasiya edilməyib. LocalStorage yalnız cari brauzerdə işləyir və real çoxistifadəçili sistem üçün server tərəfli saxlanma mexanizmini əvəz etmir.

4. Layihənin arxitekturası

Layihənin hazırkı versiyası brauzerdə işləyən JavaScript tətbiqidir. Kodun məsuliyyətləri siniflər və köməkçi funksiyalar arasında bölüşdürülüb.

4.1. Arxitektura komponentləri

1. İstifadəçi interfeysi (UI)

HTML və Tailwind CSS vasitəsilə yaradılıb. Tədbir kartları, qeydiyyat düymələri, modal pəncərələr, filtrasiya elementləri və statistika səhifəsi bu hissəyə daxildir.

2. EventManager sinfi

Tədbirlərlə bağlı məlumatların idarə edilməsinə cavabdehdir:

getAllEvents() — bütün tədbirləri qaytarır.
getEventById(id) — ID üzrə tədbiri tapır.
addEvent(eventData) — yeni tədbir yaradır.
updateEvent(id, updatedData) — tədbiri yeniləyir.
deleteEvent(id) — tədbiri silir.
registerUser(eventId, user) — qeydiyyat və gözləmə siyahısı məntiqini icra edir.
cancelRegistration(eventId, userId) — qeydiyyatı ləğv edir və uyğun halda gözləmə siyahısından iştirakçı keçirir.
toggleAttendance(eventId, userId) — davamiyyət statusunu dəyişir.
saveToStorage() — məlumatları LocalStorage-a yazır.

3. Application sinfi

İstifadəçi interfeysini və tətbiqin ümumi iş axınını idarə edir. Səhifələr arasında keçid, tədbirlərin göstərilməsi, formaların emalı, bildirişlər, statistik göstəricilər və testlərin işə salınması bu sinfin məsuliyyətinə daxildir.

4. Məlumatların saxlanması

EventManager tədbirləri JavaScript obyektləri massivində saxlayır. Məlumatlar JSON formatına çevrilərək localStorage daxilində unievents_data açarı ilə yazılır.

İlkin məlumatlar INITIAL_EVENTS massivindən götürülür.

4.2. Məlumat axını
İstifadəçi interfeysdə əməliyyat seçir.
Application uyğun funksiyanı çağırır.
EventManager məlumatı yoxlayır və dəyişiklikləri tətbiq edir.
Dəyişdirilmiş məlumatlar LocalStorage-a yazılır.
İnterfeys yenilənir və nəticə istifadəçiyə göstərilir.

Qeyd: Bu, frontend daxilində işləyən arxitekturadır. Ayrı frontend, backend və database arasında HTTP/API əlaqəsi hazırkı versiyada qurulmayıb.

5. Məlumat modeli

Hazırkı tətbiqdə məlumatlar JavaScript obyektləri şəklində saxlanılır.

5.1. Events — Tədbirlər
Sahə	Tip	Təyinat
id	Number	Tədbirin unikal identifikatoru
title	String	Tədbirin adı
category	String	Tədbirin kateqoriyası
dateTime	String	Tədbirin tarixi və saatı
location	String	Keçirilmə yeri
capacity	Number	Maksimum iştirakçı sayı
description	String	Tədbirin təsviri
registrations	Array	Qeydiyyatdan keçmiş iştirakçılar
waitlist	Array	Gözləmə siyahısındakı iştirakçılar
5.2. Registrations — Qeydiyyatlar

Hər qeydiyyat obyektində aşağıdakı sahələr saxlanılır:

userId — iştirakçının ID-si.
userName — iştirakçının adı.
registeredAt — qeydiyyat vaxtı.
attended — davamiyyət statusu.
5.3. Waitlist — Gözləmə siyahısı

Hər gözləmə siyahısı obyektində aşağıdakı sahələr mövcuddur:

userId — iştirakçının ID-si.
userName — iştirakçının adı.
addedAt — gözləmə siyahısına əlavə olunma vaxtı.
5.4. Gələcək verilənlər bazası modeli

Layihənin server əsaslı versiyasında aşağıdakı əlaqəli cədvəllərdən istifadə etmək məqsədəuyğundur:

Users — istifadəçilər.
Categories — tədbir kateqoriyaları.
Events — tədbirlər.
Registrations — qeydiyyatlar.
Waitlist — gözləmə siyahısı.

Events.category_id sahəsi Categories.id sahəsinə, Registrations.event_id sahəsi Events.id sahəsinə, Registrations.user_id sahəsi isə Users.id sahəsinə xarici açarla bağlana bilər.

Registrations cədvəlində (event_id, user_id) kombinasiyasına UNIQUE məhdudiyyəti tətbiq etməklə eyni istifadəçinin eyni tədbirə təkrar qeydiyyatının qarşısı verilə bilər. Eyni yanaşma gözləmə siyahısı
