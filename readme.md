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

### 380. Level 2 - Database Encryption

    mongoose-encryption
    install mongoose encryption: npm i mongoose-encryption
    Documentation:
        - Usage =>  https://www.npmjs.com/package/mongoose-encryption
        - Secret String Instead of Two Keys
        - Encrypt Only Certain Fields


        pada browser : lakukan register dan login, masukan email dan password
        - http://localhost:3000/register
        - http://localhost:3000/login

        jika berhasil akan diredirect kehalaman Secrets

        lihat pada database hasil register password ter-generate secara acak
