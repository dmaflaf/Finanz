# FINANZ

Control de caja y cuentas del torneo, con acceso privado.

## Uso

Abre `index.html` en un navegador (o publícalo con GitHub Pages para usarlo desde el celular y la tablet).

La primera vez te pide crear una **clave de 6 dígitos**. Con esa clave los datos se cifran (AES-256 con PBKDF2) y se guardan solo en el navegador del dispositivo. Sin la clave no se pueden leer. Si la olvidas, la única salida es borrar los datos y empezar de nuevo, así que descarga respaldos.

- **Resumen:** ingresos, gastos, saldo, cobro de inscripciones y presupuesto previsto frente al real.
- **Caja:** cierre diario con tickets (del número, al número, devueltos), efectivo, transferencias, pago a 2 cobradores, transferencia a árbitros y gastos de caja. Calcula si el día cuadra y lleva el efectivo y el banco acumulados.
- **Equipos:** pagos de inscripción y garantía por equipo.
- **Movimientos:** ingresos y gastos manuales.
- **Configuración:** valores del torneo, cambio de clave, huella o rostro y respaldos.

## Seguridad

- La app se bloquea sola a los 3 minutos sin uso o si sales de ella más de 1 minuto.
- Tras 5 claves incorrectas hay una espera que va aumentando.
- Huella o rostro (opcional) funciona solo cuando la página se abre desde una dirección **https** (por ejemplo GitHub Pages) y el dispositivo lo permite.
- Los respaldos (.json y .csv) salen sin cifrar: guárdalos en un lugar privado.
- Los datos nunca se envían a GitHub ni a ningún servidor. Aun así, conviene que el repositorio sea **privado**.
