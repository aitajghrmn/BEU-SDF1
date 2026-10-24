🎓 Universitet Tədbir İdarəetmə Sistemi (Event Management System)Universitet daxilində keçirilən elmi konfransların, seminarların, təlimlərin, müsabiqələrin və digər tədbirlərin idarə olunması, iştirakçı qeydiyyatı və statistik təhlillərin aparılması üçün hazırlanmış interaktiv Web tətbiqi.📌 MündəricatLayihə haqqındaTexnologiya Steki və ArxitekturaSistemin Funksional İmkanlarıVerilənlər Bazasının Strukturu (Database Schema)Fərdi Əlavə Tapşırıq (Bonus Feature)Proqram Təminatının Keyfiyyəti və SOLID PrinsipləriTest Ssenariləri və NəticələriAI (Süni İntellekt) İstifadə JurnalıMüdafiə üçün Tövsiyələr🎯 Layihə haqqındaBu layihə universitet tədbirlərinin təşkilini rəqəmsallaşdırmaq və avtomatlaşdırmaq məqsədilə yaradılmışdır. Tələbələr və müəllimlər tədbirləri rahatlıqla axtara, kateqoriyalara görə süzgəcdən keçirə, qeydiyyatdan keçə və iştirakçı limitlərinə canlı nəzarət edə bilərlər.🛠 Texnologiya Steki və ArxitekturaTexnologiya Seçimləri və Əsaslandırılması:Frontend:HTML5 — Səhifənin semantik strukturunu təmin edir.Tailwind CSS — Müasir, responsive (mobil uyğun) və sürətli UI dizaynı üçün.FontAwesome — İnteraktiv ikonlar üçün.Chart.js — Statistik məlumatları vizual qrafiklərlə göstərmək üçün.Backend Məntiqi (Business Logic):Vanilla JavaScript (ES6+) — Tədbir limitlərinin yoxlanması, təkrar qeydiyyatın qarşısının alınması, gözləmə siyahısının idarə olunması və verifikasiyalar üçün modul/OOP strukturu.Database (Verilənlər Bazası):Browser LocalStorage / SessionStorage (Prototip üçün) / MySQL/PostgreSQL (Relasion sxem sənədləşdirilib).Versiya İdarəetməsi: Git & GitHub.🏢 Arxitektura Modeli (3-Tier Architecture)Presentation Layer (Frontend): İstifadəçi interfeysi və formalar.Business Logic Layer (Backend): Məlumatların doğruluğunu (validation), limitləri və biznes qaydalarını yoxlayan OOP sinifləri (EventManager, RegistrationManager).Data Access Layer (Database): Məlumatların saxlanılması və yenilənməsi.⚙️ Sistemin Funksional İmkanları1. Tədbirlərin İdarə Edilməsi (CRUD)Yeni tədbirlərin yaradılması (Ad, təsvir, kateqoriya, tarix, saat, keçirilmə yeri, max iştirakçı sayı).Tədbir məlumatlarının redaktəsi və silinməsi.Keçmiş və gələcək tədbirlərin avtomatik fərqləndirilməsi (Tarix məntiqinə əsasən).2. Axtarış və FiltrasiyaAd və keçirilmə yerinə görə canlı axtarış.Kateqoriyaya görə süzgəc.Axtarış nəticəsi tapılmadıqda istifadəçiyə anlaşıqlı bildirişin göstərilməsi.3. İştirakçı Qeydiyyatı və Gözləmə Siyahısı (Waitlist)Tədbirə qeydiyyat olma və qeydiyyatı ləğv etmə imkanı.Təkrar qeydiyyatın qarşısının alınması: Bir istifadəçi eyni tədbirə ikinci dəfə yazıla bilməz.Limitə nəzarət və Avtomatik Keçid: Tədbirin tutumu dolduqda istifadəçi Gözləmə Siyahısına (Waitlist) əlavə olunur. Təstiq olunmuş iştirakçı qeydiyyatını ləğv etdikdə gözləmə siyahısındakı ilk şəxs avtomatik olaraq əsas siyahıya keçir.4. İdarəetmə Paneli və Statistika (Dashboard)Ümumi tədbir və qeydiyyat saylarının göstərilməsi.Ən çox iştirakçısı olan top tədbirlər.Kateqoriyalar üzrə tədbirlərin paylanması (Dairəvi qrafik - Chart.js).🗄 Verilənlər Bazasının Strukturu (Database Schema)Sistem 3-cü Normal Formaya (3NF) uyğunlaşdırılmış 4 əsas əlaqəli cədvəldən ibarətdir:SQL-- 1. Kateqoriyalar Cədvəli
CREATE TABLE categories (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL UNIQUE
);

-- 2. İstifadəçilər Cədvəli
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(150) NOT NULL,
    email VARCHAR(150) UNIQUE NOT NULL
);

-- 3. Tədbirlər Cədvəli
CREATE TABLE events (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    description TEXT,
    category_id INT,
    event_date DATE NOT NULL,
    event_time TIME NOT NULL,
    location VARCHAR(200) NOT NULL,
    max_participants INT NOT NULL,
    FOREIGN KEY (category_id) REFERENCES categories(id) ON DELETE SET NULL
);

-- 4. Qeydiyyatlar və Gözləmə Siyahısı Cədvəli
CREATE TABLE registrations (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    event_id INT NOT NULL,
    status ENUM('CONFIRMED', 'WAITLISTED', 'CANCELLED') DEFAULT 'CONFIRMED',
    attended BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
    FOREIGN KEY (event_id) REFERENCES events(id) ON DELETE CASCADE,
    CONSTRAINT unique_user_event UNIQUE (user_id, event_id)
);
Cədvəl Əlaqələrinin Əsaslandırılması:categories ↔ events (1-to-Many): Bir kateqoriyaya birdən çox tədbir aid ola bilər.users ↔ events (Many-to-Many): İstifadəçilər çoxlu tədbirlərə, tədbirlər də çoxlu istifadəçilərə malik ola bilər. Bu əlaqə registrations cədvəli vasitəsilə qurulmuşdur.unique_user_event məhdudiyyəti: Bir istifadəçinin eyni tədbirə təkrar yazılmasının qarşısını verillənlər bazası səviyyəsində alır.🎁 Fərdi Əlavə Tapşırıq (Bonus Feature)Gözləmə Siyahısı (Waitlist) və Avtomatik Davamiyyət/Eksport İdarəetməsi:Tədbir limiti dolduqda sistem istifadəçini rədd etmir, statusunu WAITLISTED edir.Əsas siyahıdan biri çıxdıqda avtomatik olaraq növbədəki ilk şəxs CONFIRMED statusuna keçir.İştirakçı Davamiyyəti (Attendance Tracking): İdarəçi tədbir zamanı iştirakçıların gəlib-gəlmədiyini qeyd edə bilir.CSV Eksport: Tədbir üzrə iştirakçı siyahısını .csv formatında endirmək mümkündür.📐 Proqram Təminatının Keyfiyyəti və SOLID PrinsipləriSingle Responsibility Principle (SRP): EventManager yalnız tədbir CRUD əməliyyatlarına, RegistrationManager yalnız qeydiyyat məntiqinə, UI modulları isə render işlərinə cavabdehdir.Open/Closed Principle (OCP): Yeni statistika növü və ya süzgəc əlavə etmək üçün mövcud kodu dəyişmədən yeni funksiya/modul inteqrasiya edilə bilir.Clean Code & DRY: Təkrar kodlar funksiyalara çıxarılıb, dəyişən adları mənalı və aydın seçilib.Exception Handling: Şəbəkə, boş xana və ya limit aşımı zamanı istifadəçiyə vizual, anlaşıqlı xəta mesajları (Alert/Toast) göstərilir.🧪 Test Ssenariləri və NəticələriTest №Test SsenarisiGözlənilən NəticəNəticəStatusTS-01Məcburi sahələri boş qoyub tədbir yaratmaqForm göndərilmir, xəta mesajı göstərilir.Keçdi✅ PASSEDTS-02Keçmiş tarixə tədbir əlavə etməkSistem keçmiş tarixi qəbul etmir.Keçdi✅ PASSEDTS-03Eyni tədbirə təkrar qeydiyyatdan keçmək"Siz artıq qeydiyyatdan keçmisiniz" xətası çıxır.Keçdi✅ PASSEDTS-04Limit dolduqda qeydiyyat olmaqİstifadəçi avtomatik "Gözləmə siyahısı"na əlavə edilir.Keçdi✅ PASSEDTS-05Qeydiyyatı ləğv etmək (Gözləmə siyahısı olduqda)Ləğv olunur və gözləmədəki ilk şəxs əsas siyahıya keçir.Keçdi✅ PASSED🤖 AI (Süni İntellekt) İstifadə JurnalıMərhələAI Prompt / SorğuAI Təklifi / CavabıDüzəlişlər və Öyrənilən AnlayışlarArxitektura"Universitet tədbir sistemi üçün relasion DB strukturu necə olmalıdır?"4 cədvəlli relational sxem təklif etdi.registrations cədvəlinə attended və status sahələri əlavə edildi.Kodlaşdırma"JavaScript-də təkrar qeydiyyatın və limitin yoxlanması algoritmi."Modal və Validation funksiyaları yazıldı.Məntiq RegistrationManager klassı daxilində kapsullaşdırıldı.Testləşdirmə"Bu sistem üçün 5 əsas edge-case test ssenarisi hazırla."Limit aşımı və keçmiş tarix testləri təklif olundu.Test ssenariləri sənədləşdirildi və koda validasiyalar artırıldı.
