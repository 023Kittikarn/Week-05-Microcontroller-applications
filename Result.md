คำถามทบทวน
Docker Commands: คำสั่ง docker-compose up -d และ docker-compose exec esp32-dev bash ทำอะไร?

ESP-IDF Tools: เครื่องมือไหนจาก Lab4 ที่จะใช้ในการ build โปรแกรม ESP32?

New Tools: เครื่องมือใหม่ที่ติดตั้ง (tree, htop) ใช้ทำอะไร?

Architecture Focus: การศึกษา ESP32 architecture แตกต่างจากการทำ arithmetic ใน Lab4 อย่างไร?

ตอบคำถามทบทวน

Docker Commands
  -docker-compose up -d
เป็นคำสั่งสำหรับ เริ่มต้น container ทั้งหมด ที่กำหนดไว้ในไฟล์ docker-compose.yml
ออปชัน -d หมายถึง “detached mode” คือให้รันเบื้องหลังโดยไม่แสดง log บนหน้าจอ
สั่งให้ Docker สร้างและรัน environment ที่ต้องใช้ (เช่น container ของ ESP-IDF, compiler, etc.) แบบ background
  -docker-compose exec esp32-dev bash
เป็นคำสั่งสำหรับ เข้าไปภายใน container ที่ชื่อว่า esp32-dev
bash หมายถึงเปิด shell ภายใน container เพื่อพิมพ์คำสั่งต่อได้
ใช้เข้าไป “ทำงานข้างใน container” เช่น build โค้ด, ตรวจไฟล์, run คำสั่ง ESP-IDF เป็นต้น

ESP-IDF Tools (จาก Lab4)
เครื่องมือหลักที่ใช้ในการ build โปรแกรม ESP32 คือ
  -idf.py
เป็น command-line tool ของ ESP-IDF
ใช้คำสั่งเช่น
  idf.py build → สร้าง (compile + link) โปรแกรม
  idf.py flash → อัปโหลดโปรแกรมลงบอร์ด
  
New Tools
  -tree
ใช้สำหรับแสดง โครงสร้างของโฟลเดอร์/ไฟล์ ในรูปแบบต้นไม้
  -htop
เป็นโปรแกรมแบบ interactive ที่ใช้ดู การทำงานของระบบ (System Monitor)
แสดง CPU, RAM, Process ต่างๆ แบบ real-time
ใช้ตรวจสอบว่า container หรือระบบกำลังใช้ทรัพยากรมากน้อยแค่ไหน
idf.py monitor → ดู serial output
เครื่องมือหลักที่ใช้ build และจัดการโครงการ ESP32

การศึกษา Architecture คือ เข้าใจวงในของสมอง ESP32
ส่วน Arithmetic Lab4 คือ ทดลองใช้สมองนั้นคำนวณและทำงานจริง
