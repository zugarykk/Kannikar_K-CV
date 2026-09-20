# 🎯 Instruction File — ใช้สั่งงาน Claude Code

> ไฟล์นี้คือ "คำสั่ง" (instruction/prompt) ที่ใช้สั่งงาน Claude Code
> **แยกออกจากไฟล์ input** (`input/cv_kannikar.md`) โดยตั้งใจ เพื่อให้ผู้เรียนเห็นชัดเจนว่า
> "ข้อมูลดิบ" (input) กับ "คำสั่งงาน" (instruction) เป็นคนละส่วนกัน — เป็นแนวคิดสำคัญ
> ของการทำงานกับ AI agent อย่างเป็นระบบ (separation of data & instruction)

---

## 🗣️ Prompt หลัก (Copy ไปวางใน Claude Code)

```
อ่านไฟล์ input/cv_kannikar.md ซึ่งเป็นข้อมูล Resume/CV ของฉัน

ช่วยสร้างเว็บไซต์ Personal Portfolio แบบหน้าเดียว (single page) ด้วย HTML + CSS + JavaScript
ล้วน ๆ (ไม่ใช้ framework เช่น React/Vue) ตามรายละเอียดต่อไปนี้:

1. โครงสร้างไฟล์:
   - index.html
   - style.css
   - script.js (ใช้สำหรับ smooth scroll และ active menu highlight)

2. เนื้อหาในเว็บไซต์ ให้ดึงข้อมูลจาก input/cv_kannikar.md มาจัดเป็น section ดังนี้:
   - Hero section: ชื่อ, ตำแหน่ง, ช่องทางติดต่อ
   - About / Professional Summary
   - Core Competencies (แสดงเป็น skill badges หรือ progress bar)
   - Experience Timeline (Professional Experience + Research Experience)
   - Education (แสดงเป็น timeline หรือ card)
   - Publications
   - Select Training Clients (แสดงเป็น logo grid หรือ tag list)
   - Footer พร้อมช่องทางติดต่อ

3. ดีไซน์:
   - โทนสีหลัก: น้ำเงินเข้ม (#0B3D91) ตัดกับสีขาว และสีเหลืองทอง (#E0A800) เป็นสีเน้น
   - Responsive รองรับมือถือ/แท็บเล็ต/จอคอมพิวเตอร์ (ใช้ CSS Grid/Flexbox)
   - มี Navigation bar แบบ sticky พร้อมเมนูเลื่อนไปยังแต่ละ section (smooth scroll)
   - ใช้ Google Fonts (เช่น "Inter" หรือ "Poppins")
   - มี hover effect และ animation เบา ๆ (fade-in เมื่อ scroll ผ่าน section)

4. คุณภาพของโค้ด:
   - เขียน HTML แบบ semantic (ใช้ <section>, <header>, <nav>, <footer>)
   - คอมเมนต์ในโค้ดเป็นภาษาอังกฤษสั้น ๆ อธิบายแต่ละส่วน
   - ไม่ต้องใช้ external build tool ใด ๆ เปิดไฟล์ index.html ผ่าน browser ได้ทันที

หลังจากสร้างไฟล์เสร็จ ให้สรุปสั้น ๆ ว่าไฟล์ไหนทำหน้าที่อะไร และวิธีเปิดดูผลลัพธ์
```

---

## 🔁 Prompt เสริม (ใช้ถ้าต้องการปรับปรุงต่อ)

### ปรับสีหรือธีม
```
ช่วยปรับธีมสีของเว็บไซต์เป็นโทน Dark Mode พร้อมปุ่มสลับ Light/Dark ที่มุมขวาบน
```

### เพิ่มฟีเจอร์ Print/PDF
```
ช่วยเพิ่ม CSS สำหรับ @media print ให้เว็บไซต์นี้พิมพ์ออกมาเป็น Resume PDF ที่สวยงาม
ตัด Navigation bar และ background สีออกเวลาพิมพ์
```

### ตรวจสอบ Responsive
```
ช่วยตรวจสอบว่าเว็บไซต์นี้แสดงผลถูกต้องบนหน้าจอขนาด 375px (มือถือ) และแก้ไขจุดที่ overflow หรือ
ล้นจอ
```

---

## ⚠️ หลักการสำคัญที่ผู้สอนควรเน้นกับผู้เรียน

| หลักการ | คำอธิบาย |
|---|---|
| **Input ≠ Instruction** | `input/` คือข้อมูลดิบที่ไม่เปลี่ยนบ่อย ส่วน instruction คือคำสั่งที่ปรับเปลี่ยนได้ตามงาน |
| **Prompt ที่ดีต้องระบุ output ชัดเจน** | บอกโครงสร้างไฟล์ โทนสี และพฤติกรรมที่ต้องการ ไม่ใช่แค่ "ทำเว็บให้หน่อย" |
| **ทำเป็นขั้นบันได (incremental)** | สร้างโครงหลักก่อน แล้วค่อยสั่งปรับปรุงทีละจุด (สี, responsive, animation) |
| **ใช้ Plan Mode ก่อนลงมือ** | ให้ Claude Code วางแผนโครงสร้างไฟล์ก่อน แล้วจึงสั่งให้ลงมือเขียนโค้ดจริง |
