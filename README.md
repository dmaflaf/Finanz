# FINANZ

Control de caja y cuentas del torneo, con acceso privado.

## Uso

Abre `index.html` en un navegador (o publícalo con GitHub Pages para usarlo desde el celular y la tablet).

La primera vez te pide crear una **clave de 6 dígitos**. Los datos se cifran con AES-256 usando una llave aleatoria, y esa llave queda protegida por tu clave en cada dispositivo. Si olvidas la clave de un dispositivo, la única salida es borrar sus datos y volver a vincularlo (o empezar de nuevo si no usas la nube), así que descarga respaldos.

- **Resumen:** ingresos, gastos, saldo, cobro de inscripciones y presupuesto previsto frente al real.
- **Caja:** cierre diario con tickets (del número, al número, devueltos), efectivo, transferencias, pago a 2 cobradores, transferencia a árbitros y gastos de caja. Calcula si el día cuadra y lleva el efectivo y el banco acumulados. Incluye un conteo de billetes y monedas (arqueo) que se compara con el efectivo esperado: fondo inicial + efectivo recibido − cobradores y gastos.
- **Equipos:** pagos de inscripción y garantía por equipo.
- **Movimientos:** ingresos y gastos manuales.
- **Configuración:** valores del torneo, cambio de clave, huella o rostro, nube y respaldos.

## Nube: mismos datos en todos tus dispositivos

Los datos se guardan cifrados en un **gist secreto de tu GitHub**. GitHub solo ve texto cifrado.

1. En Configuración, «Nube», pulsa **Crear token en GitHub**. Se abre una página con el permiso `gist` ya marcado. Pulsa «Generate token» y copia el token (empieza con `ghp_`). Ese token solo da acceso a tus gists, no a tus repositorios.
2. Pégalo en la app y pulsa **Conectar**.
3. Para otro dispositivo: en el primero pulsa **Código de vinculación**, cópialo, y en el nuevo elige «Ya uso FINANZ en otro dispositivo», pega el código y crea la clave de ese equipo.

Los cambios se suben solos y se bajan al abrir la app. Si dos dispositivos editan sin verse, la app te pregunta qué datos conservar. Si el token vence, desconecta y vuelve a conectar con uno nuevo: la app encuentra tu gist y retoma los datos. El código de vinculación es como una contraseña: no lo compartas y guárdalo en un lugar privado, porque sin él (y sin ningún dispositivo vinculado) los datos de la nube no se pueden recuperar.

## Seguridad

- La app se bloquea sola a los 3 minutos sin uso o si sales de ella más de 1 minuto.
- Tras 5 claves incorrectas hay una espera que va aumentando.
- Huella o rostro (opcional) funciona solo cuando la página se abre desde una dirección **https** (por ejemplo GitHub Pages) y el dispositivo lo permite.
- Los respaldos (.json y .csv) salen sin cifrar: guárdalos en un lugar privado.
- Los datos nunca se envían a GitHub. Con la nube conectada solo viajan cifrados a un gist secreto de tu cuenta.
- Aun así, conviene que el repositorio sea **privado**.
