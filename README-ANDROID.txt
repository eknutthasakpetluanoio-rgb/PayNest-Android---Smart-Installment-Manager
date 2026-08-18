PayNest Android / Google Play build
===================================

ฐานเว็บ:
https://eknutthasakpetluanoio-rgb.github.io/PayNest-v1/

วิธีนี้ใช้ Trusted Web Activity (TWA) ไม่ใช่ WebView ธรรมดา เพื่อให้ PayNest ใช้ PWA ตัวเดียวกับเว็บจริง และเปิดแบบเต็มหน้าจอเมื่อ Digital Asset Links ผ่านการยืนยัน

ค่าหลัก:
- package: com.paynest.smartinstallment
- versionName: 1.0.0
- versionCode: 1
- minSdk: 26
- targetSdk: 36
- compileSdk: 36
- Android Gradle Plugin: 9.0.1
- Gradle: 9.1.x
- Android Browser Helper: 2.7.2

สิ่งที่ยังต้องทำก่อน Publish:
1. เปิดโปรเจกต์นี้ใน Android Studio รุ่นปัจจุบัน
2. ให้ Android Studio ดาวน์โหลด Gradle 9.1 และ Android SDK 36
3. สร้าง/ใช้ upload key ของโปรเจกต์
4. Build AAB แบบ Release
5. สร้างแอปใน Google Play Console โดยใช้ package com.paynest.smartinstallment
6. หลัง Google Play แสดง SHA-256 ของ Play App Signing certificate ให้นำค่านั้นไปแทนที่
   REPLACE_WITH_PLAY_APP_SIGNING_CERTIFICATE_SHA256
   ใน site/.well-known/assetlinks.json
7. ต้องเผยแพร่ไฟล์ assetlinks.json ที่ URL นี้ (โดเมนระดับ origin):
   https://eknutthasakpetluanoio-rgb.github.io/.well-known/assetlinks.json
   ไม่ใช่ใต้ /PayNest-v1/
8. ทดสอบลิงก์และ TWA จากอุปกรณ์จริง ก่อนส่ง Production

หมายเหตุสำคัญ:
- ห้ามเปลี่ยน package หลังสร้างแอปบน Play Console
- SHA-256 ที่ใช้สำหรับ production ต้องเป็นของ Play App Signing certificate
- ถ้า Digital Asset Links ยังไม่ผ่าน แอปจะ fallback ไป Custom Tab แทนการเปิด TWA แบบเต็มหน้าจอ
- ตัวเว็บ PayNest เดิมยังคงเป็น source of truth ไม่มีการรวมเวอร์ชันเก่าเข้ามา
