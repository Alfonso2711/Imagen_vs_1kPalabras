Aquí tienes una propuesta para el `README.md`. Está estructurado para ser claro, educativo y resaltar tanto el propósito del código como tus conclusiones.

---

# Una Imagen Dice Más Que Mil Palabras 🖼️ vs 📝

### Demostración Computacional de la Teoría de la Información de Shannon

Este proyecto es una demostración en Python que explora los conceptos fundamentales de la **Teoría de la Información de Claude Shannon**. A través de un análisis comparativo entre un texto de 1000 palabras y una fotografía de 1000x1000 píxeles, el código ilustra cómo se mide la información (entropía) y cómo esta afecta la capacidad de compresión de los datos.

## 🚀 Características Principales

* **Cálculo de Entropía de Shannon:** Implementación matemática para calcular los bits por símbolo empíricos usando la fórmula $H(X) = -\sum P(x) \log_2(P(x))$.
* **Mapas de Entropía Visuales:** Divide las matrices de datos (texto e imagen) en una cuadrícula (grid) de 32x32 para visualizar las zonas con mayor y menor densidad de información.
* **Análisis de Compresión:** Utiliza la librería `zlib` para demostrar la relación directa entre la entropía de un archivo y su ratio de compresión.
* **Visualización con Matplotlib:** Genera una figura que contrasta visualmente la fuente de datos con su respectivo mapa de calor de entropía.

## 🛠️ Requisitos

Para ejecutar este código, necesitarás Python 3.x y las siguientes librerías de terceros. Puedes instalarlas ejecutando:

```bash
pip install numpy matplotlib pillow

```

*(Las librerías `io`, `urllib.request` y `zlib` ya vienen incluidas en la biblioteca estándar de Python).*

## 💻 Uso

Simplemente ejecuta el script desde tu terminal o entorno de desarrollo:

```bash
python shannon_demo.py

```

El script automáticamente:

1. Generará un texto de 1000 palabras basado en *Don Quijote de la Mancha*.
2. Descargará una imagen aleatoria de 1000x1000 píxeles desde *Picsum*.
3. Generará una imagen completamente negra del mismo tamaño.
4. Imprimirá los resultados analíticos en la consola y desplegará una ventana gráfica con la comparativa visual.

## 📊 Resultados Esperados

En la consola verás un desglose analítico mostrando:

* La entropía calculada en bits/carácter o bits/valor.
* El tamaño original en memoria (bytes).
* El tamaño estimado de bits físicos frente a los teóricos de Shannon.
* El tamaño tras pasar por un algoritmo de compresión y su ratio de efectividad (ej. `2.50x`).

---

## 📌 CONCLUSIÓN

El análisis arrojado por este script nos permite concluir lo siguiente:

1. **El tamaño de una representación NO determina por sí mismo su cantidad de información.**
2. La **imagen negra** y una imagen compleja tienen exactamente el mismo tamaño físico sin comprimir en memoria (misma cantidad de píxeles).
3. Sin embargo, su entropía es muy diferente:
* **Imagen negra:** $H = -0.0000$
* **Fotografía:** $H = 7.2611$


4. **Una señal altamente predecible (como la imagen negra) puede comprimirse mucho más** que una señal impredecible (como la fotografía).
5. **La entropía de Shannon mide incertidumbre estadística, NO significado semántico.** El texto puede tener un profundo significado para un humano, pero a nivel estadístico de los bytes que lo componen, posee un nivel de entropía y compresión distinto al de una imagen.
