
##### ทำการ update package เพื่อ download ข้อมูลแพ็คเกจทั้งหมด

    apt-get update

##### ทำการติดตั้ง nginx 

    apt-get install nginx

##### ตรวจสอบ version ของ nginx ที่ทำการติดตั้ง

    nginx -v

##### ทำการตรวจสอบว่ามี service ของ nginx หรือเปล่า

    service  --status-all | grep nginx

##### ทำการตรวจสอบสถานะ service nginx 

    service nginx status

##### ทำการ start service nginx

    service nginx start

##### ทำการทดสอบเรียกใช้งาน

    curl localhost
