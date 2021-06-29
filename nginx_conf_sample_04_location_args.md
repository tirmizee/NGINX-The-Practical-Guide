#### สร้าง Certificate โดยใช้ mkcert 

- https://github.com/FiloSottile/mkcert

##### ตรวจสอบ packet wget มีให้ติดตั้งหรือไม่

    apt-cache search wget

##### ติดตั้ง packet wget 

    apt-get install wget
    
##### ตรวจสอบ version การติดตั้ง wget

    apt-get -V

##### download mkcert โดยใช้ wget

    wget https://github.com/FiloSottile/mkcert/releases/download/v1.4.3/mkcert-v1.4.3-linux-amd64

##### ทำการ copy mkcert-v1.4.3-linux-amd64 ไปยัง /usr/local/bin/mkcert เพื่อให้สามารถเรียกใช้คำสั่ง mkcert ได้ทุกที่

    cp mkcert-v1.4.3-linux-amd64 /usr/local/bin/mkcert

##### ให้สิทธิ exercute คำสั่ง mkcert

    chmod +x /usr/local/bin/mkcert

##### สร้าง Certificate 

    mkcert localhost
