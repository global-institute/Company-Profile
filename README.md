
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

### Bagaimana cara menjalankannya :
- Gunakan Fork untuk untuk menyalin repository ini dengan meng klik pada link berikut [https://github.com/global-institute/Company-Profile.git](https://github.com/global-institute/Company-Profile/fork)
- Kemudian Clone repository yang sudah anda fork ke local pc anda
  - `$ git clone [url-git-anda]`
- Lalu ubah beberapa hal berikut :
  - Tambahkan identitas anda, pada file berikut : 
   - **Dockerfile** : `Sesuaikan instruksi : LABEL`
   - **Json** di folder **html/team/json** : `Tambahkan file [nama Anda].json dan isi dengan data diri Anda`
   - **index.html** di folder **team** : `Tambahkan path dari file .json yang sudah Anda buat di line : 118`
- Kemudian buat **Access Token** di dockerhub, untuk dihubungkan dengan **github action**
- Setelah **Access Token** dibuat, pergi ke setting repository github Anda, dan tambahkan secret yang berisi _dockerhub Access Token_
  - `Settings -> Secrets -> Actions -> New Repository Secret`
- Setelah itu buat file yang berlokasi di folder **.github/workflows/github-actions-.yml**
- Lalu ubah dan sesuaikan _tag_, _repository_, _secrets_ pada file **actions-workflow.yml** 
  - `sesuaikan nama username dockerhub dengan repository dockerhub anda masing-masing :`
  - `docker build . --file Dockerfile --tag (dockerhub_username)/company-profile:v1`
  - `docker login -u ${{secrets.[dockerhub_username]}} -p ${{secrets.[dockerhub_AccessToken]}} && docker push (dockerhub_username)/company-profile:v1`
- Jika semua persiapan sudah selesai, silahkan push ke repository masing-masing
  - `git add .`
  - `git commit -m "commit message"`
  - `git push origin main`
- Kemudian cek menu Action pada Github anda, pastikan tidak ada error
- Jika github action berhasil, cek dockerhub anda seharusnya ada image baru dengan nama **company-profile:v1**
- Coba jalankan docker image yang anda buat di local docker machine ataupun docker playground
  - `docker run -itd -p8080:80 (dockerhub_username)/company-profile:v1`
- Kemudian jalankan containers kalian di port 80:80 dengan cara klik `open in browser`
