# POLÍTICA DE PRIVACIDAD PRELIMINAR (VERSIÓN BETA)
## Wyfog — Gestión de Viajes Local-First y Seguridad de Datos

*Última actualización técnica: Noviembre de 2026*  
*Estado: Documento preliminar de trabajo sujeto a validación jurídica antes del lanzamiento público definitivo.*

---

### 1. INTRODUCCIÓN Y FILOSOFÍA DEL PROYECTO

Wyfog ha sido concebida bajo el principio de **privacidad por diseño** y una arquitectura **local-first** (prioridad local). Esto significa que la aplicación no requiere la creación de cuentas de usuario en la nube para funcionar, ni mantiene servidores centrales donde se almacenen perfiles, historiales de navegación, itinerarios o archivos privados de los viajeros.

Sin embargo, para prestar funcionalidades como la visualización cartográfica, la búsqueda de puntos de interés, la previsión meteorológica o la actualización de tipos de cambio, Wyfog se comunica puntualmente con proveedores de servicios en red.

Esta política detalla de manera transparente qué datos se procesan en el dispositivo, cuáles se transmiten a servicios externos y qué medidas de seguridad protegen tu información.

---

### 2. RESPONSABLE DEL TRATAMIENTO Y CONTACTO

> [!IMPORTANT]
> **Datos legales y titularidad:**  
> - **Titular/Responsable:** JUDMAV  
> - **N.I.F. / Identificación fiscal:** [En trámite de formalización antes de publicación comercial]  
> - **Domicilio o sede:** España  
> - **Correo electrónico de soporte y privacidad:** soporte@wyfog.app  
> - **Delegado de Protección de Datos (DPO):** No aplicable en fase beta al no realizarse tratamiento a gran escala en servidores propios.

---

### 3. ARQUITECTURA DE DATOS: LOCAL VS. REMOTO

A continuación se desglosa el tratamiento de la información diferenciando estrictamente lo que permanece en tu dispositivo y lo que se comunica al exterior:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   DISPOSITIVO DEL USUARIO (LOCAL)                      │
│                                                                        │
│  Base de datos Isar:                                                   │
│   • Viajes, Fechas, Presupuestos, Notas de itinerario                  │
│   • Actividades y Planes A/B                                           │
│   • Lugares guardados y Contactos de emergencia                        │
│   • Gastos, Divisas y Balances compartidos                             │
│   • Lista de equipaje y Curiosidades culturales                        │
│                                                                        │
│  Bóveda Cifrada (AES-256-GCM / CBC):                                   │
│   • Pasaportes, Visados, Billetes y Reservas                           │
│   • Clave maestra protegida en hardware (Android Keystore / Win Cred)  │
│   • Acceso biométrico nativo estricto o PIN propio de 6 dígitos        │
│                                                                        │
│  Herramientas Locales y Sensores:                                      │
│   • Escáner de códigos QR local para importación de viajes             │
│   • Mapa mundial y Fog of War (GeoJSON local integrado)                │
│   • Alarmas exactas de actividades en segundo plano                    │
└──────────────────────────────────┬─────────────────────────────────────┘
                                   │
                     ¿Requiere conexión a Internet?
                                   │
                    ┌──────────────┴──────────────┐
                    ▼                             ▼
       PETICIONES EXTERNAS PUNTUALES     SERVIDORES DE WYFOG
       • Teselas: OpenStreetMap          • [NINGUNO]
       • Búsqueda: Nominatim             • Sin cuentas de usuario
       • Puntos cercanos: Overpass       • Sin telemetría / analítica
       • Tiempo: Open-Meteo              • Sin seguimiento publicitario
       • Divisas: Frankfurter API
```

#### 3.1. Datos almacenados estrictamente en el dispositivo local

Los siguientes elementos se gestionan mediante el motor de base de datos **Isar** y el sistema de archivos local de tu dispositivo:
- **Gestión de Viajes:** Nombres de destinos, fechas de salida y regreso, descripciones, notas sobre salud, requisitos de entrada, datos de seguro y teléfonos de emergencia introducidos manualmente.
- **Itinerarios y Actividades:** Títulos, descripciones de actividades, horas de inicio/fin, alternativas organizadas en grupos (Plan A y Plan B) y participantes.
- **Equipaje:** Artículos empacados, cantidades y categorías organizativas.
- **Gastos y Presupuestos:** Registros de costes, conceptos, categorías, pagadores y miembros con los que se divide un gasto.
- **Notas Rápidas y Curiosidades:** Anotaciones personales, colores seleccionados e información cultural guardada.
- **Diario de Recuerdos:** Fotografías personales, notas geolocalizadas y miniaturas comprimidas localmente.

#### 3.2. Datos transmitidos a servicios de terceros y justificación técnica

Wyfog **no posee servidores propios de recopilación de datos**. Sin embargo, para ciertas características de consulta, la aplicación realiza solicitudes HTTP directas a los siguientes proveedores externos:

| Servicio / Proveedor | URL / Endpoint consultado | Datos transmitidos | Finalidad técnica | ¿Funciona Offline? |
| :--- | :--- | :--- | :--- | :--- |
| **OpenStreetMap** | `tile.openstreetmap.org` | Coordenadas de tesela `{z}/{x}/{y}`, dirección IP, User-Agent técnico | Descarga de imágenes del mapa cartográfico base | Sí, si la zona fue descargada o visualizada previamente en caché. |
| **Nominatim (OSM)** | `nominatim.openstreetmap.org` | Términos de búsqueda de texto o coordenadas de sesgo, dirección IP | Localización de direcciones y puntos de interés geocodificados | No, requiere conexión activa. |
| **Overpass API** | `overpass-api.de` | Coordenadas aproximadas y radio de consulta (~3 km) | Búsqueda de restaurantes, alojamientos o museos cercanos | No, requiere conexión activa. |
| **Open-Meteo** | `api.open-meteo.com` | Latitud y longitud de la ubicación consultada, dirección IP | Previsión meteorológica puntual para el itinerario | No, requiere conexión (mantiene última consulta en caché temporal). |
| **Frankfurter API** | `api.frankfurter.app` | Código de divisa base (ej. `EUR`, `USD`), dirección IP | Tipos de cambio oficiales del Banco Central Europeo | Sí, utiliza tasas en caché o valores de respaldo estáticos pregrabados. |

---

### 4. BÓVEDA DOCUMENTAL, CIFRADO Y CREDENCIALES

Wyfog incorpora un módulo de **Bóveda Segura** para salvaguardar billetes, pólizas de seguro, pasaportes y visados:

1. **Algoritmo de Cifrado:** Los archivos binarios de documentos sensibles se almacenan en el disco local cifrados mediante **AES-256 en modos GCM y CBC** con vector de inicialización (IV) de 16 bytes pseudoaleatorio generado por documento.
2. **Custodia de la Clave Maestra:** La clave de cifrado de 256 bits se genera aleatoriamente en el dispositivo y se almacena en el contenedor seguro del sistema operativo:
   - En **Android:** `Android Keystore` a través de `flutter_secure_storage` (con respaldo por hardware TEE/StrongBox si el terminal lo soporta).
   - En **Windows:** Administrador de credenciales / DPAPI de Windows.
3. **Acceso Biométrico Nativo Estricto:** La verificación biométrica (`local_auth`) en Android está configurada con `biometricOnly: true`, evitando que el sistema operativo sustituya la autenticación con el PIN o patrón de bloqueo del teléfono.
4. **Protección del PIN de Wyfog:** Si el usuario decide utilizar PIN o como método de respaldo, se utiliza exclusivamente el PIN de 6 dígitos propio de la aplicación, derivado mediante **PBKDF2/SHA-256 con 100.000 iteraciones** y sal criptográfica de 16 bytes.
5. **Alcance Real del Cifrado y Estado de la Base de Datos Isar:** El cifrado criptográfico AES-256 se aplica de forma estricta y exclusiva al contenido binario de los documentos almacenados en la carpeta segura (`documentos_seguros/`). **La base de datos Isar no está cifrada a nivel de motor de almacenamiento**. Los metadatos de viajes, títulos, presupuestos, notas y actividades se almacenan en texto claro, amparados por el aislamiento (*sandbox*) y permisos de almacenamiento privado proporcionados por los sistemas operativos Android y Windows.

---

### 5. PERMISOS DEL DISPOSITIVO

Wyfog solicita únicamente los permisos estrictamente necesarios para sus funcionalidades. Puedes denegar o revocar estos permisos en los ajustes del sistema, asumiendo las limitaciones correspondientes:

#### En Android (`AndroidManifest.xml`)
- `INTERNET` y `ACCESS_NETWORK_STATE`: Necesario para descargar teselas de mapas, consultar el tiempo, buscar sitios o descargar modelos de idioma.
- `ACCESS_FINE_LOCATION` y `ACCESS_COARSE_LOCATION`: Opcional. Solicitado para obtener tu ubicación GPS real actual al calcular distancias hacia lugares/actividades, centrar el mapa en el Modo en Vivo y geolocalizar recuerdos. Wyfog no registra ni envía tu ubicación en segundo plano.
- `POST_NOTIFICATIONS`: Solicitado al inicio de la app para permitir la emisión de alertas y recordatorios de itinerario.
- `SCHEDULE_EXACT_ALARM` y `USE_EXACT_ALARM`: Permite programar alarmas exactas en el reloj del sistema de Android, garantizando que los avisos de actividades y transportes lleguen en el instante preciso sin verse bloqueados por el reposo del dispositivo (*Doze mode*).
- `RECEIVE_BOOT_COMPLETED` y `VIBRATE`: Permite reprogramar recordatorios al reiniciar el terminal y emitir respuesta háptica.
- `CAMERA`: Opcional. Solicitado únicamente cuando el usuario decide escanear un código QR para importar un viaje o tomar fotografías para recuerdos o documentos de perfil.
- `USE_BIOMETRIC` y `USE_FINGERPRINT`: Permite validar tu identidad mediante el sensor biométrico del dispositivo para abrir la Bóveda Segura.

#### En Windows
- Acceso al sistema de archivos local para guardar la base de datos de usuario en la carpeta de documentos de la aplicación (`AppData` / `Documents`) y la caché de mapas.
- Conectividad de red para consultas cartográficas y de divisas.
- Windows Hello (autenticación) si está habilitado en el sistema operativo.

---

### 6. TELEMETRÍA, ANALÍTICA Y PUBLICIDAD

- **Publicidad:** Wyfog **no incluye ningún SDK de publicidad**, ni banners comerciales, ni redes de anuncios.
- **Rastreo (Tracking):** Wyfog **no rastrea** tu actividad a través de aplicaciones ni vende tus datos a corredores de información (*data brokers*).
- **Analítica y Telemetría:** En la versión actual verificada en el código fuente, la aplicación **no cuenta con herramientas de telemetría o analítica de terceros** (como Google Analytics, Firebase Analytics, Sentry o Mixpanel).
- **Registros de depuración:** Los registros de error (`debugPrint`) se emiten únicamente a la consola del desarrollador durante fases de depuración local, sin transmitirse a ningún servidor remoto.

---

### 7. COPIAS DE SEGURIDAD, EXPORTACIÓN Y COMPARTICIÓN

1. **Compartir Viaje por QR:**
   - La función de compartir por QR genera una cadena compacta serializada (`trip:<base64-gzip>`) con información resumida de itinerario.
   - Esta transmisión se produce exclusivamente de pantalla a cámara de forma directa entre dos personas (Peer-to-Peer), sin intermediarios en red.
   - **Garantía de Privacidad:** Los documentos de la Bóveda Segura **nunca** se incluyen en las cadenas de código QR.
2. **Exportación de Viaje (.trip):**
   - Genera un archivo ZIP local con las actividades y datos del viaje.
   - Los documentos sensibles y contraseñas de la bóveda quedan **estrictamente excluidos** de este archivo para evitar fugas accidentales al compartirlo.
3. **Copia de Seguridad Completa (.wyfogbackup):**
   - Diseñada para migración de datos o resguardo integral. Incluye la base de datos Isar y los archivos multimedia empaquetados en un archivo comprimido.
   - **Elección Flexible de Respaldo:** El usuario puede elegir libremente crear copias con PIN o sin PIN.
   - **Advertencia de Documentos Sensibles:** Si la base de datos contiene documentos confidenciales en la Bóveda Segura y el usuario selecciona crear una copia sin PIN, Wyfog muestra una ventana de advertencia de seguridad explícita para que el usuario confirme de forma consciente e informada si desea proceder sin protección o asignar un PIN.
   - **Restauración Segura con Combinación de Datos:** Durante la restauración, el usuario puede sustituir la base de datos o combinarla con los viajes existentes, previniendo colisiones de identificadores y garantizando la integridad de los datos.
   - El archivo de respaldo se guarda donde el usuario decida (almacenamiento local o compartición directa). El usuario es el único custodio de su copia.

---

### 8. CONSERVACIÓN Y ELIMINACIÓN DE DATOS

Puesto que todos los datos residen en el dispositivo del usuario:
- **Eliminación manual:** Puedes borrar cualquier viaje, gasto, actividad, recuerdo o documento individual en cualquier momento desde la interfaz. Al eliminar un documento seguro, el archivo `.enc` en disco se destruye físicamente de forma inmediata.
- **Eliminación total:** Puedes limpiar la caché cartográfica desde los ajustes de la aplicación, o desinstalar Wyfog y borrar sus datos locales a través de los ajustes del sistema operativo para erradicar por completo cualquier información almacenada.
- **Plazos de conservación en servidores:** No aplica para Wyfog, al no disponer de servidores centrales de almacenamiento de usuarios. Respecto a proveedores externos (OpenStreetMap, Nominatim, Overpass, Open-Meteo, Frankfurter), estos procesan las peticiones en sus respectivos servidores con registros técnicos habituales de servidor web (dirección IP y User-Agent) de acuerdo con sus propias políticas de retención de registros de infraestructura.

---

### 9. DERECHOS DE LOS USUARIOS (RGPD / DERECHOS ARCO)

Bajo normativas como el Reglamento General de Protección de Datos (RGPD) de la Unión Europea:
- **Acceso, Rectificación y Portabilidad:** Al residir la información en tu poder, puedes acceder a todos tus datos, editarlos o exportarlos íntegramente mediante las funciones nativas de exportación (.trip, .wyfogbackup, PDF, ICS).
- **Supresión ("Derecho al olvido"):** Tienes el control total para eliminar cualquier dato o la base de datos entera sin requerir autorización ni trámite previo con los desarrolladores.
- **Contacto para dudas de privacidad:** Dirígete al buzón indicado en el apartado 2 (`soporte@wyfog.app`).

---

### 10. MODIFICACIONES DE ESTA POLÍTICA

Wyfog continúa evolucionando. En caso de que futuras versiones incorporen nuevas características de sincronización voluntaria en la nube, copias cifradas remotas o nuevos proveedores, esta política se actualizará con carácter previo indicando los cambios en los documentos del repositorio público y en las notas de la versión.
