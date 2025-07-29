Per iniziare, clona la repository del progetto ed entra nella cartella appena creata:

```bash
git clone git@github.com:NomeCognome/progetto.git

cd progetto
```

Successivamente, installa le dipendenze necessarie:

```bash
composer install
npm install
```

Configura l’ambiente di sviluppo:

```bash
cp .env.example .env

php artisan key:generate

```

Crea il database e lancia le migrazioni:

```bash
touch database/database.sqlite

php artisan migrate
```

Infine, lancia il server locale con:

```bash
php artisan serve
npm run dev
```

Oppure

```bash
composer run dev
