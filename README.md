# Dashboard de compras — María Ximena Torrez Campero

## Abrir
Abre `index.html` con un navegador. Funciona sin internet, sin instalar dependencias y sin servidor. Los datos están incluidos dentro del HTML.

## Publicar en GitHub Pages
1. Crea un repositorio en GitHub y sube el contenido de esta carpeta a la raíz.
2. En Settings → Pages, selecciona Deploy from a branch.
3. Selecciona la rama main y la carpeta / (root), y guarda.
4. Abre el enlace que GitHub Pages muestre al finalizar la publicación.

El HTML contiene información del cliente. Elige la visibilidad del repositorio y del sitio según el acceso que quieras dar.

## Datos y criterios
- Fuente: ximena.csv proporcionado por el usuario. Cuenta CC2342, del 07/01/2026 al 12/10/2026. Octubre es un período parcial.
- El total suma IMPORTE_BS exactamente como aparece, incluidos N1, FA y D2. No representa un saldo, pago ni deuda; la fuente no proporciona estos conceptos.
- D2 no tiene definición en el archivo; se conserva con su importe positivo de Bs 104,00. El filtro de tipo permite excluirlo.
- Documentos únicos: combinación TI + NÚMERO. Productos únicos: código ITEM. Promedio por documento: importe del filtro dividido entre documentos únicos del filtro.
- La fila 52 repite los mismos campos de la fila 51 (N1 023248, artículo 50080, Bs 800,00). Se conservan ambas porque no se puede determinar si es un error o una segunda línea válida.
- Las cantidades se muestran por unidad original (LTR y BDN), sin mezclarlas ni convertir bidones a litros.
- Se unifican las variantes del nombre por la cuenta CC2342. Se corrige visualmente Ba¤os a Baños y se normalizan espacios; el CSV de respaldo conserva el texto recibido.
- Los gráficos, indicadores, productos y documentos responden a mes, tipo y búsqueda. El CSV exportado contiene únicamente los registros filtrados.
- Los importes se calculan en centavos para evitar diferencias de redondeo.

## Actualizar
Esta es una instantánea del archivo recibido, sin conexión al Excel. Para actualizar el contenido, reemplaza el JSON del elemento `source-data` en index.html con registros del mismo esquema. `cents` es el importe en centavos; `date` usa AAAA-MM-DD. Conserva el número de documento como texto para mantener los ceros iniciales.
