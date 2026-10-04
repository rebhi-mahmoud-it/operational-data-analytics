# operational-data-analytics
# 📊 Operational Data Integration & Analytics System

مشروع متكامل لمعالجة، دمج، وتحليل البيانات التشغيلية المتعددة المصادر، واستخراج مؤشرات الأداء الرئيسية (KPIs) لدعم اتخاذ القرار.

---

## 🚀 الميزات الرئيسية (Features)

- **دمج البيانات (Data Integration):** ربط سجلات البيانات المتفرقة باستخدام استعلامات SQL المتقدمة ودوال Excel مثل `XLOOKUP`.
- **تنظيف البيانات (Data Cleaning):** معالجة القيم المفقودة والمتضاربة لضمان دقة التقارير.
- **تحليل الأداء (Performance Analytics):** استخراج تقارير دورية ومؤشرات قياسية حول سير العمليات.
- **لوحة عرض البيانات (Dashboard Presentation):** تصميم تقارير بصرية وسهلة القراءة لمتخذي القرار.

---

## 🛠️ التقنيات المستخدمة (Tech Stack)

- **Databases:** SQL (PostgreSQL / MySQL)
- **Data Analysis & Processing:** Python (Pandas), Advanced Excel (XLOOKUP, Pivot Tables)
- **Reporting:** Power BI / Excel Dashboards
- **Concepts:** Data Modeling, Relational Databases, Aggregations & Joins

---

## 📋 نماذج الاستعلامات (Sample SQL Queries)

```sql
-- استعلام لدمج البيانات واستخراج مؤشرات الأداء
SELECT 
    d.driver_id,
    d.driver_name,
    COUNT(v.vehicle_id) AS total_assigned_vehicles,
    MAX(v.last_inspection_date) AS last_check
FROM drivers d
LEFT JOIN vehicle_assignments v ON d.driver_id = v.driver_id
GROUP BY d.driver_id, d.driver_name
HAVING COUNT(v.vehicle_id) > 0;
