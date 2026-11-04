# 🛣️ Road to Data Engineer

คอร์สเรียน Data Engineer ตั้งแต่พื้นฐานจนพร้อมทำงานจริง
อาจารย์ประจำคอร์ส: Claude · รูปแบบ: เรียนทีละบท → ลงมือทำ → ส่งงาน → รีวิว → ไปบทถัดไป

---

## 🎯 เป้าหมายของคอร์ส

จบคอร์สแล้วคุณจะ:

1. เขียน **SQL** และ **Python** สำหรับงานข้อมูลได้คล่อง
2. ออกแบบ **Data Model / Data Warehouse** ได้ (Star schema, SCD)
3. สร้าง **Data Pipeline** แบบ ETL/ELT ที่รันอัตโนมัติ มี test มี monitoring
4. ใช้เครื่องมือที่บริษัทใช้จริง: **Docker, Airflow, dbt, Spark, Kafka, Cloud (GCP/AWS)**
5. มี **Portfolio 3 โปรเจกต์** บน GitHub ไว้ยื่นสมัครงาน + พร้อมสัมภาษณ์

ระยะเวลาโดยประมาณ: **6–9 เดือน** (เรียนวันละ 1–2 ชม. / สัปดาห์ละ ~10 ชม.)

---

## 🧭 ภาพรวม: Data Engineer ทำอะไร?

```
 แหล่งข้อมูล            Ingestion        Storage            Transform         ผู้ใช้ข้อมูล
┌──────────────┐     ┌──────────┐    ┌──────────────┐   ┌───────────┐   ┌──────────────┐
│ App DB (OLTP)│ ──▶ │ Batch    │──▶ │ Data Lake    │──▶│ dbt / SQL │──▶│ Dashboard/BI │
│ API          │     │ Stream   │    │ (S3/GCS)     │   │ Spark     │   │ Data Science │
│ Files / Logs │     │ (Kafka)  │    │ Warehouse    │   │           │   │ ML / AI      │
└──────────────┘     └──────────┘    └──────────────┘   └───────────┘   └──────────────┘
                     ╰──────────── Orchestration (Airflow) + Data Quality + Monitoring ───────╯
```

DE = คนสร้าง "ท่อส่งข้อมูล" ให้ข้อมูลไหลจากต้นทาง → ปลายทาง **ถูกต้อง ครบ ตรงเวลา และเชื่อถือได้**

---

## 📚 หลักสูตร (10 Phase)

| Phase | หัวข้อ | สิ่งที่ได้ | เวลา |
|---|---|---|---|
| **0** | ตั้งค่าเครื่อง & Mindset | Terminal, Git/GitHub, VS Code, Python venv | 1 สัปดาห์ |
| **1** | SQL ตั้งแต่ศูนย์ → ขั้นสูง | SELECT, JOIN, GROUP BY, Subquery, CTE, **Window Functions**, Query tuning | 4 สัปดาห์ |
| **2** | Python สำหรับ Data | พื้นฐาน, ไฟล์ CSV/JSON, API (requests), **pandas**, OOP เบื้องต้น, error handling, logging, pytest | 4 สัปดาห์ |
| **3** | Database & Data Modeling | PostgreSQL, Normalization, OLTP vs OLAP, **Kimball Star Schema**, SCD Type 1/2, Index | 3 สัปดาห์ |
| **4** | Linux, Docker & ETL ตัวแรก | Bash, Docker, docker-compose → **🏗️ Project 1: ETL ดึง API → Postgres** | 3 สัปดาห์ |
| **5** | Data Warehouse & ELT | Columnar storage, Parquet, DuckDB, BigQuery, **dbt** (models, tests, docs) | 4 สัปดาห์ |
| **6** | Orchestration | **Apache Airflow** (DAG, Operator, scheduling, backfill, idempotency) | 3 สัปดาห์ |
| **7** | Big Data & Lakehouse | **Spark / PySpark**, partitioning, Delta Lake / Iceberg, Medallion (Bronze/Silver/Gold) → **🏗️ Project 2** | 4 สัปดาห์ |
| **8** | Streaming | **Kafka**, producer/consumer, CDC (Debezium), Spark Structured Streaming | 3 สัปดาห์ |
| **9** | Cloud & Production | GCP หรือ AWS, IAM, Terraform เบื้องต้น, CI/CD (GitHub Actions), Data Quality, Observability, ต้นทุน | 4 สัปดาห์ |
| **10** | Capstone & หางาน | **🏗️ Project 3 (End-to-end)**, Resume, Portfolio, ฝึกสัมภาษณ์ SQL/Python/System Design | 4 สัปดาห์ |

> 💡 ลำดับนี้ตั้งใจให้ **SQL มาก่อน** เพราะเป็นทักษะที่ใช้บ่อยที่สุดในงานจริงและถูกถามในสัมภาษณ์ทุกที่

---

## 🔁 วิธีเรียนกับอาจารย์

1. พิมพ์ **"เริ่มบทถัดไป"** → อาจารย์จะสร้างไฟล์บทเรียนใน `lessons/`
2. อ่านเนื้อหา + **พิมพ์โค้ดเอง** (ห้าม copy-paste ทั้งก้อน — มือต้องจำ)
3. ทำ **แบบฝึกหัด** ลงในโฟลเดอร์ `exercises/`
4. พิมพ์ **"ตรวจงานบท X"** → อาจารย์จะรีวิวโค้ด ให้คะแนน และบอกจุดที่ต้องแก้
5. ติดตรงไหน ถามได้ตลอด — **ไม่มีคำถามไหนโง่**
6. ความคืบหน้าทั้งหมดบันทึกใน [PROGRESS.md](PROGRESS.md)

คำสั่งที่ใช้ได้กับอาจารย์:
- `เริ่มบทถัดไป` · `ตรวจงานบท X` · `อธิบาย ___ ใหม่แบบง่ายกว่านี้` · `ขอโจทย์เพิ่ม` · `ทดสอบ quiz Phase X` · `จำลองสัมภาษณ์`

---

## 📁 โครงสร้างโฟลเดอร์

```
road-to-data-engineer/
├── README.md          ← แผนคอร์ส (ไฟล์นี้)
├── PROGRESS.md        ← ตัวติดตามความคืบหน้า + บันทึกการเรียน
├── lessons/           ← เนื้อหาบทเรียน
├── exercises/         ← งานที่คุณทำ (อาจารย์จะตรวจตรงนี้)
└── projects/          ← โปรเจกต์ Portfolio
```

---

## 🧰 เครื่องมือในเครื่องคุณ (เช็กแล้ว)

| เครื่องมือ | สถานะ |
|---|---|
| Python 3.13 | ✅ |
| Git 2.51 | ✅ |
| Docker 29 | ✅ |
| VS Code | ⬜ ตรวจในบทที่ 0.1 |
| บัญชี GitHub | ⬜ ตรวจในบทที่ 0.1 |
