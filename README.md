# 📊 HR Employee Attrition & Retention Analysis

Bu layihə, şirkətdəki işçilərin işdən ayrılma (**Attrition**) səbəblərini analiz etmək, əsas kadr göstəricilərini (KPI) hesablamaq və kadr axınının şirkətə vurduğu maliyyə zərərini müəyyən etmək üçün Python (Pandas, Seaborn, Matplotlib) vasitəsilə hazırlanmışdır.

---

## 📌 Layihənin Məqsədi
* Şirkətdəki ümumi **Attrition Rate** (işdən ayrılma faizi) göstəricisini hesablamaq.
* İşdən ayrılan və qalan işçilərin gəlir, təcrübə və iş məmnuniyyəti fərqlərini müqayisə etmək.
* İşçilərin şirkətdəki iş stajı (**Tenure Group**) və gəlir səviyyələrinə (**Income Quartiles**) görə ayrılma risklərini analiz etmək.
* Kadr axınının şirkətə illik maliyyə təsirini (**Cost of Attrition**) hesablamaq.

---

## 📁 Data Haqqında
* **Dataset:** `WA_Fn-UseC_-HR-Employee-Attrition.csv` (IBM HR Analytics)
* **Həcm:** 1470 sətir, 35 sütun
* **Təmizlik:** Buraxılmış dəyərlər (Nulls) və təkrar sətirlər (Duplicates) mövcud deyil (0).

---

## 🛠️ İstifadə Olunan Texnologiyalar
* **Python 3.x**
* **Pandas:** Datanın təmizlənməsi, qruplaşdırılması və transformasiyası.
* **Matplotlib & Seaborn:** Vizual grafiklərin və trendlərin qurulması.

---

## 📈 Əsas Analiz Nəticələri (Key Insights)

### 1. Ümumi KPI Göstəriciləri
* **Cəmi İşçi Sayı:** 1470 nəfər
* **Şirkəti Tərk Edənlər:** 237 nəfər
* **Ümumi Attrition Rate:** **16.12%**

| Status | İşçi Sayı | Hissə (%) | Orta Aylıq Gəlir ($) | Orta Şirkət Stajı (İl) | Orta İş Məmnuniyyəti (1-4) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Qalanlar (No)** | 1233 | 83.88% | $6,832.74 | 7.37 il | 2.78 |
| **Ayrılanlar (Yes)** | 237 | 16.12% | $4,787.09 | 5.13 il | 2.47 |

---

### 2. İş Stajına Görə Ayrılma Riski (Tenure Groups)
İşçilərin ilk 2 ili şirkət üçün ən kritik dövrdür:
* **0–2 il stajı olanlar:** Attrition Rate **29.82%** (Ən yüksək risk zonası)
* **3–5 il stajı olanlar:** Attrition Rate **13.82%**
* **6–10 il stajı olanlar:** Attrition Rate **12.28%**
* **11+ il stajı olanlar:** Attrition Rate **8.13%**

---

### 3. Gəlir Səviyyəsinə Görə Analiz (Income Quartiles)
Aşağı maaş alan işçilər arasında şirkəti tərk etmə ehtimalı kəskin dərəcədə yüksəkdir:
* **Q1 (Ən aşağı gəlir qrupu):** Attrition Rate **29.27%**
* **Q2:** Attrition Rate **14.21%**
* **Q3:** Attrition Rate **10.63%**
* **Q4 (Ən yüksək gəlir qrupu):** Attrition Rate **10.33%**

---

### 4. Maliyyə Təsiri (Cost of Attrition)
*(Hər ayrılan işçinin əvəzlənmə xərci 6 aylıq maaş olaraq götürülüb)*
* **Ayrılan işçi sayısı:** 237
* **İllik ümumi Attrition Xərci:** **$6,807,246.00**

---

## 💡 İdarəetmə Üçün Tövsiyələr (Recommendations)
1. **Onboarding və İlk 2 İl Strategiyası:** Yeni işə qəbul olunanların adaptasiya prosesi gücləndirilməli və ilk 2 ildə saxlanma (retention) proqramları tətbiq edilməlidir.
2. **Əməkhaqqı Və Ödəniş Balansı:** Q1 gəlir kvartilindəki ayrılma faizi (29.27%) çox yüksəkdir. Maaşların bazar standartlarına uyğunluğu yenidən qiymətləndirilməlidir.
3. **Məmnuniyyət Sorğuları:** İşdən ayrılanların iş məmnuniyyəti (2.47) aşağı olduğundan, davamlı HR sorğuları və geri bildirim mexanizmləri qurulmalıdır.

---

## 🚀 Quraşdırma və İcra

```bash
# Repository-ni klonlayın
git clone [https://github.com/istifadəçi-adınız/hr-attrition-analysis.git](https://github.com/istifadəçi-adınız/hr-attrition-analysis.git)

# Qovluğa keçin
cd hr-attrition-analysis

# Lazımi kitabxanaları quraşdırın
pip install pandas matplotlib seaborn notebook

# Jupyter Notebook-u başladın
jupyter notebook
