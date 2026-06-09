# Farmacia Escuela Venezuela — App de confirmación RRHH

Herramienta web para que los coordinadores de RRHH revisen y confirmen el estado de las Farmacias Escuela. El **administrador** controla los datos (lista de tiendas y estados) desde un Excel; los **coordinadores** solo registran acciones y comentarios.

## Archivos del repositorio

| Archivo | Para quién | Qué hace |
|---|---|---|
| `index.html` | Coordinadores | La app. Se abre en el navegador (celular o computador). |
| `base.xlsx` | **Administrador** | La base de datos editable. La app lee esta hoja al abrirse. |
| `README.md` | — | Este documento. |

> El Excel de análisis con todos los indicadores (`FarmaciaEscuela_VZLA_Estructurado.xlsx`) es aparte, para el trabajo interno del administrador. No hace falta subirlo al repo.

## Cómo se reparten los roles

- **Administrador (tú):** edita `base.xlsx` — agrega o quita tiendas y cambia la columna **ESTADO** (menú desplegable: Activa / Próximamente / A inactivar / Inactiva / No es FE). Al guardar y subir el archivo, la app muestra los datos nuevos para todos.
- **Coordinadores:** abren el enlace de la app. **Solo** pueden usar los botones de **Acción** (Confirmar / Activar / Inactivar) y escribir **Comentarios**. No pueden cambiar el estado ni la lista de tiendas: eso lo controlas tú desde el Excel.

## Publicar la app en GitHub (GitHub Pages)

1. Crea una cuenta en https://github.com y un repositorio nuevo (ej. `farmacia-escuela`), marcado como **Public**.
2. Sube los 3 archivos: `index.html`, `base.xlsx` y `README.md` (botón **Add file → Upload files**).
3. Ve a **Settings → Pages**.
4. En **Source** elige la rama `main` y la carpeta `/ (root)`. Guarda.
5. En 1–2 minutos GitHub te dará un enlace tipo:
   `https://TU-USUARIO.github.io/farmacia-escuela/`
6. Ese es el enlace que compartes con los coordinadores. Funciona en celular y computador.

## Cómo actualizar los datos (administrador)

1. Descarga `base.xlsx`, edítalo en Excel (cambia ESTADO o agrega tiendas) y guárdalo.
2. En GitHub: **Add file → Upload files**, sube el `base.xlsx` actualizado y confirma (**Commit changes**).
3. Listo: la próxima vez que alguien abra la app, verá los datos nuevos. El panel superior (Total, Activas, Próximamente, etc.) se recalcula solo.

## Cómo trabajan los coordinadores

1. Abren el enlace.
2. Filtran por su **Área** o buscan su **tienda**.
3. En cada tienda eligen **Confirmar**, **Activar** (justificando en Comentarios) o **Inactivar**, y dejan observaciones.
4. Sus respuestas se guardan automáticamente **en su propio navegador**.
5. Al terminar, pulsan **Exportar CSV** y te envían ese archivo.

## Importante sobre el guardado

GitHub Pages es un sitio “estático”: muestra la app pero **no guarda en un servidor central**. Por eso cada coordinador guarda su revisión en **su navegador** y te la manda con **Exportar CSV**; tú consolidas los CSV.

Si más adelante quieres que **todos editen una misma base centralizada** (sin exportar/enviar archivos), se puede conectar la app a una **Google Sheet** como backend. Es un paso adicional que se puede montar cuando lo necesites.

## Notas

- La app necesita internet la primera vez (carga las fuentes y la librería que lee el Excel).
- Debe abrirse desde el enlace de GitHub Pages (no haciendo doble clic al archivo local), para que pueda leer `base.xlsx`.
- Si `base.xlsx` no se puede leer, la app usa una copia de respaldo de los datos incluida en `index.html`.
