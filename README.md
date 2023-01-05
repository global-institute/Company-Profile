
## Project UAS Pengantar Cloud Computing - PHOENIX SQUAD
- Ahmad Pausi (1121130019)
- Argin Fiorenza (1121130049)
- Muhammad Raihan (1121130051)
- Dimas Eurico (1121130041)
- Bayu Irfan Aditya (1121130089)
- Dhea Wida Kamilah (1121130154)

### Apa yang dibutuhkan :
- Akun github
- Akun dockerhub
- Text Editor (Visual Studio Code recommended)
- Doa Ibu

2.	Bagaimana cara menjalankannya :
•	Gunakan Fork untuk untuk menyalin repository global-institute/Company-Profile dengan meng klik pada link berikut https://github.com/global-institute/Company-Profile.git
 ![image](https://user-images.githubusercontent.com/104171054/210681050-26f7e555-763a-4f96-a114-448187a5c6ac.png)
 
•	Kemudian Clone repository yang sudah anda fork ke local pc anda
o	$ git clone [url-repositori-fork-anda]
 ![image](https://user-images.githubusercontent.com/104171054/210681031-272e86f2-a167-4c76-aaf3-de060d5ec0e1.png)
 
*pastikan Anda berada di direktori yang tepat ketika melakukan clone repositori

•	Setelah clone selesai dilakukan, silahkan ikuti instruksi di bawah untuk melakukan perubahan di beberapa file
 ![image](https://user-images.githubusercontent.com/104171054/210681013-ac16254c-6ea0-4f36-a23f-4834ef6f654c.png)
 
•	Tambahkan informasi identitas anda di beberapa file berikut :
o	Dockerfile : Silahkan isi sesuai instruksi pada LABEL (ubah kalimat change me)
![image](https://user-images.githubusercontent.com/104171054/210680999-bd62e46f-172d-4c44-9d72-ddbc06cf4799.png)

o	Json di folder html/team/json : Tambahkan file [nama Anda].json dan isi data diri Anda sesuai dengan format test.json
![image](https://user-images.githubusercontent.com/104171054/210680989-3cc94f2b-7f7c-4eba-aa4e-d67f062fbe0f.png)

o	index.html di folder team : Tambahkan path dari file .json yang sudah Anda buat di line : 118
![image](https://user-images.githubusercontent.com/104171054/210680975-ef49a927-19b1-486b-ae2b-4047c3430b5e.png)

•	Kemudian buat Access Token di dockerhub, untuk dihubungkan dengan github action
![image](https://user-images.githubusercontent.com/104171054/210680948-206862e1-4847-404e-9c9d-3ca7db8129b0.png)
![image](https://user-images.githubusercontent.com/104171054/210680959-7e5c0dac-c1a8-4f19-862c-cbf0133d145b.png)

*Token selesai di buat
•	Setelah Access Token dibuat, pergi ke setting repository github Anda, dan tambahkan secret yang berisi dockerhub Access Token
o	Settings -> Secrets -> Actions -> New Repository Secret
![image](https://user-images.githubusercontent.com/104171054/210680861-6b9247fd-9ec9-433a-8fe5-907d3d8ad228.png)
![image](https://user-images.githubusercontent.com/104171054/210680868-f01d96d8-eb92-43cd-897d-7eabd3e77a42.png)

•	Setelah itu buat file yang berlokasi di folder .github/workflows/actions-workflow-.yml
 ![image](https://user-images.githubusercontent.com/104171054/210680848-e6404281-e85c-4690-8393-6e502b8d8827.png)
 
•	Lalu ubah dan sesuaikan tag, repository, secrets pada file actions-workflow.yml
o	sesuaikan nama username dockerhub dengan repository dockerhub anda masing-masing :
o	docker build . --file Dockerfile --tag dockerhub-username/nama-image:tag
o	docker login -u ${{secrets.[ DOCKERHUB_USERNAME]}} -p ${{secrets.[DOCKERHUB_SECRET]}} && docker push dockerhub-username/nama-image:tag
![image](https://user-images.githubusercontent.com/104171054/210680833-22357261-4e68-4c85-a502-cd03976a5be7.png)

•	Jika semua persiapan sudah selesai, silahkan push ke repository masing-masing
o	git add .
o	git commit -m "commit message"
o	git push origin main
![image](https://user-images.githubusercontent.com/104171054/210680812-a0b31883-9270-4e8d-9e31-fa191b5b24dc.png)

•	Kemudian cek menu Action pada Github anda, pastikan tidak ada error
![image](https://user-images.githubusercontent.com/104171054/210680794-0a570002-071b-493f-93c4-c4df5b95c76e.png)

•	Jika github action berhasil, cek dockerhub anda seharusnya ada image baru dengan nama dummy-profile:v1
 ![image](https://user-images.githubusercontent.com/104171054/210680763-93dc8bf4-edbd-490c-a8ea-1e4efab688a7.png)
![image](https://user-images.githubusercontent.com/104171054/210680773-913b92aa-25c2-4046-bf5a-faed738cecb9.png) 

•	Coba jalankan docker image yang anda buat di local docker machine ataupun docker playground dengan cara :
o	docker run -itd -p8080:80 dockerhub-username/dummy-profile:v1
 ![image](https://user-images.githubusercontent.com/104171054/210680741-18508d72-2484-45b6-a648-f44f845636ff.png)
 
*images repositori kita
•	Kemudian jalankan containers kalian di port 80:80 dengan cara klik open in browser
![image](https://user-images.githubusercontent.com/104171054/210680718-06e6762f-322e-42c6-ab66-e0ffa84649c5.png)
 
o	Tampilan setelah berhasil di jalankan di browser
 ![image](https://user-images.githubusercontent.com/104171054/210680635-83b42c56-3f39-47b4-8206-4a6c789f6654.png)
![image](https://user-images.githubusercontent.com/104171054/210680659-d9cca3d3-8ae0-4d28-8002-36c51106cabd.png)
