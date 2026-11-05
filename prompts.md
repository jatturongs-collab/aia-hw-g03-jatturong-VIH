# บันทึกขั้นตอน (process log)

> **หมายเหตุ:** งานทั้งหมดทำเสร็จก่อนสร้าง repo นี้ (ก.ย. 2569/2026) entry ด้านล่างจึง **เขียนย้อนหลัง** วันที่และเวลาอ้างอิงจาก timestamp ของไฟล์ผลลัพธ์ ไม่ใช่เวลาที่พิมพ์ prompt ช่องที่ไม่มีบันทึกจริงเว้นไว้ให้ระบุว่า "ไม่ได้บันทึก" ไม่เดาเพิ่ม

---

## รอบ 1 · 24 ก.ย. 2026 (ราว 22:14–22:36 ตาม timestamp ไฟล์)

- **ทำอะไร:** ถอดวิธีคิดของนักลงทุนที่ติดตาม VIH ทุกไตรมาส (คุณ Pop) ออกมาเป็น skill แล้วสร้าง finance sheet v1 (Excel + รายงาน md) ของ VIH
- **เครื่องมือ / model:** Antigravity (AGY) สำหรับสร้าง skill · model ไม่ได้บันทึก
- **Prompt ที่ใช้:** (ย่อจาก `0_readme/readme_VIH.txt`)

```text
ช่วยทำ Reverse-Engineering ดังนี้:
1. วิเคราะห์และสกัด (Extract) ตรรกะการลงทุน (Investment Logic), วิธีการคิด (Mental Models), กฎเกณฑ์การประเมิน (Valuation Rules), สัญญาณความเสี่ยง (Red Flags) และประเด็นตามติด (Monitoring Checklist) ออกมาให้เป็นหลักเกณฑ์เชิงระบบ (Systematic Rules)
2. สร้าง Skill ใหม่สำหรับ Antigravity ภายใต้โฟลเดอร์ .agents/skills/investor-mindset-analyzer/
3. ภายในโฟลเดอร์ ให้สร้างไฟล์ SKILL.md ...
4. ในเนื้อหา SKILL.md ให้ระบุ: Workflow & Steps, Checklist หัวข้อชี้วัด (Bull Points, Bear Points, Fatal Flaws, Catalysts), เกณฑ์การตัดสินใจ (Decision Framework) และ Actionable Output Template
5. หากมีสูตรคำนวณเฉพาะตัว ให้เขียน Python helper script ไว้ใน scripts/
```

- **ผลที่ได้:** ได้ skill ตั้งต้นและ `finance_sheet_v1` ยังไม่มีรายงานเชิงลึก
- **ตัดสินใจอะไร และเพราะอะไร:** ไม่ได้บันทึกเหตุผล
- **ขั้นต่อไป:** ทำ snapshot รายไตรมาสจาก finance sheet

---

## รอบ 2 · 24–26 ก.ย. 2026 (v9 เมื่อ 24 ก.ย. 23:32, v20 ล่าสุด 26 ก.ย. 23:50 ตาม timestamp ไฟล์)

- **ทำอะไร:** สร้างและปรับ Snapshot Q2/2569 หลายรอบจนถึง v20 (ย้อนหลัง 4 ไตรมาส คาดการณ์ 2–4 ไตรมาส) จากข้อมูล 14 ไตรมาส
- **เครื่องมือ / model:** Claude · skill `stock-snapshot` · model ไม่ได้บันทึก
- **Prompt ที่ใช้:** ไม่ได้บันทึก prompt ดิบ (สั่งผ่าน skill)
- **ผลที่ได้:** `output/VIH_Snapshot_Report_Q2_2569-v20.{md,html}` ตรวจงบดุลสมดุลและโครงสร้างรายได้ตรงกัน
- **ตัดสินใจอะไร และเพราะอะไร:** ไม่ได้บันทึกเหตุผล
- **ขั้นต่อไป:** ขยายเป็นรายงานเชิงลึก 5–6 ปี

---

## รอบ 3 · 26 ก.ย. 2026 (ราว 21:19 ตาม timestamp ไฟล์)

- **ทำอะไร:** ปรับ Deep Dive หลายรอบ (v1 → v9) ได้รายงาน 9 หัวข้อ ปิดที่ `VIH_DeepDive_Report_2569-v9`
- **เครื่องมือ / model:** Claude · skill `thai-hospital-deepdive` · model ไม่ได้บันทึก
- **Prompt ที่ใช้:** ไม่ได้บันทึก prompt ดิบ (สั่งผ่าน skill)
- **ผลที่ได้:** `output/VIH_DeepDive_Report_2569-v9.{md,html}` มีตาราง 5 ปี, อัตราครองเตียงรายโรงพยาบาล, moat, guideline vs execution, scorecard ยังมีตัวเลขผิดปกติบางช่อง (ดู `PROJECT_MEMORY.md`)
- **ตัดสินใจอะไร และเพราะอะไร:** เก็บตัวเลขนอกเอกสารทางการไว้แยกในหัวข้อ 9 และใส่สีแดง เพื่อให้เห็นว่าอะไรยืนยันไม่ได้ (ตามกติกา "ทุกตัวเลขต้องมี source")
- **ขั้นต่อไป:** อัปเดตโมเดลการเงินให้ตรงกับรายงาน

---

## รอบ 4 · 29 ก.ย. – 5 พ.ย. 2026 (v9 เมื่อ 29 ก.ย. 00:47, v20 ล่าสุด 5 พ.ย. 10:58 ตาม timestamp ไฟล์)

- **ทำอะไร:** สร้างและปรับโมเดลการเงินหลายรอบจนถึง v20 (Excel + md) เป็นฐานตัวเลขของรายงาน
- **เครื่องมือ / model:** Claude · skill `thai-hospital-finance-sheet` (ไม่ยืนยัน) · model ไม่ได้บันทึก
- **Prompt ที่ใช้:** ไม่ได้บันทึก prompt ดิบ (สั่งผ่าน skill)
- **ผลที่ได้:** `output/VIH_finance_model_v20.{xlsx,md}`
- **ตัดสินใจอะไร และเพราะอะไร:** ไม่ได้บันทึกเหตุผล
- **ขั้นต่อไป:** แก้ตัวเลขผิดปกติใน deep dive และเพิ่มช่วงมูลค่า downside/upside (ค้างอยู่ใน `help.md`)

---

## รอบ 5 · 5 พ.ย. 2026

- **ทำอะไร:** จัดงานเดิมเข้าโครง template: กรอก README/spec, คัดลอก v9 ของ deepdive, snapshot และโมเดลการเงินเข้า `output/`, เขียน log ย้อนหลัง, PROJECT_MEMORY, help
- **เครื่องมือ / model:** Claude Code (Claude Sonnet 5.5) · Plan mode
- **Prompt ที่ใช้:**

```text
ผมมี home work ที่ต้องส่ง มี format ตาม template github.com/Bank-The-Great/aia-hw-template
แต่ผมทำงานเสร็จแล้ว มี skill มี report ... ทำอย่างไรที่ผมจะทำงานใหม่อีกรอบ ตาม template ข้างบน
```

และ `ignor deadline, here is repo url that you can push` + ลิงก์ repo นี้

- **ผลที่ได้:** repo ครบตามโครง template ตรวจพบตัวเลขผิดปกติใน deepdive v9 ระหว่างจัดงาน (บันทึกใน `PROJECT_MEMORY.md` และ `help.md`) ยังไม่ได้แก้
- **ตัดสินใจอะไร และเพราะอะไร:** ไม่วิเคราะห์ใหม่ แต่ย้ายงานเดิมเข้า template เพราะเนื้องานเสร็จแล้ว และบันทึก log ย้อนหลังโดยระบุชัดว่าย้อนหลัง · ใส่ xlsx ตามที่ผู้เรียนยืนยัน (ไม่มีข้อมูลดิบ SETSMART) · ไม่คัดลอก `paper/`, `PDF/`, `set/`, `filing/`
- **ขั้นต่อไป:** แก้ 3 ข้อใน `help.md`

---

## รอบ 6 · 5 พ.ย. 2026

- **ทำอะไร:** เปลี่ยนไฟล์ snapshot และโมเดลการเงินใน `output/` จาก v9 เป็นเวอร์ชันล่าสุด v20 (deepdive v9 เป็นเวอร์ชันล่าสุดอยู่แล้ว) และแก้ชื่อไฟล์ที่อ้างใน README, spec, prompts
- **เครื่องมือ / model:** Claude Code (Claude Sonnet 5.5)
- **Prompt ที่ใช้:**

```text
why you upload v9 why not upload the last version ?
```

- **ผลที่ได้:** ไฟล์ใน repo ตรงกับ master ล่าสุด
- **ตัดสินใจอะไร และเพราะอะไร:** รอบ 5 เลือก v9 เพราะดูจากท้ายรายการที่เรียงตามชื่อ ไม่ได้เรียงตามเวลาแก้ไข จึงพลาด v10–v20 · เรื่อง ROIC, Payout, YoY ผู้เรียนสั่งให้ข้าม จึงไม่ได้ตรวจว่า v20 แก้แล้วหรือยัง
- **ขั้นต่อไป:** ไม่มี
