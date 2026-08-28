# HR Employee Attrition & Retention Analysis — Hesabat

## 1. Data Təmizləmə və Hazırlıq Addımları
- **Datasetin Yüklənməsi:** `WA_Fn-UseC_-HR-Employee-Attrition.csv` — 1,470 sətir, 35 sütun.
- **Boş Dəyər və Təkrar Sətir Yoxlanışı:** Datada heç bir buraxılmış dəyər (Nulls) və ya təkrar sətir (Duplicates) aşkar edilmədi.
- **Attrition Sütununun Kodlaşdırılması:** Binary və numerik analizlər aparmaq üçün `Attrition` sütunundakı `"Yes"` / `"No"` dəyərləri `1` və `0` göstəricilərinə çevrildi.
- **Qruplaşdırma və Transformativ Sütunların Yaradılması:** 
  - `YearsAtCompany` göstəricisi əsasında staj qrupları (`Tenure Groups`: `0-2 years`, `3-5 years`, `6-10 years`, `11+ years`) yaradıldı.
  - `MonthlyIncome` sütunu üzrə kvartillər (`Income Quartiles`: `Q1`, `Q2`, `Q3`, `Q4`) formalaşdırıldı.
- **Maliyyə Təsirinin Hesablanması:** Hər ayrılan işçinin əvəzlənmə xərci şərti olaraq 6 aylıq əməkhaqqı (`MonthlyIncome * 6`) həcmində götürülərək ümumi maliyyə zərəri hesabla təyin olundu.

## 2. Əsas Statistik Göstəricilər

- **Cəmi İşçi Sayı:** 1,470 nəfər.
- **Attrition Paylanması:** 1,233 nəfər Qalanlar (83.88%), 237 nəfər Ayrılanlar (16.12%).
- **Ümumi Attrition Rate:** **16.12%**.
- **Aylıq Gəlir Fərqi:** Qalan işçilərin orta aylıq gəliri **$6,832.74**, ayrılanların orta aylıq gəliri isə **$4,787.09** təşkil edir (ayrılanlar ~30% daha az gəlir əldə edir).
- **Şirkət Stajı Müqayisəsi:** Qalan işçilərin orta şirkət stajı **7.37 il**, ayrılanların orta stajı isə **5.13 il** təşkil edir.
- **İş Məmnuniyyəti (Job Satisfaction):** Qalanlarda orta göstərici **2.78 / 4**, ayrılanlarda isə **2.47 / 4** səviyyəsindədir.
- **Tenure Group üzrə Attrition Rate:** 
  - `0-2 years`: **29.82%** (ən yüksek ayrılma nisbəti)
  - `3-5 years`: **13.82%**
  - `6-10 years`: **12.28%**
  - `11+ years`: **8.13%**
- **Income Quartiles üzrə Attrition Rate:**
  - `Q1` (ən aşağı gəlir): **29.27%** (ən yüksək ayrılma nisbəti)
  - `Q2`: **14.21%**
  - `Q3`: **10.63%**
  - `Q4` (ən yüksək gəlir): **10.33%**
- **Maliyyə Zərəri (Cost of Attrition):** 237 ayrılan işçinin şirkətə illik ümumi əvəzlənmə maliyyəti **$6,807,246.00** təşkil edir.

## 3. Executive Summary — 6 Main Findings

1. **İşə qəbulun ilk 2 ili şirkət üçün en böyük kadr itkisi risk zonasıdır.** `0-2 il` stajı olan işçilər arasında ayrılma faizi **29.82%** təşkil edir ki, bu da ümumi orta göstəricidən (16.12%) demək olar ki, iki dəfə yüksəkdir. Staj artdıqca ayrılma riski kəskin azalır (11+ il stajda 8.13%).

2. **Aşağı gəlir səviyyəsi kadr axınının əsas aparıcı drayveridir.** Ən aşağı gəlir kvartilində (`Q1`) olan işçilər **29.27%** ayrılma nisbətinə malikdir. Yüksək gəlir qruplarında (`Q3` və `Q4`) bu göstərici ~10%-ə qədər düşür.

3. **Gəlir və staj göstəriciləri ayrılanlar üçün kəskin şəkildə daha aşağıdır.** Şirkətdən ayrılan işçilər orta hesabla **$2,045 daha az aylıq gəlir** əldə edir ($4,787 vs $6,832) və şirkətdə **2.24 il daha az staja** malikdirlər (5.13 il vs 7.37 il).

4. **İş məmnuniyyəti göstəricisi (Job Satisfaction) ayrılma qərarına birbaşa təsir edir.** Ayrılan işçilərin iş məmnuniyyəti balı (2.47) qalan işçilərin göstəricisindən (2.78) nəzərəçarpan dərəcədə aşağıdır.

5. **Kadr axını şirkət üçün çox ciddi maliyyə yükü yaratmaqdadır.** İşdən ayrılan 237 nəfərin əvəzlənməsi və yenilərinin işə adaptasiyası şirkətə illik **$6.8 milyon dollardan çox** birbaşa maliyyə itkisi vurur.

6. **Kadr itkisi təsadüfi deyil, müəyyən demoqrafik və iqtisadi seqmentlərdə cəmləşib.** Analiz göstərir ki, kadr axını əsasən "Yeni işçilər + Aşağı Əməkhaqqı" kəsişməsində cəmləşərək fokuslanmış müdaxilə tələb edir.

## 4. HR Recommendations

1. **İlk 2 İl Üçün Onboarding və Adaptasiya Proqramlarının Yenidən Qurulması:**
   İlk 2 ildəki 29.82%-lik kadr itkisini azaltmaq üçün yeni işçilər üçün xüsusi mentorluq, mütəmadi 30/60/90 günlük adaptasiya görüşləri və saxlanma (retention) strategiyaları tətbiq edilməlidir.

2. **Aşağı Qrup Əməkhaqqı Siyasətinin Və Kvartillərin İncələnməsi:**
   `Q1` gəlir qrupundakı 29.27%-lik kadr axınının qarşısını almaq üçün bazar qiymətləndirilməsi (market benchmark) aparılmalı və giriş səviyyəsindəki əməkhaqqı paketlərinə baxılmalıdır.

3. **Erkən Xəbərdarlıq Sisteminin (Early Warning System) Yaradılması:**
   İş məmnuniyyəti balı 1 və 2 olan işçilər dərhal risk qrupuna daxil edilməli, HR tərəfindən onlarla fərdi "Stay Interview" (şirkətdə saxlanma sorğuları) müsahibələri keçirilməlidir.

4. **Karyera Yolu Və İrəliləyiş İmkansızlıqlarının Aradan Qaldırılması:**
   İşçilərin ilk 3 ildə şirkətdən ayrılmaması üçün aydın daxili yüksəliş (promotion) və bacarıqların artırılması (upskilling) xəritəsi təqdim olunmalıdır.

5. **Maliyyə Zərərinin Azaldılması Üçün Retensiya Büdcəsinin Ayrılması:**
   İllik $6.8M maliyyə zərərini nəzərə alaraq, bu məbləğin cəmi 10-15%-i həcmində büdcə daxili bonus, saxlanma stimulları və iş şəraitinin yaxşılaşdırılması üçün HR Retensiya Fondu kimi ayrılmalıdır.