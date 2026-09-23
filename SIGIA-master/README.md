#SIGIA

Este es un proyecto desarrollado para un curso de desarrollo de aplicaciones WEB, desarrollado en Django 1.8. El proposito de esta aplicación es complir con los requerimientos establecidos en el siguisiente parrafo.

Se requiere desarrollar una aplicación para un concesionario de automóviles; la aplicación tiene como objetivo apoyar las actividades de gestión de inventarios (vehículos y repuestos) de cada sucursal, la generación de cotizaciones, ventas de automóviles y órdenes de trabajo de reparaciones de vehículos. La aplicación tendrá tres tipos de usuarios gerente, vendedores y jefe de taller. El gerente puede gestionar la información relacionada las sucursales, los inventarios (vehículos y repuestos) y crear los usuarios vendedores y jefe de taller. Los usuarios vendedores pueden gestionar cotizaciones y venta de vehículos. El usuario jefe de taller gestiona las ordenes de trabajo. Adicionalmente se requiere que los clientes puedan consultar mediante un teléfono móvil si su vehículo que esta en reparación ya esta disponible o no.

#DETALLES DE LA APLICACIÓN

Administrador Django
Usuario: admin
Password: admin

#EJECUCIÓN LOCAL (Windows)

Requisito: Python 2.7 (Django 1.8 y Pillow 2.9.0 no funcionan con Python 3.10+).
Se puede instalar con `winget install --id Python.Python.2 --exact`, queda en `C:\Python27`.

Crear el entorno virtual e instalar dependencias (una sola vez, desde `SIGIA-master`):

```powershell
C:\Python27\python.exe -m pip install --user "virtualenv<20.22"
C:\Python27\python.exe -m virtualenv venv
.\venv\Scripts\activate
pip install -r requirements.txt
```

Crear la base de datos local (no se sube al repo, cada uno tiene la suya):

```powershell
cd concesionario
python manage.py migrate
python manage.py loaddata fixtures/datos_iniciales.json
```

Esto crea los usuarios `admin` (superusuario) y `aurelio` (empleado con rol Gerente).
Para volver a empezar desde cero basta con borrar `db.sqlite3` y repetir los dos comandos.

Levantar el servidor:

```powershell
python manage.py runserver
```

- Aplicación: http://127.0.0.1:8000/
- Administrador Django: http://127.0.0.1:8000/admin/
