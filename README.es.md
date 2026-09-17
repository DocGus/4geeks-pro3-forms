# 💳 Payment Form — 4Geeks

<div style="background:#111827; color:#ffffff; padding:12px 16px; border-left:4px solid #60a5fa; border-radius:10px; margin:12px 0; font-weight:500;">
Recreación de un formulario de pago utilizando HTML5 y CSS3.
</div>

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-local-000000?logo=flask&logoColor=white)
![Git](https://img.shields.io/badge/Git-version--control-F05032?logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-repository-181717?logo=github&logoColor=white)

## 📌 Descripción

Este proyecto forma parte de los ejercicios de **4Geeks Academy**.

El objetivo es recrear un formulario de pago a partir de una referencia visual, utilizando **HTML5 y CSS3**, y practicar la creación de formularios, tipos de entrada, validaciones HTML5, estructura semántica y organización de estilos.

El proyecto comenzó utilizando la [plantilla oficial de 4Geeks Academy](https://github.com/4GeeksAcademy/html-hello), que incluye un servidor local basado en Flask.

## 🚀 Cómo ejecutarlo

### Requisitos

- Python 3
- Navegador web
- Git

### Crear el entorno virtual

Desde la carpeta del proyecto:

```bash
python3 -m venv venv
```

Activar el entorno virtual:

En Linux/macOS:

```bash
source venv/bin/activate
```

Cuando el entorno está activo, la terminal muestra:

```bash
(venv)
```

### Instalar Flask

Con el entorno virtual activado:

```bash
pip install flask
```

### Iniciar el servidor local

Ejecuta:

```bash
python server.py
```

El servidor estará disponible en:

```text
http://localhost:3000
```

Para detener el servidor:

```text
Ctrl + C
```

### Desactivar el entorno virtual

Cuando termines de trabajar:

```bash
deactivate
```

## 🛠️ Tecnologías utilizadas

| Tecnología | Uso |
| --- | --- |
| HTML5 | Estructura y formulario |
| CSS3 | Diseño, distribución y estilos |
| Python 3 | Entorno de ejecución |
| Flask | Servidor local de desarrollo |
| Git | Control de versiones |
| GitHub | Repositorio remoto |

## 🧱 Estructura del proyecto

```text
4geeks-pro3-forms/
├── index.html
├── style.css
├── server.py
├── learn.json
├── README.md
├── README.es.md
├── README.cn.md
├── .gitignore
└── venv/
```

Durante el desarrollo también se utiliza un entorno virtual. El entorno virtual se mantiene fuera del control de versiones mediante `.gitignore`.

El archivo `index.html` contiene la estructura del formulario y `style.css` contiene los estilos.

La hoja de estilos se conecta mediante:

```html
<link rel="stylesheet" href="style.css">
```

## 📝 Estructura del formulario

El formulario se dividió en diferentes bloques:

```text
Payment Form
├── Título
├── Mensaje de alerta
├── Información de tarjeta
│   ├── Card #
│   ├── CVC #
│   └── Amount
├── Información personal
│   ├── First Name
│   ├── Last Name
│   ├── City
│   ├── State
│   └── Postal Code
├── Métodos de pago
│   ├── Mastercard
│   ├── Visa
│   └── American Express
├── Message
├── Botones
│   ├── Cancel
│   └── Send
```

## 🧩 HTML5 Forms

Uno de los objetivos principales del proyecto fue practicar diferentes tipos de elementos de formulario.

### Input de texto

Se utilizó `type="text"` para campos como nombre, apellido, ciudad y número de tarjeta:

```html
<input
    type="text"
    id="first-name"
    name="first-name"
    placeholder="First Name"
    required
>
```

### Input numérico

Para el importe del pago se utilizó:

```html
<input
    type="number"
    id="amount"
    name="amount"
    placeholder="Amount"
    min="0"
    step="0.01"
    required
>
```

Esto permite introducir valores numéricos y especificar incrementos de centavos mediante `step="0.01"`.

## ✅ Validación HTML5

El formulario utiliza las herramientas de validación incorporadas en HTML5.

Entre ellas:

- `required`
- `minlength`
- `maxlength`
- `min`
- `step`
- `pattern`

Por ejemplo, el campo CVC utiliza una expresión regular para aceptar entre 3 y 4 dígitos:

```html
<input
    type="text"
    id="cvc"
    name="cvc"
    pattern="[0-9]{3,4}"
    maxlength="4"
    required
>
```

El código postal utiliza una validación similar para aceptar cinco números:

```html
<input
    type="text"
    id="postal-code"
    name="postal-code"
    pattern="[0-9]{5}"
    maxlength="5"
    required
>
```

La validación se realiza directamente por el navegador antes de enviar el formulario.

## ☑️ Radio Buttons

Para seleccionar el método de pago se utilizaron botones de tipo radio.

Los tres elementos comparten el mismo atributo `name`, por lo que solamente una opción puede seleccionarse:

```html
<input
    type="radio"
    name="card-type"
    value="mastercard"
    required
>
```

Las opciones disponibles son:

- Mastercard
- Visa
- American Express

## 🔽 Select

Para seleccionar el estado se utilizó un elemento `select`:

```html
<select
    id="state"
    name="state"
    required
>
    <option value="">Pick a state</option>
    <option value="california">California</option>
    <option value="texas">Texas</option>
</select>
```

El atributo `required` evita que el formulario se envíe sin seleccionar un estado.

## 🎨 Conceptos de CSS practicados

### Box Model

Se practicaron conceptos fundamentales del modelo de cajas:

- `margin`
- `padding`
- `border`
- `width`
- `box-sizing`

Por ejemplo:

```css
* {
    box-sizing: border-box;
}
```

Esto permite que el ancho y alto de los elementos incluyan su contenido, padding y borde.

### Flexbox

Flexbox se utilizó para organizar horizontalmente los diferentes campos del formulario:

```css
.row {
    display: flex;
    gap: 20px;
    margin-bottom: 20px;
}
```

Los campos utilizan:

```css
.field {
    flex: 1;
}
```

De esta forma, los campos pueden distribuirse dentro de la fila disponible.

### Responsive Design

También se agregó una regla `@media` para adaptar el formulario a pantallas pequeñas:

```css
@media (max-width: 700px) {
    .row {
        flex-direction: column;
    }
}
```

En pantallas pequeñas los campos pasan de una distribución horizontal a una distribución vertical.

## 📄 Separación de HTML y CSS

Inicialmente los estilos se encontraban dentro del archivo `index.html`.

Posteriormente se creó un archivo independiente:

- `style.css`

Y se conectó desde el elemento `<head>`:

```html
<link rel="stylesheet" href="style.css">
```

Esta separación permite mantener por un lado la estructura HTML y por otro los estilos CSS.

## 🖥️ Servidor local con Flask

Durante el desarrollo se utilizó el servidor proporcionado por la plantilla de 4Geeks Academy mediante Flask.

El entorno virtual se activa con:

```bash
source venv/bin/activate
```

Flask se instala mediante:

```bash
pip install flask
```

Y el servidor se inicia con:

```bash
python server.py
```

La aplicación queda disponible en:

```text
http://localhost:3000
```

El archivo `server.py` utiliza Flask para servir `index.html` y los demás archivos estáticos del proyecto, incluyendo `style.css`.

## 📚 Lo que aprendí

- Crear formularios utilizando HTML5.
- Utilizar diferentes tipos de input.
- Utilizar select, textarea y radio buttons.
- Aplicar validaciones HTML5 mediante atributos.
- Utilizar `required`, `pattern`, `min`, `step`, `minlength` y `maxlength`.
- Relacionar un archivo HTML con una hoja de estilos CSS externa.
- Utilizar Flexbox para organizar elementos.
- Aplicar conceptos del Box Model.
- Crear un diseño responsive básico mediante `@media`.
- Crear y utilizar un entorno virtual de Python.
- Instalar y utilizar Flask.
- Ejecutar un proyecto mediante `server.py`.
- Visualizar un proyecto desde un servidor local.
- Utilizar Git y GitHub durante el desarrollo.

## 🔄 Proceso de desarrollo

1. Crear el repositorio a partir de la plantilla de 4Geeks Academy.
2. Clonar el proyecto y abrirlo en VS Code.
3. Recuperar y preparar el archivo `index.html`.
4. Construir la estructura del formulario de pago.
5. Agregar diferentes tipos de campos HTML5.
6. Incorporar validaciones HTML5.
7. Crear los estilos iniciales.
8. Crear el archivo `style.css`.
9. Separar los estilos del documento HTML.
10. Conectar `index.html` con `style.css`.
11. Crear el entorno virtual `venv`.
12. Instalar Flask.
13. Ejecutar `server.py`.
14. Comprobar el formulario en el navegador.
15. Controlar las modificaciones mediante Git.
16. Crear commits y sincronizar el proyecto con GitHub.

## 🎯 Resultado

Una recreación funcional de un formulario de pago utilizando HTML5 y CSS3.

El proyecto permite practicar la creación de formularios, validación nativa del navegador, Flexbox, Box Model, separación de responsabilidades entre HTML y CSS, diseño responsive básico y ejecución de aplicaciones mediante un servidor local de Flask.

## 👨‍💻 Autor

Gustavo A. Santoyo B.

Proyecto realizado como parte del aprendizaje de desarrollo Full Stack en 4Geeks Academy.

## 📖 Plantilla original

El proyecto se inició con la plantilla HTML oficial de 4Geeks Academy.
