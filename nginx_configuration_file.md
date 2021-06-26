
#### configuration file มีเนื้อหา 2 ส่วน

- Context
- Directive

#### Directive

ตัวเลือกการกำหนดค่าใน Nginx เรียกว่า directives. directive ประกอบไปด้วย name และ values และต้องลงท้ายด้วยเครื่องหมาย ; เช่น gzip on;  

มิฉะนั้น Nginx จะไม่สามารถโหลดการกำหนดค่าและสร้างข้อผิดพลาดได้


#### Context

เมื่อเปิด configuration file จะสั่งเกตเห็น { ... } พื้นที่ที่เป็นวงเล็บนี้เรียกว่า context. เพื่อแยกรายละเอียดการกำหนดค่าตามขอบเขตต่างๆ

```sql

    worker_processes 2; # directive ใน main or global context  
    http {              # http context  
        gzip on;        # directive ใน http context  

      server {          # server context  
        listen 80;      # directive ใน server context  
      }  
    }  

```

main or global context เป็นบริบทเดียวที่ไม่มีอยู่ภายในบล็อกของบริบทอื่น

#### Main or Global Context

```sql

    # main context อยู่นอกบริบทอื่นใดๆ

    . . .

    context {

        . . .

    }

```

#### Events Context
#### HTTP Context
#### Server Context
#### Location Context
#### Upstream Context
#### Mail Context
#### Limit_except Context
#### Other Contexts
