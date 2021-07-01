
### พื้นฐาน Rate Limiting

- การตั่งค่า rate limit ใช้สองคำสั่งหลักได้แก่ limit_req_zone และ limit_req 
- limit_req_zone ใช้เพื่อการกำหนดค่า ส่วน limit_req ใช้เพื่อเปิดใช้งานใน context 
- คำสั่ง limit_req_zone ถูกกำหนด block ของ http มี 3 parameter

### สิ่งที่ต้องติดตั้ง

- siege  คือ regression test และ benchmark utility

##### ติดตั้ง siege

    apt-get install siege
    
##### ตรวจสอบการติดตั้ง     

    siege -V


### Reference

- https://www.nginx.com/blog/rate-limiting-nginx/
