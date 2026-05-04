<<<<<<< HEAD
<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

In addition, [Laracasts](https://laracasts.com) contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

You can also watch bite-sized lessons with real-world projects on [Laravel Learn](https://laravel.com/learn), where you will be guided through building a Laravel application from scratch while learning PHP fundamentals.

## Agentic Development

Laravel's predictable structure and conventions make it ideal for AI coding agents like Claude Code, Cursor, and GitHub Copilot. Install [Laravel Boost](https://laravel.com/docs/ai) to supercharge your AI workflow:

```bash
composer require laravel/boost --dev

php artisan boost:install
```

Boost provides your agent 15+ tools and skills that help agents build Laravel applications while following best practices.

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
=======
# Laboratorio-CRUD

## 📌 Descripción

Este proyecto consiste en el desarrollo de un sistema CRUD (Crear, consulta, actualizar, Eliminar) utilizando
el framework Laravel. Permitiendo gestionar productos mediante operaciones básicas de base de datos, aplicando el patrón MVC (Modelo-Vista-Controlador) y utilizando Blade como motor de plantillas.


---

## 🚀 Instalación del proyecto

### 1. Crear el proyecto
Primero entrar a la carpeta wamp y ejecute el comando para crear el proyecto
![Captura CRUD](img1.png)

---

### 2. Configurar base de datos

Edite el archivo .env y cambie la base de datos a mysql ya que estaba en sqllite
![Captura CRUD](img2.png)


phpMyAdmin cree la base de datos con el nombre: crud_rapido

![Captura CRUD](img3.png)

---

### 3. Crear modelo y migración

En visual studio code abri una terminal y me ubique dentro del proyecto laravel que se creo "crud_rapido"
y ejecute el comando: php artisan make:model Product -m

![Captura CRUD](img4.png)

luego edite la migración del archivo products

![Captura CRUD](img5.png)

---

### 4. Ejecutar migraciones

Ejecute las migraciones

![Captura CRUD](img6.png)


### 5. Instalar generador CRUD

ejecute el comando: composer require ibex/crud-generator --dev

![Captura CRUD](img7.png)


---

### 6. Publicar archivos

ejecute el comando: php artisan vendor:publish --tag=crud
![Captura CRUD](img8.png)

---

### 7. Generar CRUD

luego genere el CRUD con el comado: php artisan make:crud products

![Captura CRUD](img9.png)

Me preguto que elegir y escribi: Blade with Bootstrap css.

El siguio ejecutándose y me dice que el modelo Product ya existe entonces puse n ya que no
queria sobrescribirlo, luego de eso seguio ejecutándose y que el crub de creo correctamente 

![Captura CRUD](img10.png)

---

### 8. Configurar rutas
Aqui configure las rutas en el archivo: routes/web.php

```php
use App\Http\Controllers\ProductController;

Route::resource('products', ProductController::class);
```
![Captura CRUD](img11.png)


---

### 9. Levantar el servidor y ejecutar el proyecto

ejecute los comandos npm run y npm iinstall

```bash
npm install
npm run dev
```
en otra terminal ejecute:

```bash
php artisan serve
```

#### 🔹 Error ProductRequest

al abrir http://127.0.0.1:8000/products en mi navegador Ya estaba dentro

![Captura CRUD](img12.png)

Pero al presionar el boton crear me salio el siguiente error:

![Captura CRUD](img13.png)

El controlador está intentando usar un archivo llamado: ProductRequest, Pero NO existe en el proyecto
Investigando porque pasa, es el generador CRUD a veces crea validaciones pero no crea el archivo automáticamente 

Solución: ir  app/Http/Controllers/ProductController.php

Elimine la linea:

```php
use Illuminate\Http\Request;
```
cambie el metodo store

![Captura CRUD](img14.png)

Y el metodo update:
![Captura CRUD](img15.png)


#### 🔹 Error Mass Assignment

Ahora tenia el siguiente error

![Captura CRUD](img16.png)

Laravel no me dejo guardar datos por seguridad: mass assignment

En Product.php agregue lo siguiemte:

![Captura CRUD](img17.png)

---

## ▶️ Ejecución del proyecto

![Captura CRUD](img18.png)

y ahora si pude Crear productos, Listar productos, Editar productos y Eliminar productos

---

## 👨‍🎓 Información del Estudiante

**Nombre:** Kathlyn Morales
**Carrera:** Desarrollo y Gestión de Software
**Materia:** Desarrollo de Software VII
**Profesor:** IRINA FONG
**Fecha de entrega:** Lunes 27 de abril 2026


---
>>>>>>> b8b9093a1a3f78c43adb4ef8d79e7fb5006bce1e
