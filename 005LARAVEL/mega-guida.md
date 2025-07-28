# Step by Step
### Model e Migration
1. Crea un nuovo progetto con `laravel new nome-progetto`
2. Lancia `php artisan serve` in un nuovo terminale
3. Apri un nuovo terminale, installa e lancia `npm i bootstrap` e successivamente `npm run dev`
4. Importa Bootstrap dentro `resources/css/app.css` e `resources/js/app.js`; Ricorda di importare `@vite([])`
5. Apri TablePlus e crea il database del progetto;
6. Configura il Database dentro il file `.env`

```

DB_CONNECTION=mysql 
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=nome_del_DB (il nome usato al punto 5)
DB_USERNAME=tuo_username (solitamente root)
DB_PASSWORD=tua_password (solitamente rootroot)
```

7. Crea la migrazione per la tabella `books` con il comando `php artisan make:migration create_books_table`
8. Andiamo ad aggiungere 3 colonne:
    
    ```php
    $table->string('name');
    $table->integer('years')
    $table->integer('pages')
    ```
    
9. Lancia la creazione della tabella con `php artisan migrate`

10. Definisci le rotte:

```php

  Route::get('/books', [BookController::class, 'index'])->name('books.index');
  Route::get('/books/create', [BookController::class, 'create'])->name('books.create');
  Route::post('/books/store', [BookController::class, 'store'])->name('books.store');

```

11. Crea il controller `BookController` con il comando `php artisan make:controller BookController`
12. Scrivi i 3 metodi nel controller:
    - index: Recupera tutti i libri con Book::all();
    - create: Un semplice form;
    - store: L’azione da eseguire quando si clicca su salva;
13. Crea le view relative utilizzando un layout ed eventualmente dei componenti per creare una struttura responsive con Bootstrap 5.
    - books/index
    - books/create
    - components/main
    - components/navbar 
14. Aggiungi la nuova colonna negli attributi `$fillable` del Model appena creato Book
```php artisan make:model Book ```

```php
  protected $fillable = [
        'name',  'pages', 'years'
    ];
```
### File Upload & Validation Rules

1. Crea una nuova migrazione, questa volta di modifica tabella con `php artisan make:migration add_to_books_table`
2. Aggiungi una colonna nuova relativa all'immagine di copertina  nel metodo `up()` e il `dropColumn` nel metodo `down()`:
    
    ```php
     public function up(): void
    {
        Schema::table('books', function (Blueprint $table) {
            $table->string('image')->nullable();
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::table('books', function (Blueprint $table) {
            $table->dropColumn('image');
        });
    }
    ```
3. Aggiungi la nuova colonna negli attributi `$fillable` del Model Book    
4. Lancia la modifica della tabella con `php artisan migrate`
5. Definisci le rotte facendo attenzione ad utilizzare la nomenclatura corretta anteponendo il nome del model avanti al metodo (book.index ad esempio):

```php 
Route::get('/books', [BookController::class, 'index'])
  ->name('books.index');

Route::get('/books/create', [BookController::class, 'create'])
  ->name('books.create');

Route::post('/books/store', [BookController::class, 'store'])
  ->name('books.store');

Route::get('/books/{book}/show', [BookController::class, 'show'])
  ->name('books.show');
```
6. Se non lo hai ancora fatto, crea il controller `BookController` con il comando `php artisan make:controller BookController`
7. Scrivi i 4 metodi nel controller:
    - index: Recupera tutti i libri con Book::all();
    - create: Un semplice form;
    - store: L’azione da eseguire quando si clicca su salva;
    - show: una pagina di dettaglio per visualizzare il dato singolo
8. Crea le view relative utilizzando un layout ed eventualmente dei componenti per creare una struttura responsive con Bootstrap 5.
    - books/index
    - books/create
    - books/show
    - components/main
    - components/navbar
9. Crea una Request Class chiamata BookStoreRequest per validare i dati inseriti con il comando `php artisan make:request BookStoreRequest` (ricordati di autorizzare il metodo `authorize()`)
10. Inserisci le `rules()` nella classe appena dichiarata e iniettala nel metodo `store()` di `BookController`

```php
    public function store(BookRequest $request)
    {
        //
    }
```
11. Inserisci nel form  `create`  l’enctype e il campo input file
12. Gestisci l’immagine nel controller e utilizza lo `storeAs()` per salvarlo con un nome e un percorso personalizzato
13. Inserisci il path_name nel `Book::create([])`
14. Lancia il comando `php artisan storage:link` per creare il collegamento con la cartella storage
15. Nella view della card utilizza l’helper di Blade `{{Storage::url($book→image)}}` 

### Laravel Fortify & Middleware

1. Installo fortify: composer require laravel/fortify

2. Porto i file di Fortify che mi servono da vendor al mio progetto:`php artisan fortify:install`

3. Aggiorno il database con le migrazioni di laravel `php artisan migrate`


4. In FortifyServiceProvider indico a Fortify come deve restituire le viste di login e register

    ```php
    Fortify::loginView(function () {
        return view('auth.login');
    });

    Fortify::registerView(function () {
        return view('auth.register');
    });
 
    // 
    ```
7. Creo il file `resources/views/auth/register.blade.php` .Questo blade ha bisogno di:

- method POST
- action {{ route('register') }}
- i campi: name, email, password, password_confirmation

8. Nella navbar, gestisco il logout (Scrivetelo a mano per abituarvi!)

```php
 <form action="{{ route('logout') }}" method="POST">
    @csrf
    <button class="btn btn-danger" type="submit">
        Esci
    </button>
</form>

```
9. Mi dara' errore, quindi gestisco la navbar con le direttive blade @auth @endauth o @guest @endguest

10. Creo il file `resources/views/auth/login.blade.php.` Questo blade ha bisogno di:

- method POST
- action {{ route('login') }}
- i campi: email, password
- Provo a loggarmi

Se tutto funziona, ho correttamente installato Laravel Fortify! 🚀

11. Middleware. Laravel ci permette diversi modi di utilizzare un middleware, utilizzate quello che preferite

### CRUD
1. Aggiungo le rotte mancanti per compleatre il CRUD:
```php 
Route::get('/books/{book}/edit', [BookController::class, 'edit'])
  ->name('books.edit');

Route::put('/books/{book}/update', [BookController::class, 'update'])
  ->name('books.update');

Route::delete('/books/{book}', [BookController::class, 'destroy'])
  ->name('books.destroy');
```

2. Vado nel BookController e specifico i relativi metodi
3. Edit:

```php 
 public function edit(Book $book)
    {

        return view('books.edit', compact('book'));
    }
```

4. Update:
```php

 public function update(BookUpdateRequest $request, Book $book)
    {
        $path_image = $book->image; // inserire immagine gia presente
        if ($request->hasFile('image')) {
            $file_name = $request->file('image')->getClientOriginalName();
            $path_image = $request->file('image')->storeAs('covers', $file_name, 'public');
         
        }
    
        $book->update([
            'name' => $request->name,
            'pages' => $request->pages,
            'year' => $request->year,
            'image' => $path_image,
        ]);

        return redirect()->route('books.index')->with('success', 'Libro Aggiornato');
    }

```

5. Destory:

```php

    public function destroy(Book $book)
    {
        $book->delete();
        return redirect()->route('books.index')->with('success', 'Libro Eliminato');
    }
```

6. View: In ultimo, creare la vista edit per gestire il form di modifica
7. Tutte le rotte pososno essere sostituite da: ```php Route::resource('books', BookController::class);```
8. Extra: Esiste un comando all in one per generare tutto: ``` php artisan make:model Author -mcrR ```
