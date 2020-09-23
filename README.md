# NGINX-Document

- #### reverse proxy 

<p align="center" ><img width="650px" src="https://user-images.githubusercontent.com/15135199/93990294-2632e900-fdb5-11ea-9313-8ee570f41b40.png"/></p>


  รับ request จาก client ส่งต่อไปยัง server ปลายทางและส่ง response จาก server กลับไปยัง client

- #### load balancer 

<p align="center" ><img width="650px" src="https://user-images.githubusercontent.com/15135199/93993317-ccccb900-fdb8-11ea-97fc-84c7f5cefa91.png"/></p>

  แจกจ่าย request จาก client ที่เข้ามาไปยัง server หลายเครื่อง เพื่อแบ่งเบาภาระของ server ที่ทำงานแค่เครื่องเดียว


## ความสามารถของ NGINX

- ทำเป็น web server
- ทำเป็น proxy server
- ทำเป็น load balance 

## ข้อดีของ NGINX

- 1. เร็วที่สุดและดีที่สุดสำหรับการแสดงข้อมูลไฟล์แบบคงที่

- 2. รองรับ Load Balancing

- 3. รองรับและจัดการ  concurrent connections ได้มากกว่า Apache หลายเท่า
