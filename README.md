
# Laboratorio-CRUD

## 📌 Descripción

Este proyecto consiste en el desarrollo de un sistema CRUD (Crear, consulta, actualizar, Eliminar) utilizando
el framework Laravel. Permitiendo gestionar productos mediante operaciones básicas de base de datos, aplicando el patrón MVC (Modelo-Vista-Controlador) y utilizando Blade como motor de plantillas.


---

## Instalación del proyecto

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
