# Suite Matematica y Algoritmica (Proyecto Integrador)
![Build](https://github.com/Eliasgg18/Commits-guia-proyecto-web/actions/workflows/pages/pages-build-deployment/badge.svg)

Evaluacion practica de logica computacional, algebra y precision numerica.
Proyecto integrador para trabajo en casa con control de versiones en GitHub y despliegue en GitHub Pages.

## 1. Modulos del Proyecto
- Modulo A: Retos Logicos BairesDev (probabilidad de dados, torneos, divisores O(1), logistica).
- Modulo B: Motor Cuadratico & Graficador Canvas (ax^2 + bx + c = 0, raices, vertice y grafica).
- Modulo C: Detector de Secuencias (patrones aritmeticos, geometricos y de segundo orden).
- Modulo D: Suite de Autoevaluacion (10 pruebas unitarias en el navegador).

## 2. Estructura de Archivos
- index.html: Interfaz con pestañas.
- css/style.css: Estilos responsivos.
- js/app.js: Coordinador principal de eventos y canvas.
- js/modules/bairesdev.js: Retos logicos.
- js/modules/cuadratica.js: Solucionador cuadratico estable.
- js/modules/secuencias.js: Detector de secuencias.
- js/modules/test-suite.js: Suite de 10 pruebas unitarias.
## Arquitectura
La aplicacion es estatica y no usa frameworks. Esta separada por responsabilidades:
- Capa de logica (js/modules/): funciones sin acceso al DOM. Cada modulo (bairesdev, cuadratica, secuencias) recibe numeros y devuelve un objeto con el resultado.
- Capa de interfaz (js/app.js): lee los formularios, llama a los modulos y pinta los resultados y la parabola en Canvas.
- Capa de pruebas (js/modules/test-suite.js): ejecuta 10 pruebas unitarias en el navegador sobre la capa de logica.
- Presentacion: index.html (estructura con pestañas) y css/style.css (estilos responsivos).

Los archivos usan modulos ES (import/export), por eso se necesita un servidor HTTP para ejecutarlo en local.

## 3. Ejecucion Local
Ejecutar un servidor local HTTP:
```bash
python3 -m http.server 8000
```
Abrir http://localhost:8000 en el navegador.

## 4. Desafios de Precision Numerica (Cascaritas)
1. Cancelacion Catastrofica: Usar formula de Citardauq / Muller cuando b^2 >> 4ac.
2. Caso Degenerado: Manejar a = 0 como ecuacion lineal sin dividir entre cero.
3. Precision Flotante IEEE-754: Usar tolerancia Number.EPSILON para comparar porcentajes.

## 5. Requisitos de Git y GitHub
- Minimo 10 commits significativos con Conventional Commits (feat, fix, style, test, docs).
- Trabajo con ramas y Pull Requests.
- Despliegue activo en GitHub Pages.

## 6. Rubrica (100 Puntos)
- Logica y Matematicas: 25 pts
- Superacion de Casos Borde: 25 pts
- Gestion de Git y Commits: 20 pts
- Despliegue y UX/UI: 15 pts
- Sustentacion Presencial: 15 pts

## Autor
- Nombre: Samuel Elias Garcia Cifuentes
- Programa: Analisis y Desarrollo de Software (ADSO), SENA
- Repositorio: https://github.com/Eliasgg18/Commits-guia-proyecto-web

## Ejecución local

1. Clona el repositorio:
   ```bash
   git clone https://github.com/Eliasgg18/Commits-guia-proyecto-web.git
   ```
2. Entra a la carpeta del proyecto:
   ```bash
   cd Commits-guia-proyecto-web
   ```
3. Abre `index.html` en tu navegador (doble clic) o usa la extensión **Live Server** de VS Code.

No requiere instalar dependencias: es HTML, CSS y JavaScript puro.
