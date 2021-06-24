
#### nginx เก็บ configuration file ไว้ที่ /etc/nginx/ ไฟล์แรกที่ nginx อ่านเมื่อ start

- /etc/nginx/nginx.conf
- /usr/local/etc/nginx/nginx.conf  
- /usr/local/nginx/conf/nginx.conf  

#### configuration file มีเนื้อหา 2 ส่วน

- Context
- Directive

#### Directive

ตัวเลือกการกำหนดค่าใน Nginx เรียกว่า directives. directive ประกอบไปด้วย name และ values และต้องลงท้ายด้วยเครื่องหมาย ; เช่น gzip on;  

มิฉะนั้น Nginx จะไม่สามารถโหลดการกำหนดค่าและสร้างข้อผิดพลาดได้


#### Context

เมื่อเปิด configuration file จะสั่งเกตเห็น { ... } พื้นที่ที่เป็นวงเล็บนี้เรียกว่า context. เพื่อแยกรายละเอียดการกำหนดค่าตาม mudule ต่างๆ

    worker_processes 2; # directive in the global context  
    http {              # http context  
        gzip on;        # directive in http context  

      server {          # server context  
        listen 80;      # directive in server context  
      }  
    }  
