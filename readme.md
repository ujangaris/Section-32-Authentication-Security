## Section-32-Authentication-Security

### 377. Getting Set Up | install module

    npm init -y
    npm i express ejs body-parser

### 377. Getting Set Up | Server , render view : home, login , register

    jalankan server : nodemon app.js
    buka pada browser:
                        - http://localhost:3000/
                        - http://localhost:3000/login
                        - http://localhost:3000/register

### 378. Level 1 - Register Users with Username and Password | Register

    install mongoose: npm i mongoose
    Register:
        pada browser : http://localhost:3000/register
        lakukan register, masukan email dan password
        jika berhasil akan diredirect kehalaman Secrets

### 378. Level 1 - Register Users with Username and Password | Login

    Login:
        pada browser : http://localhost:3000/login
        lakukan login, masukan email dan password
        jika berhasil akan diredirect kehalaman Secrets

        note: password masih belum aman!
