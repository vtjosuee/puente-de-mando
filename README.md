# Puente de Mando

Panel personal de tareas, agenda y dinero. Una sola página HTML, sin dependencias, sin proceso de compilación y sin servidor.

**Probarlo:** https://vtjosuee.github.io/puente-de-mando/

> **Sobre los datos: los tuyos son tuyos y los míos son míos.**
>
> La aplicación no tiene servidor ni base de datos. Todo lo que escribes se guarda en el `localStorage` **de tu propio navegador**. Si abres el enlace de arriba, verás el panel **vacío**, esperando tus datos — no los de nadie más.
>
> La sincronización entre tus dispositivos es opcional y usa **un gist privado de tu propia cuenta de GitHub**, con un token que introduces tú y que no sale de tu equipo.

---

## Qué hace

| Sección | Contenido |
|---|---|
| **Hoy** | Tareas y rutinas del día, con prioridad, área, estimación y cronómetro. Vista de jornada donde las tareas que se solapan se reparten en columnas en lugar de taparse. |
| **Agenda** | Calendario mensual y semanal. Importa y exporta ficheros `.ics`, así que entra y sale de cualquier calendario estándar. |
| **Dinero** | Reparto del ingreso por sobres, gastos fijos, puntuales y a plazos. Los gastos programados se descuentan solos al llegar su fecha. |
| **Balance** | Resumen por semana, mes y año. |
| **Ajustes** | Copias de seguridad, importación y exportación, y la sincronización opcional. |

---

## Dónde viven los datos

Esto es lo que conviene entender antes de usarlo:

**Por defecto, los datos no salen de tu navegador.** Se guardan en `localStorage` bajo claves con prefijo `pdm.`. Eso significa:

- Nadie los ve, ni siquiera yo.
- Son **por dispositivo y por navegador**: el móvil y el ordenador llevan cuentas separadas mientras no actives la sincronización.
- Si borras los datos del navegador o usas el modo privado, desaparecen. Por eso hay exportación de copias de seguridad en *Ajustes*.

**Si activas la sincronización**, los datos viajan además a un **gist privado de tu cuenta de GitHub**:

- El gist es privado; solo lo ve quien entre con tu cuenta.
- El token que introduces se guarda **solo en tu dispositivo**, nunca se envía a ningún sitio que no sea la API de GitHub.
- El token necesita **únicamente el permiso `gist`**. No le des acceso a tus repositorios: no le hace falta y no lo usa.

Si vas a usar esta aplicación, crea **tu propio token**. No hay ninguna cuenta compartida ni ningún servidor común.

---

## Instalarlo

No hay instalación. Se abre el enlace en el navegador.

Es una **aplicación web instalable**: incluye manifiesto y *service worker*, así que desde el móvil se puede añadir a la pantalla de inicio y abrir como una aplicación más, también sin conexión.

Para usarlo en local basta con abrir `index.html` en un navegador. Eso es todo el procedimiento.

---

## Cómo está hecho

Un único `index.html` de unos 120 KB, con todo dentro: estructura, estilos y lógica. Sin frameworks, sin dependencias externas, sin paso de compilación.

Que sea un solo fichero no es una limitación autoimpuesta por deporte, sino lo que hace que el proyecto siga funcionando dentro de dos años: no hay dependencias que se queden obsoletas ni cadena de compilación que se rompa. Se abre y funciona.

Los únicos ficheros adicionales son los de la aplicación instalable:

```
index.html              la aplicación entera
manifest.webmanifest    para poder instalarla en el móvil
sw.js                   service worker, para que funcione sin conexión
icon-180/192/512.png    iconos de la pantalla de inicio
```

---

## Licencia

Proyecto personal. Si algo te sirve, cógelo.
