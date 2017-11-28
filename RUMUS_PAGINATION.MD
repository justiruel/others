Inti dari pagination adalah menentukan limit dan offset suatu query select <br /> 
```
select * from tableX limit [offset],[limit]
select * from tableX limit 0,6 --> [jangan ditampilkan 0 record dari depan (berarti tampil semua)], [tampilkan 6 record setelahnya]
```
dengan kata lain query diatas akan menampilkan 6 record dari atas/awal record (0 disebut offset, 6 disebut limit)

RUMUS PENCARIAN OFFSET:
```
offset = (page - 1) * limit
```

contoh : <br/>
1. Menampilkan halaman 1 dengan limit perhalaman 5
```
offset = (1-1) * 5 = 0
select * from tableX limit 0,5 --> [jangan ditampilkan 0 record dari depan (berarti tampil semua)], [tampilkan 5 record setelahnya]
```
2. Menampilkan halaman 2 dengan limit perhalaman 5
```
offset = (2-1) * 5 = 5
select * from tableX limit 5,5 --> [jangan ditampilkan 5 record dari depan], [tampilkan 5 record setelahnya]
```
3. Menampilkan halaman 3 dengan limit perhalaman 5
```
offset = (3-1) * 5 = 10
select * from tableX limit 10,5 --> [jangan ditampilkan 10 record dari depan], [tampilkan 5 record setelahnya]
```


