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

### 381. Using Environment Varibles to Keep Secrets Safe

    Documentation: https://www.npmjs.com/package/dotenv
    install dotenv : npm i dotenv

    untuk menghilangkan beberapa document/file sewaktu hendak di push ke git/ akan di deploy:
        Documentation: https://github.com/github/gitignore/blob/main/Node.gitignore
        cara pengunaan tinggal copy lalu paste ke file .gitignore

        pada browser : lakukan  login, masukan email dan password

        - http://localhost:3000/login

        lihat pada terminal akan ada API_KEY

### 382. Level 3 - Hashing Passwords

    Documentation: https://www.npmjs.com/package/md5
    install md5 : npm i md5

        pada browser : lakukan register dan login, masukan email dan password
        - http://localhost:3000/register
        - http://localhost:3000/login

        jika berhasil akan diredirect kehalaman Secrets
        lihat pada terminal akan ada password yang sama dengan di database

### 383. Hacking Passwords 101

    untuk mengetahui kekuatan kemanan password anda secara online:
    http://password-checker.online-domain-tools.com/

### 384. Level 4 - Salting and Hashing Passwords with bcrypt

    Documentation:
        A Note on Rounds => - https://www.npmjs.com/package/bcrypt
                            - https://github.com/kelektiv/node.bcrypt.js/issues/www.npmjs.com/package/bcrypt
    instal bcrypt: npm i bcrypt

    ┌──────────────────────────────────────────────────────────────────────────────┐
    │ Untuk Register :                                                             │
    │     Technique 2 (auto-gen a salt and hash):                                  │
    │     bcrypt.hash(myPlaintextPassword, saltRounds, function(err, hash) {       │
    │         // Store hash in your password DB.                                   │
    │     });                                                                      │
    └──────────────────────────────────────────────────────────────────────────────┘
    lakukan register : http://localhost:3000/register

                        email : "user@bcrypthash.com
                        password : 123456

    ┌──────────────────────────────────────────────────────────────────────────────┐
    │ Untuk Login:                                                                 │
    │         To check a password:                                                 │
    │         // Load hash from your password DB.                                  │
    │         bcrypt.compare(myPlaintextPassword, hash, function(err, result) {    │
    │             // result == true                                                │
    │         });                                                                  │
    └──────────────────────────────────────────────────────────────────────────────┘
    lakukan login : http://localhost:3000/login

                        email : "user@bcrypthash.com
                        password : 123456

    jika login dan register berhasil akan diarahkan kehalaman secret

### 385. What are Cookies and Sessions?

### 386. Level - 5 Using Passport.js to Add Cookies and Sessions | Register

    install package:
    npm i passport passport-local passport-local-mongoose express-session

    Documentation:
            - https://www.npmjs.com/package/express-session
            - https://www.passportjs.org/docs/

            ┌──────────────────────────────────────────────────────────────────────────────┐
            │ https://www.npmjs.com/package/passport-local-mongoose                        │
            │                 Simplified Passport/Passport-Local Configuration :           │
            │                 const User = require('./models/user');                       │
            │                                                                              │
            │                 // CHANGE: USE "createStrategy" INSTEAD OF "authenticate"    │
            │                 passport.use(User.createStrategy());                         │
            │                                                                              │
            │                 passport.serializeUser(User.serializeUser());                │
            │                 passport.deserializeUser(User.deserializeUser());            │
            └──────────────────────────────────────────────────────────────────────────────┘

    pada browser lakukan Register : http://localhost:3000/register
        email : user@passportlocalmongoose.com
        password : 123456

    jika berhasil akan diarahkan kehalaman secrets, dan sudah termasuk dengan cookiesnya , jd kalo kita masih belom logout kita buka kembali tidak perlu login .

### 386. Level - 5 Using Passport.js to Add Cookies and Sessions | Login & Logout

    pada browser lakukan login : http://localhost:3000/login
        email : user@passportlocalmongoose.com
        password : 123456

    jika berhasil akan diarahkan kehalaman secrets, dan sudah termasuk dengan cookiesnya , jd kalo kita masih belom logout kita buka kembali tidak perlu login .
    namun ada kelemahan jika server di load ulang akan meminta login kembali.
    karna ini hanya basic dari passport passport-local passport-local-mongoose express-session, ada baiknya lebih di perdalam pembelajarannya pada documentasi setiap package!

    pada browser lakukan logout : http://localhost:3000/secrets
    pada halaman secrets lakukan logout . jika berhasil maka akan di redirect ke halaman home.
