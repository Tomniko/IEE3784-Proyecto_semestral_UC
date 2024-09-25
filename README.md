# README: DICOM Image Processing and Vertebra Segmentation with B-Splines
## Resumen
Este repositorio contiene un script en Python que permite cargar imágenes DICOM, visualizar cortes coronales interactivos y aplicar interpolación B-spline sobre vértebras seleccionadas manualmente. Además, permite medir la altura proyectada de las vértebras en las imágenes procesadas.

## Requisitos

Para ejecutar el script, asegúrate de tener instaladas las siguientes dependencias:

- Python 3.x
- [pydicom](https://pydicom.github.io/)
- [numpy](https://numpy.org/)
- [matplotlib](https://matplotlib.org/)

Puedes instalar las dependencias usando el siguiente comando:

```bash
pip install pydicom numpy matplotlib
```

## Funcionalidades
1. Carga y visualización de archivos DICOM:

- El script carga todos los archivos DICOM en una carpeta y los ordena correctamente según su posición en el espacio 3D.

2. Interfaz interactiva de selección de vértebras:

- Puedes navegar por los cortes coronales utilizando un deslizador. Al fijar un corte, puedes seleccionar puntos sobre las vértebras manualmente.

3. Interpolación B-spline:

- Después de seleccionar los puntos de una vértebra, puedes generar curvas suavizadas utilizando interpolación cúbica B-spline para marcar los contornos de las vértebras.

4. Medición de la altura vertebral:

- La altura de las vértebras se calcula proyectando la distancia vertical entre los puntos más altos y bajos de la región delimitada por la curva B-spline.

## Cómo usar
1. Coloca todos los archivos DICOM en una carpeta y asegúrate de que están en formato .dcm.

2. Modifica la variable folder_path en el script main() con la ruta de la carpeta donde se encuentran tus archivos DICOM.

3. Ejecuta el script con el siguiente comando:

```bash
python nombre_del_script.py
```

4. Usa el deslizador para navegar entre los cortes coronales. Cuando encuentres un corte que quieras analizar:

- Presiona x para fijar el corte coronal.
  
- Haz clic en los puntos que delimitan la vértebra.
  
- Presiona n para comenzar la selección de una nueva vértebra.
  
- Presiona r para generar las curvas B-spline de las vértebras seleccionadas.
  Detalle> Es necesario que se presione n una vez se termina de seleccionar todas los puntos en las vertebras.
  
- Presiona c para aplicar una máscara y recortar la región delimitada por la B-spline.
  
- Presiona q para finalizar la selección y calcular la altura de las vértebras.

## Controles
* x: Fijar el corte coronal actual.
* n: Iniciar la selección de una nueva vértebra.
* r: Dibujar la interpolación B-spline sobre las vértebras seleccionadas.
* c: Recortar la región delimitada por la B-spline en la última vértebra seleccionada.
* q: Finalizar la selección de puntos y mostrar las alturas proyectadas de las vértebras.

## Ejemplo de uso
*  Al ejecutar el script, verás una ventana con un corte coronal de las imágenes DICOM cargadas. Puedes navegar entre los cortes utilizando el deslizador. A continuación, selecciona manualmente los puntos que delimitan cada vértebra y aplica la interpolación para visualizar las curvas suavizadas.

- El script calculará la altura de las vértebras y mostrará una gráfica con las alturas proyectadas en función de las coordenadas x.

## Licencia

Este proyecto está bajo la licencia MIT. Siéntase libre de utilizar y modificar el código según sea necesario.
