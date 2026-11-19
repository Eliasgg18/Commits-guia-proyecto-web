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
Los archivos usan modulos ES, por lo que no funcionan con doble clic. Opciones:

1. Servidor de Python:
   ```bash
   git clone https://github.com/Eliasgg18/Commits-guia-proyecto-web.git
   cd Commits-guia-proyecto-web
   python3 -m http.server 8000
   ```
   Abrir http://localhost:8000 en el navegador.
2. Extension **Live Server** de VS Code (clic derecho en `index.html` → Open with Live Server).

No requiere instalar dependencias: es HTML, CSS y JavaScript puro.

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
- Calidad del Codigo y README: 15 pts

## 7. Analisis de Complejidad

| Modulo | Algoritmo | Tiempo | Espacio | Justificacion |
|---|---|---|---|---|
| A | `calcularProbabilidadDados` | O(1) | O(1) | Dos ciclos fijos de 6x6 = 36 iteraciones, sin importar la entrada |
| A | `calcularPartidosTorneo` | O(1) | O(1) | Formula directa C(n,2) = n(n-1)/2 |
| A | `contarMultiplosMenores` | O(1) | O(1) | Una division entera con `Math.floor`, sin recorrer el rango |
| A | `calcularViajesMinimos` | O(1) | O(1) | Una division con `Math.ceil` |
| B | `resolverCuadratica` | O(1) | O(1) | Numero fijo de operaciones aritmeticas (formula estable de Citardauq) |
| B | `dibujarParabola` | O(k) | O(1) | Recorre k = 120 puntos para trazar la curva (constante en la practica) |
| C | `analizarSecuencia` | O(n) | O(n) | Recorre el arreglo para razones y diferencias; guarda los arreglos `d1` y `d2` |
| D | `ejecutarSuiteCompleta` | O(t) | O(t) | Ejecuta t = 10 pruebas y guarda un resultado por cada una |

Notas:
- n es el tamano de la secuencia ingresada en el Modulo C.
- Los algoritmos del Modulo A son O(1) porque usan formulas cerradas en lugar de ciclos.
- `resolverCuadratica` evita la cancelacion catastrofica con `q = -0.5 * (b + sgn(b) * sqrt(delta))`, sin costo extra en complejidad.

## Autor
- Nombre: Samuel Elias Garcia Cifuentes
- Programa: Analisis y Desarrollo de Software (ADSO), SENA
- Repositorio: https://github.com/Eliasgg18/Commits-guia-proyecto-web
