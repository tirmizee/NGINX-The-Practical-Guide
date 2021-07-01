
### พื้นฐาน Rate Limiting

- การตั่งค่า rate limit ใช้สองคำสั่งหลักได้แก่ limit_req_zone และ limit_req 

### สิ่งที่ต้องติดตั้ง

- siege  คือ regression test และ benchmark utility

##### ติดตั้ง siege

    apt-get install siege
    
##### ตรวจสอบการติดตั้ง     

    siege -V


### Reference

- https://www.nginx.com/blog/rate-limiting-nginx/
