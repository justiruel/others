## Membuat token sendiri
- user login
<br/>-- SUKSES : generate token -->  save (token,current time) di table token
-- FAIL : message("token invalid")
- post/get/put/patch/delete API --> sertakan token di header, di sisi api "select * from token where token = xyz"
<br/>-- Token ada, cek datetime nya apakah valid atau tidak
--- VALID   : masuk ke proses API
--- TOKEN EXPIRED : message("token was expired")
<br/>-- token tidak eksis, message("invalid token")
