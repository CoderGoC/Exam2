# Data Science EXAM

Ushbu repository CoderGoC tomonidan yaratilgan data science uy vazifalarini o'z ichiga oladi. Bu yerda turli data science muammolarini hal qilish bo'yicha mashqlar, kodlar va natijalar jamlangan.

# Yoshni Bashorat Qilish Uchun Huber Regressor Modeli

## Umumiy ma'lumot
Ushbu loyiha turli xususiyatlarga ega ma'lumotlar to'plamidan foydalanib, `Yosh`ni bashorat qilishga qaratilgan. Model, xatolarga chidamli va oddiy chiziqli regressiya bilan murakkab modellarning o'rtasini ushlab turuvchi `HuberRegressor` yordamida qurilgan.


## Loyiha tuzilishi
- **train.csv**: Xususiyatlar va maqsadli o'zgaruvchini (`Yosh`) o'z ichiga olgan o'quv ma'lumotlar to'plami.
- **test.csv**: Bashoratlar ishlab chiqariladigan test ma'lumotlar to'plami.
- **main.py**: Ma'lumotlarni yuklab olish, ularni oldindan qayta ishlash, model pipeline'ini qurish va bashoratlarni chiqarish uchun asosiy skript.
- **submission.csv**: Test to'plami uchun bashoratlarni o'z ichiga olgan chiqish fayli, Kaggle'ga topshirishga tayyor.
- **README.md**: Ushbu loyiha haqida umumiy ma'lumot beruvchi fayl.

## Xususiyatlar va Maqsad
- **Xususiyatlar**: Ma'lumotlar to'plami turli xususiyatlarni, jumladan, kategoriyali va sonli o'zgaruvchilarni o'z ichiga oladi.
- **Maqsad**: Maqsadli o'zgaruvchi `Yosh` bo'lib, model uni bashorat qilishga qaratilgan.

## Ma'lumotlarni Oldindan Qayta Ishlash
Oldindan qayta ishlash qadamlarini quyidagilar tashkil qiladi:
1. **Xususiyatlarni Muhandislik**: `feature_funk` deb nomlangan maxsus funksiya `Sex` ustunidagi kategoriyali qiymatlarni xaritalash va ma'lumotlarni filtrlash uchun ishlatiladi.
2. **Imputatsiya**: Yetishmayotgan sonli qiymatlar o'rtacha bilan to'ldiriladi.
3. **Polinomial Xususiyatlar**: Noliniy bog'liqliklarni aniqlash uchun interaktiv xususiyatlar qo'shiladi.
4. **Shkalalash**: Sonli xususiyatlar `StandardScaler` yordamida standartlashtiriladi.

## Model Pipeline'i
Model pipeline'i quyidagi qadamlarni o'z ichiga oladi:
1. **Oldindan Qayta Ishlash**: Polinomial xususiyatlar va shkalalash yordamida sonli xususiyatlarni o'zgartirish.
2. **Xususiyatlarni Tanlash**: Kross-valitatsiya bilan Rekursiv Xususiyatlarni Yo'qotish (RFECV) yordamida eng muhim xususiyatlar tanlanadi.
3. **Modellashtirish**: Maqsadli o'zgaruvchini (`Yosh`) bashorat qilish uchun `HuberRegressor` ishlatiladi.

## Model Baholash
Model quyidagi ko'rsatkichlar yordamida baholanadi:
- **Kross-Valitatsiya (CV)**: Modelni baholash uchun 10 ta bo'linma kross-valitatsiya ishlatiladi, bu esa xatoni kamaytiradi va umumlashtirishni ta'minlaydi.
- **Ko'rsatkichlar**: Test to'plamida O'rtacha Mutlaq Xato (MAE), O'rtacha Kvadrat Xato (MSE) va R^2 Ko'rsatkichi hisoblanadi.


## Ishlatilgan texnologiyalar

Ushbu loyihada quyidagi texnologiyalar va kutubxonalardan foydalanilgan:
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Qanday foydalanish

1. Repositoryni klonlash:
   ```bash
   git clone https://github.com/CoderGoC/Homework.git
   ```
2. Virtual muhit yaratish va kerakli kutubxonalarni o'rnatish:
   ```bash
   cd Data-science-home-work
   python -m venv venv
   ```
   ```bash
   source venv/bin/activate  # Linux/Mac
   ```
   ```bash
   .\venv\Scripts\activate  # Windows
   ```
   ```bash
   pip install -r requirements.txt
   ```
3. Jupyter Notebook'ni ishga tushirish:
   ```bash
   jupyter notebook
   ```

## Hissa qo'shish

Agar loyihaga hissa qo'shmoqchi bo'lsangiz, iltimos quyidagi qadamlarni bajaring:
1. Repositoryni fork qiling
2. Yangi branch oching (`git checkout -b feature/YourFeature`)
3. O'zgarishlarni kiritib commit qiling (`git commit -m 'Add some feature'`)
4. Branchni push qiling (`git push origin feature/YourFeature`)
5. Pull request yarating

## Litsenziya

Ushbu loyiha MIT litsenziyasi ostida tarqatiladi. Batafsil ma'lumot uchun [LICENSE](LICENSE) faylini ko'rib chiqing.



Loyihaga qiziqishingiz uchun rahmat!
