# Cracking Windows Password

Windows sistemangizni parolini unitib qoydingizmi yoki parollangan windows sistemani paroldan ochmoqchi bolsangiz bu maqola sizga yozdam beradi :)

Men buni Windows Regedit yordamida amalga oshiraman. Ushbu jarayonni **Windows 7, Windows 8, Windows 8.1 va Windows 10**da muvaffaqiyatli sinovdan o'tkazdim **windows 11**da ham ishlashiga ishonaman.

Quyida ko'rsatilganlarni qadamma qadam bajaring

### 1 - Windows'ni obrazini tayyorlash

>Windows (iso) falyni fleskaga **Rufus**, **PowerISO** yoki istalgan soft yordamida o'rnatishga tayyor qilib yuklang. 
>Bu fleshkani kompyuteringizga ulan va _reboot(перезагружать)_ qiling, kompyuter yonish jarayonida Boot Menu ga oting, 
>Boot Menu ga o'tish uchun odatda **F2, F10, F12** Tugmalaridan foydalanasiz
 
 
### 2 - Regedit-ni oching

>Media-dan yuklangandan so'ng, Windows Setup oynasi ochiladi. Bu orqali davom etish o'rniga 
>**Shift + F10** tugmalarini bosib, CMD(Command Prompt window) oynasini ochingx-special/nautilus-clipboard
>
>![2](https://user-images.githubusercontent.com/61009662/125900059-dcffbb5e-1ff3-46a6-b4bf-cc95ce068be2.png)


>Yuqorida ochilgan CMD oynasiga `Regedit` yozing va *Enter* tugmasini bosing, shunda *Registry Editor* muharriri ochiladi
>
>![2 1](https://user-images.githubusercontent.com/61009662/125900500-a897aedc-ed09-400c-8f00-757ee5c47153.png)


### 3 – *Registry Editor* muharririga o'zgartirishlar kiritish

>**HKEY_LOCAL_MACHINE** -ni bosing va yuqoridagi paneldan *Fayl* -> *Load Hive* ga o'ting
>
>![3](https://user-images.githubusercontent.com/61009662/125901061-5327a2a4-b742-48e3-97c2-3f618dd09a93.png)
>
>![3 1](https://user-images.githubusercontent.com/61009662/125901120-c74a595f-0ee8-4b5d-8f78-88a94aa55732.png)


>**C:\Windows\System32\config** direktoriyasini ichidan **SYSTEM** ni tanlang
>
>![3 2](https://user-images.githubusercontent.com/61009662/125901147-f3fe0533-242a-44ec-86db-8a18127b13bb.png)


>Kalit ism so'ralganda **temp**ni kiriting va *OK* tugmasini bosing
>
>![3 3](https://user-images.githubusercontent.com/61009662/125901558-917a8ac3-179e-47e5-8f17-2aa607b5b26b.png)




>Chap panelda **HKEY_LOCAL_MACHINE**-ni kengaytiring va keyin **temp**ni kengaytiring. Keyin uni belgilash uchun **Setup** tugmachasini bosing
>
>![3 4](https://user-images.githubusercontent.com/61009662/125901813-49cb3703-a5cf-4044-a67e-a7b59a7fc84f.png)


>O'ng panelda, uni tahrirlash uchun **SetupType** faylini ikki marta bosing. Yangi ochilgan oynada *Value Type*ni **2** ga o'zgartiring, so'ngra **OK** tugmasini bosing
>
>![3 5](https://user-images.githubusercontent.com/61009662/125902173-00c65618-a76c-4a10-a904-49950ba2fc77.png)


>O'ng panelda, uni tahrirlash uchun **CmdLine** ikki marta bosing. Yangi ochilgan oynada *Value Type*ni **cmd.exe** ga o'zgartiring va **OK** tugmasini bosing.
>
>![3 6](https://user-images.githubusercontent.com/61009662/125902584-83845aa9-5c87-4cc0-8916-b36d2cfa8ed2.png)


>Chap panelda **temp** ustiga bosib, uni ajratib ko'rsatganingizdan keyin yuqori panelda *Fayl* -> *Unload Hive* ni bosing.
>
>![3 7](https://user-images.githubusercontent.com/61009662/125902795-a628193a-e652-40e4-94b5-bb80091539a9.png)

>![3 8](https://user-images.githubusercontent.com/61009662/125902831-1960b61d-9f80-4044-822e-1714d4a826f9.png)


>Tasdiqlash uchun so'rovda **Yes** tugmasini bosing
>
>![3 9](https://user-images.githubusercontent.com/61009662/125902933-c8d8e1fc-6050-4359-abce-b2eb9a865be8.png)

>Endi **Registry Editor**ni yoping va kompyuterni *restart(перезагружать)* qiling.

###### Kompyuter yangidan yonganida sizda endi **CMD** oynasi to'g'ridan to'g'ri ochiladi
 
### 4 - Parolni tiklash uchun CMD oynasida quyidagi buyruqlarini ishga tushiring

>Parolni qayta tiklash uchun `net user` buyrug'idan foydalanamiz. Bu `net user <username> <new password>` ni terib **Enter** tugmasini bosish orqali amalga oshiriladi.
>
>![4](https://user-images.githubusercontent.com/61009662/125904485-816bc86b-0e82-4a65-9d15-c7713d238347.png)

*Agar **username** ham esingizdan chiqqan bolsa siz yangi user qoshishingiz mumkin. Bu uchun `net user <newuser> <newpassword> /add` buyrug'idan foydalanasiz.
Buyerda `<newuser>` ga istalgan *username* va `<newpassword>` ga istalgan parolingizni qoyishingiz mumkin.

!Eslatma: Agar **username** nomingizda bo'sh joy mavjud bo'lsa, buyruqni kiritishda foydalanuvchi nomini ikkita ""("Aliyev Vali") qo'shtirnoq bilan o'rab olishingiz kerak.


### 5 -Registerda qilingan ishlarni orqaga qaytarish

>Endi **CMD** oynasida `regedit` buyrug'ini yozing va **Enter** tugmasini bosing, so'ngra **Registry Editor** muharriri ochiladi.
>
>![5](https://user-images.githubusercontent.com/61009662/125906119-ed9140e2-f624-4b16-b373-c3480019043e.png)


>**HKEY_LOCAL_MACHINE\SYSTEM\Setup** ga o'ting va **CmdLine** qiymati bo'sh qoldiring va **SetupType** qiymati **0** ga tenglashtiring
>
>![5 1](https://user-images.githubusercontent.com/61009662/125906494-cd7bcbc1-fe36-4833-8191-2f958897a191.png)



##### *Regedit* va *CMD* oynalarini yoping, kompyuterni qayta ishga tushiring (reboot) va kompyuter qayta yonganidan keyin siz yangi kiritgan parolingiz bilan kirishingiz mumkin.


