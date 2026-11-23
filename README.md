# Fabricación

App para consultar en el taller lo que se fabrica y no es mueble de aglomerado: estructuras en madera, metal, prefabricados en concreto y piezas mixtas.

- App: https://handeress.github.io/Fabricaci-n/ (código público, sin datos).
- Datos: repo privado `handeress/Bitacora-datos`, carpeta `fabricacion/` (`indice.json` + `<id>/item.json`). Los escribe Claude; la app solo lee.
- Llave: la de la Bitácora (la toma sola en el mismo navegador) o pegada en Ajustes.

## Pestañas

Resumen (nota, revisiones ⚠, proceso con marcas), Piezas por material, Corte y compras (optimización de barras con 3 mm por corte, áreas de lámina, compras), Plano, 3D, Taller (identificar pieza dictando el largo) e Historial.

## item.json

`id, nombre, proyecto, proyectoNombre, tipo, estado ('por diseñar' | 'borrador' | 'diseñado' | 'en fabricación' | 'terminado'), nota, unidad:'mm', barras:{material: largo de barra}, piezas:[{codigo, nombre, material, largo, ancho, esp, cant, detalle?, revisar?}], materiales:[{nombre, cant, und, nota?}], herrajes, herrajesNota, procesos:[{texto}], planos:[{titulo, lo, hi}], visor, docs:[{titulo,url}], revisiones:[{texto,fecha}], historial:[{fecha,tipo,texto}], actualizado`.

Al cambiar un ítem desde el chat: se edita su item.json, se agrega una línea al historial (creado, cambio, corte, plano, evento, revision), se actualiza `actualizado` y la fila del índice.

## Versiones

- 1.0 (22/11/2026): torre del calentador, tapas de cajas, piezas de la fogata, closet en paneles de Fontanar y 4 ítems por diseñar.

- 1.2 (23-nov-2026): botón Instalar en el celular; atrás va de subpágina a la página inicial del elemento, luego al inicio y luego cierra la app.

- 1.3 (23-nov-2026): recuerda el elemento y la pestaña al recargar (12 h); el 3D guarda su vista (cámara, filtros, corte, separación, abierto) y se recarga solo si el celular lo borra al cambiar de app.
