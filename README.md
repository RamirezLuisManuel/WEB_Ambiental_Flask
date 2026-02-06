# Documentación Técnica: Aplicación Web "Conciencia Ambiental"
## 1. Descripción General
Esta aplicación web es una plataforma educativa e informativa diseñada para concientizar sobre el cuidado del medio ambiente. Desarrollada con el “micro-framework Flask”, utiliza un motor de plantillas dinámico y un diseño responsivo basado en Bootstrap 5.

## 2. Configuración del Entorno y Creación
Para garantizar la portabilidad y el orden de las dependencias, el proyecto se construyó siguiendo estos pasos:
### Creación del directorio raíz 
mkdir web_medio_ambiente
### Entorno Virtual
Se aisló el proyecto para evitar conflictos de librerías.
### Creación del ambiente llamado venv
python -m venv venv
### Activación el ambiente
venv\Scripts\activate
### Instalación de dependencias
pip install flask

## 3. Estructura del Proyecto
El proyecto sigue la convención estándar de Flask, separando la lógica del servidor de los recursos estáticos y las vistas.

web_medio_ambiente/
├── app.py               # Servidor y lógica de rutas
├── static/                 # Recursos estáticos
│   └── images/         # Banco de imágenes del proyecto
└── templates/          # Vistas HTML (Jinja2)
    ├── base.html       # Plantilla maestra (Layout)
    ├── index.html      # Página de inicio (importancia del medio ambiente)
    ├── sistema.html   # Sistema de gestión ambiental
    ├── futuro.html     # Sostenibilidad
    └── tres_r.html     # Las 3 erres del cuidado ambiental

## 4. Implementación del Backend (Flask)
El archivo app.py gestiona las peticiones del usuario y renderiza las vistas correspondientes, inyectando datos dinámicos como las migas de pan (breadcrumbs).
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def index():
    return render_template(
        'index.html',
        breadcrumb=["Inicio"]
    )

@app.route('/sistema-ambiental')
def sistema():
    return render_template(
        'sistema.html',
        breadcrumb=["Inicio", "Sistema de Gestión Ambiental"]
    )

@app.route('/futuro')
def futuro():
    return render_template(
        'futuro.html',
        breadcrumb=["Inicio", "Futuro del Planeta"]
    )

@app.route('/tres-r')
def tres_r():
    return render_template(
        'tres_r.html',
        breadcrumn=["Inicio","Las 3 R"] 
    )
if __name__=='__main__':
    app.run(debug=True)
    
## 5. Frontend y Diseño Responsivo
La interfaz se diseñó bajo el concepto de Herencia de Plantillas, lo que permite mantener un diseño consistente sin duplicar código.
Estrategia de Diseño:
### Base Maestra (base.html): 
Contiene el Navbar responsivo, la lógica de los breadcrumbs y el footer. Define un bloque {% block content %} donde se inyectan las páginas hijas.
### Componentes Bootstrap: 
Se utilizaron Containers, Rows y Cols para asegurar que la web sea accesible desde dispositivos móviles y escritorio.
### Estética Visual
Se implementaron tarjetas (cards) con sombras y efectos de elevación para mejorar la experiencia de usuario.

#### Paso A: Inicio (importancia del medioambiente)
Se implemento una vista de inicio donde se describe la importancia del medio ambiente como sustento básico, regulador de la temperatura, valor económico y salud pubica.
#### Paso B: El Sistema de Gestión (SGA)
Se implementó una vista técnica que explica la norma ISO 14001, utilizando el ciclo PHVA (Planificar, Hacer, Verificar, Actuar) como eje central de la información.
#### Paso C: El Futuro y Sostenibilidad
En esta sección se integró el concepto de Desarrollo Sostenible, destacando la ética intergeneracional mediante bloques de texto resaltados.
#### Paso D: Las 3 R's
Se diseñó una cuadrícula de tres columnas que prioriza la jerarquía inversa: Reducir como acción principal, seguida de Reutilizar y Reciclar.


## 7. Ejecución y Evidencia
Para poner en marcha el servidor de desarrollo, se ejecuta: python app.py
Resultado esperado: La aplicación estará disponible en http://127.0.0.1:5000.

**Nota Técnica**: El modo debug=True se mantuvo activo durante el desarrollo para permitir la recarga automática del servidor tras cada modificación en los archivos HTML o Python.

### Vista index
<img src="https://drive.google.com/file/d/1t8DBcpa8h1bV8JA1ar3k74Ioiegwk4Xa/view?usp=sharing" width="300" height="200">

### Vista sistema
<img src="https://drive.google.com/file/d/1NU5PITVfXDxRZU2nsmxVR4sLXyM7wxRN/view?usp=sharing" width="300" height="200">

### Vista futuro
<img src="https://drive.google.com/file/d/1gxP-0tsj-6SVO0slMjKcFxw_G49qO_Sx/view?usp=sharing" width="300" height="200">

### Vista tres_r
<img src="https://drive.google.com/file/d/1LfsNSZ9jux_Ez9C8KgxP92eimehyLZRt/view?usp=sharing" width="300" height="200">
