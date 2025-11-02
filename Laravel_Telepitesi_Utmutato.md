#  Laravel Telepítési Útmutató

Ez a dokumentum lépésről lépésre bemutatja, hogyan telepítsd és futtasd a **Laravel** keretrendszert a gépeden.

---

##  1. Előfeltételek

Laravel futtatásához az alábbi programok szükségesek:

- **PHP 8.1 vagy újabb**
- **Composer** – PHP csomagkezelő
- **Node.js és npm** – frontend eszközök (Vite, Tailwind stb.)
- **Egy webszerver** (pl. Apache vagy a Laravel beépített szervere)

Ellenőrizd, hogy ezek telepítve vannak:

```bash
php -v
composer -V
node -v
npm -v
```

Ha valamelyik hiányzik, töltsd le és telepítsd őket:

- [PHP letöltés](https://windows.php.net/download/)
- [Composer letöltés](https://getcomposer.org/download/)
- [Node.js letöltés](https://nodejs.org/)

---

##  2. Új Laravel projekt létrehozása

Composer segítségével hozd létre a projektet:

```bash
composer create-project laravel/laravel projekt-neve
```

 Példa:
```bash
composer create-project laravel/laravel blog
```

Ez letölti és telepíti a legújabb Laravel verziót a `blog` mappába.

---

##  3. Laravel fejlesztői szerver indítása

Lépj be a projekt mappájába:

```bash
cd blog
```

Majd indítsd el a beépített szervert:

```bash
php artisan serve
```

Ha minden rendben, a konzolban ez jelenik meg:

```
Starting Laravel development server: http://127.0.0.1:8000
```

Most nyisd meg a böngészőben:  
 [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

##  4. Környezeti beállítások (.env)

A Laravel automatikusan létrehoz egy `.env` fájlt, ahol a környezeti beállításokat találod.  
Itt módosíthatod például az adatbázis kapcsolatot:

```env
APP_NAME="Laravel Blog"
APP_ENV=local
APP_KEY=base64:kulcs...
APP_DEBUG=true
APP_URL=http://127.0.0.1:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=blog
DB_USERNAME=root
DB_PASSWORD=
```

Ha módosítod az `.env` fájlt, futtasd újra a szervert, vagy használd:

```bash
php artisan config:cache
```

---

##  5. Frontend build (opcionális)

Ha a projekt használ Vite-ot vagy Tailwindet, telepítsd a függőségeket:

```bash
npm install
npm run dev
```

Ez elindítja a frontend build folyamatot, és élőben frissíti a fájlokat.

---

##  6. Kész!

Most már készen állsz a fejlesztésre.  
A Laravel fut, a böngészőben elérhető, és készen áll arra, hogy saját alkalmazásodat építsd vele.  

---

### Hasznos parancsok

| Parancs | Leírás |
|----------|--------|
| `php artisan serve` | Laravel szerver indítása |
| `php artisan migrate` | Adatbázis migráció futtatása |
| `php artisan make:model ModelName -m` | Új model + migráció létrehozása |
| `npm run dev` | Frontend fejlesztői build indítása |

---

**Készen is van!**  
Ha ezt `README.md` néven elmented a projekted gyökerébe, GitHubon és VS Code-ban szépen formázva fog megjelenni.
