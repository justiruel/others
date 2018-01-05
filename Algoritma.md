## Membuat token sendiri
- user login
<br/>-- SUKSES : generate token -->  save (token,current time) di table token
<br/>-- FAIL : message("token invalid")
- post/get/put/patch/delete API --> sertakan token di header, di sisi api "select * from token where token = xyz"
<br/>-- Token ada, cek datetime nya apakah valid atau tidak
<br/>&nbsp;&nbsp;--- VALID   : masuk ke proses API
<br/>&nbsp;&nbsp;--- TOKEN EXPIRED : message("token was expired")
<br/>-- token tidak eksis, message("invalid token")


soap
