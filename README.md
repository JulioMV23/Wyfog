<p align="center">
  <img src="assets/wyfog-logo.png" alt="Logotipo de Wyfog" width="160" />
</p>

<h1 align="center">Wyfog</h1>

<p align="center">
  <strong>Asistente y gestor integral de viajes offline-first, seguro y accesible.</strong><br>
  Tus itinerarios, documentos, mapas, gastos y recuerdos siempre contigo, bajo tu propio control y sin dependencia obligatoria de la nube.
</p>

<p align="center">
  <em>Versión actual: v1.0.0+1 (Fase Beta)</em> • 
  <em>Plataformas: Android y Windows</em> •
  <em>Última actualización: Noviembre de 2026</em>
</p>

<p align="center">
  <a href="#-galería-visual-de-la-aplicación">📸 Ver todas las capturas (25)</a> •
  <a href="#-funcionalidades-verificadas-en-la-versión-actual">✨ Funcionalidades</a> •
  <a href="#-plataformas-disponibles-y-estado-beta">📱 Plataformas</a> •
  <a href="#-instalación-y-puesta-en-marcha">🚀 Instalación y Descargas</a> •
  <a href="BETA.md">🧪 Guía Beta</a> •
  <a href="https://tally.so/r/zEygb8">📝 Dar Feedback</a>
</p>

<div align="center">
  <table>
    <tr>
      <td align="center" width="72%">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="screenshots/oscuro_home_windows.webp" />
          <source media="(prefers-color-scheme: light)" srcset="screenshots/claro_home_windows.webp" />
          <img src="screenshots/oscuro_home_windows.webp" alt="Wyfog en Windows Desktop — Panel Principal y Modo en Vivo" width="100%" />
        </picture>
        <br />
        <sub><strong>Windows Desktop</strong> — Panel principal multi-panel y Modo en Vivo</sub>
      </td>
      <td align="center" width="28%">
        <picture>
          <source media="(prefers-color-scheme: dark)" srcset="screenshots/oscuro_home.webp" />
          <source media="(prefers-color-scheme: light)" srcset="screenshots/claro_home.webp" />
          <img src="screenshots/oscuro_home.webp" alt="Wyfog en Android — Inicio y Modo en Vivo" width="100%" />
        </picture>
        <br />
        <sub><strong>Android</strong> — Diseño ergonómico offline-first</sub>
      </td>
    </tr>
  </table>
</div>

---

## 📌 ¿Qué es Wyfog?

**Wyfog** es una aplicación de viaje diseñada para devolver la autonomía, la tranquilidad y la privacidad al viajero moderno. Frente a soluciones comerciales que requieren conexión constante a Internet, cuentas en servidores remotos o suscripciones invasivas, Wyfog adopta una arquitectura **local-first**: toda la información de tus viajes se guarda directamente en la memoria de tu dispositivo.

Tanto si estás explorando una ciudad sin roaming como si viajas en tren por zonas de montaña o necesitas consultar urgentemente tu pasaporte en el mostrador del aeropuerto, Wyfog te permite acceder de inmediato a tus itinerarios, reservas, billetes cifrados y presupuestos.

---

## 🧭 Filosofía y Principios de Diseño

1. **Local-First & Offline-First:** Los datos primarios se gestionan mediante una base de datos local embebida de alto rendimiento ([Isar](https://isar.dev)). No necesitas crearte una cuenta online ni iniciar sesión en ningún servidor para utilizar la aplicación.
2. **Privacidad Real por Diseño:** Sin publicidad, sin rastreo comercial y sin telemetría invasiva. Tus planes de viaje no se comparten con anunciantes ni corredores de datos.
3. **Seguridad Documental y Criptografía Robusta:** Los documentos sensibles (pasaportes, visados, pólizas de seguro) se cifran mediante algoritmos criptográficos robustos (**AES-256-GCM / CBC**) y se custodian bajo control biométrico nativo estricto o PIN propio de 6 dígitos reforzado con PBKDF2/SHA-256 (100.000 iteraciones).
4. **Notificaciones y Alarmas Exactas:** Sistema de avisos de itinerario configurado con permisos de alarma exacta (`USE_EXACT_ALARM` y `SCHEDULE_EXACT_ALARM`) para garantizar avisos puntuales de vuelos, transportes y reservas incluso con la pantalla apagada o en modo reposo (*Doze*).
5. **Accesibilidad Universal:** Interfaz adaptada con soporte para modo oscuro profundo de alto contraste, tipografía escalable y cumplimiento de las pautas WCAG 2.2 con objetivos táctiles ergonómicos de al menos 48–56 dp.

---

## 📸 Galería Visual de la Aplicación

Wyfog está diseñado de forma nativa con **Material 3** adaptado tanto para pantallas táctiles **Android** como para escritorio en **Windows**, con soporte completo para **Tema Claro** y **Tema Oscuro de alto contraste**.

<details open>
<summary><strong>☀️ Modo Claro — Android (7 capturas) y Windows (5 capturas)</strong></summary>

#### 📱 Android (Modo Claro)

<table align="center">
  <tr>
    <td align="center" width="25%">
      <img src="screenshots/claro_home.webp" alt="Android Modo Claro - Inicio y Modo en Vivo" width="190" /><br />
      <sub><strong>Inicio y Modo en Vivo</strong><br />Día actual y cuenta atrás</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/claro_itinerario.webp" alt="Android Modo Claro - Itinerario con Plan A y Plan B" width="190" /><br />
      <sub><strong>Itinerario (Plan A / B)</strong><br />Clima y viabilidad de traslados</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/claro_lugares.webp" alt="Android Modo Claro - Lugares de Interés" width="190" /><br />
      <sub><strong>Lugares de Interés</strong><br />Categorización y costes</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/claro_equipaje.webp" alt="Android Modo Claro - Equipaje Inteligente" width="190" /><br />
      <sub><strong>Equipaje Inteligente</strong><br />Generación por clima y conteo</sub>
    </td>
  </tr>
</table>

<table align="center">
  <tr>
    <td align="center" width="33%">
      <img src="screenshots/claro_emergencias.webp" alt="Android Modo Claro - Info y Emergencia" width="190" /><br />
      <sub><strong>Info &amp; Emergencia</strong><br />Consulado, salud y requisitos</sub>
    </td>
    <td align="center" width="33%">
      <img src="screenshots/claro_recuerdos.webp" alt="Android Modo Claro - Diario de Recuerdos" width="190" /><br />
      <sub><strong>Diario de Recuerdos</strong><br />Vista en cuadrícula de postales</sub>
    </td>
    <td align="center" width="33%">
      <img src="screenshots/claro_perfil.webp" alt="Android Modo Claro - Perfil de Viajero y Accesibilidad" width="190" /><br />
      <sub><strong>Perfil y Accesibilidad</strong><br />Pasaporte, inclusión e idioma</sub>
    </td>
  </tr>
</table>

#### 💻 Windows Desktop (Modo Claro)

<table align="center">
  <tr>
    <td align="center" width="33%">
      <img src="screenshots/claro_home_windows.webp" alt="Windows Modo Claro - Inicio" width="290" /><br />
      <sub><strong>Panel Principal</strong><br />Modo en Vivo y resumen de viajes</sub>
    </td>
    <td align="center" width="33%">
      <img src="screenshots/claro_itinerario_windows.webp" alt="Windows Modo Claro - Itinerario del Viaje" width="290" /><br />
      <sub><strong>Itinerario Desktop</strong><br />Días, Plan A/B y tiempos de traslado</sub>
    </td>
    <td align="center" width="33%">
      <img src="screenshots/claro_mapa_windows.webp" alt="Windows Modo Claro - Mapa del Viaje OpenStreetMap" width="290" /><br />
      <sub><strong>Mapa del Viaje</strong><br />Cartografía OpenStreetMap y pines</sub>
    </td>
  </tr>
</table>

<table align="center">
  <tr>
    <td align="center" width="50%">
      <img src="screenshots/claro_estadisticas_windows.webp" alt="Windows Modo Claro - Estadísticas del Viaje" width="420" /><br />
      <sub><strong>Estadísticas del Viaje</strong><br />Duración, gasto total y desglose por categorías</sub>
    </td>
    <td align="center" width="50%">
      <img src="screenshots/claro_recuerdos_windows.webp" alt="Windows Modo Claro - Diario de Recuerdos" width="420" /><br />
      <sub><strong>Diario de Recuerdos</strong><br />Colección fotográfica geolocalizada</sub>
    </td>
  </tr>
</table>

</details>

<details open>
<summary><strong>🌙 Modo Oscuro — Android (8 capturas) y Windows (5 capturas)</strong></summary>

#### 📱 Android (Modo Oscuro)

<table align="center">
  <tr>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_home.webp" alt="Android Modo Oscuro - Inicio y Modo en Vivo" width="190" /><br />
      <sub><strong>Inicio y Modo en Vivo</strong><br />Cuenta atrás en tiempo real</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_viaje.webp" alt="Android Modo Oscuro - Centro de Control del Viaje" width="190" /><br />
      <sub><strong>Vista del Viaje</strong><br />Planificación, Logística y Diario</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_itinerario.webp" alt="Android Modo Oscuro - Itinerario del Viaje" width="190" /><br />
      <sub><strong>Itinerario (Plan A / B)</strong><br />Actividades, clima y márgenes</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_gastos.webp" alt="Android Modo Oscuro - Gastos y Presupuesto" width="190" /><br />
      <sub><strong>Gastos y Presupuesto</strong><br />Alertas preventivas y grupo</sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_reservas.webp" alt="Android Modo Oscuro - Reservas y Billetes" width="190" /><br />
      <sub><strong>Reservas y Billetes</strong><br />Visor integrado y apertura externa</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_emergencias.webp" alt="Android Modo Oscuro - Info y Emergencia" width="190" /><br />
      <sub><strong>Info &amp; Emergencia</strong><br />Consulado, póliza y visados</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_recuerdos.webp" alt="Android Modo Oscuro - Visado de Recuerdo" width="190" /><br />
      <sub><strong>Visado de Recuerdo</strong><br />Postal detallada y descarga PNG</sub>
    </td>
    <td align="center" width="25%">
      <img src="screenshots/oscuro_perfil.webp" alt="Android Modo Oscuro - Perfil de Viajero" width="190" /><br />
      <sub><strong>Perfil de Viajero</strong><br />Ficha médica y accesibilidad</sub>
    </td>
  </tr>
</table>

#### 💻 Windows Desktop (Modo Oscuro)

<table align="center">
  <tr>
    <td align="center" width="33%">
      <img src="screenshots/oscuro_home_windows.webp" alt="Windows Modo Oscuro - Panel Principal" width="290" /><br />
      <sub><strong>Panel Principal</strong><br />Modo oscuro de alto contraste</sub>
    </td>
    <td align="center" width="33%">
      <img src="screenshots/oscuro_itinerario_windows.webp" alt="Windows Modo Oscuro - Itinerario Desktop" width="290" /><br />
      <sub><strong>Itinerario Desktop</strong><br />Agenda por días y contingencias</sub>
    </td>
    <td align="center" width="33%">
      <img src="screenshots/oscuro_mapa_windows.webp" alt="Windows Modo Oscuro - Mapa Nocturno" width="290" /><br />
      <sub><strong>Mapa Nocturno OSM</strong><br />Filtro de alto contraste oscuro</sub>
    </td>
  </tr>
</table>

<table align="center">
  <tr>
    <td align="center" width="50%">
      <img src="screenshots/oscuro_estadisticas_windows.webp" alt="Windows Modo Oscuro - Estadísticas del Viaje" width="420" /><br />
      <sub><strong>Estadísticas del Viaje</strong><br />Métricas, reservas y documentos</sub>
    </td>
    <td align="center" width="50%">
      <img src="screenshots/oscuro_recuerdos_windows.webp" alt="Windows Modo Oscuro - Diario de Recuerdos" width="420" /><br />
      <sub><strong>Diario de Recuerdos</strong><br />Postales en vista escritorio</sub>
    </td>
  </tr>
</table>

</details>

---

## ✨ Funcionalidades Verificadas en la Versión Actual

### 1. Gestión Integral de Viajes e Itinerarios
- **Organización Centralizada y Estado Automático:** Creación y edición completa de viajes con detección automática del estado (*En curso* si el viaje comienza hoy, *Planificado* o *Finalizado*), fotos de portada, acompañantes y presupuestos globales.
- **Contador en Pantalla de Inicio y Modo en Vivo ("Ahora"):** Cuando un viaje está en curso, la pantalla principal muestra tanto el día actual del viaje como una **cuenta atrás en tiempo real para la próxima actividad del itinerario**, complementada por el panel dinámico del Modo en Vivo.
- **Información Sanitaria y de Emergencia:** Secciones específicas para guardar teléfonos de emergencia locales, detalles consulares o de embajada, requisitos de visado y datos de pólizas de seguro.
- **Itinerarios Flexibles (Planes A y B):** Cada actividad permite asociar alternativas de grupo para reaccionar con agilidad ante imprevistos meteorológicos o cambios de horario sin desorganizar tu plan principal.
- **Recordatorios y Notificaciones Exactas:** Programación automática de alertas previas y de inicio en cada actividad o reserva sincronizada (`USE_EXACT_ALARM` y `SCHEDULE_EXACT_ALARM`), funcionando de forma silenciosa y fiable en segundo plano sin diálogos intrusivos al iniciar la app.

### 2. Cartografía, Ubicación GPS Real y Mapas Descargables
- **Ubicación Real en Todo Momento:** El buscador de direcciones y lugares calcula siempre los kilómetros reales desde tu **posición GPS actual** (`A X.X km de tu ubicación actual`) e incluye un botón directo para utilizar tu ubicación GPS al instante.
- **Mapas con OpenStreetMap:** Visualización fluida con `flutter_map` y teselas abiertas de OpenStreetMap, con filtro adaptado para modo oscuro y alto contraste.
- **Uso de Mapas Offline:** Wyfog almacena en una caché local persistente las teselas de las zonas que consultas y permite **descargar previamente zonas concretas** asociadas a los puntos de tu viaje (niveles de zoom 12 a 15) para utilizarlas en destino sin conexión.
- **Búsqueda de Puntos de Interés:** Búsqueda global y verificada de lugares mediante [Nominatim](https://nominatim.openstreetmap.org) y descubrimiento de restaurantes, alojamientos o museos cercanos mediante [Overpass API](https://overpass-api.de).
- **Mapa Mundial y Descubrimiento (*Fog of War*):** Mapa interactivo que procesa un recurso GeoJSON local para iluminar los países que has visitado según tus viajes registrados y calcular el porcentaje de mundo descubierto de forma 100% offline.

### 3. Listas de Equipaje Inteligentes
- **Organización por Categorías:** Clasificación de equipaje por ropa, calzado, aseo, electrónica, documentación o botiquín.
- **Conteo Coherente por Artículo y Cantidad:** Cada artículo añadido cuenta como una entrada única en el progreso de completado y en el PDF, mostrando claramente a su lado el número de unidades necesarias (por ejemplo, `x5`) sin distorsionar el porcentaje.
- **Generación Inteligente y Exportación PDF:** Creación automática de listas según el destino/clima, plantillas personalizables y exportación completa a PDF multipágina o apertura directa en visores externos.

### 4. Control de Presupuestos, Gastos Grupales y Conversor de Divisas
- **Registro Multidivisa y Conversor Interactivo:** Anotación de gastos en diferentes monedas y conversor de divisas integrado con importes rápidos, inversión de moneda y tasas oficiales del Banco Central Europeo ([Frankfurter API](https://api.frankfurter.app)) con respaldo offline automático.
- **Gastos en Grupo y Reembolsos Sincronizados:** División de gastos entre acompañantes y liquidación de deudas con un toque. Cuando un compañero te devuelve su parte (`Liquidación: Acompañante ➡️ Yo`), se registra en positivo (`+` en verde) y se descuenta automáticamente tanto del **Total Gastado** como del **Desglose y Límites por Categoría** correspondientes.
- **Alertas de Presupuesto:** Indicadores visuales al alcanzar el 85% o superar el límite asignado a cada categoría.
- **Exportación de Informes:** Generación de reportes financieros detallados en formato PDF.

### 5. Bóveda Segura de Documentos, Perfil de Viajero y Reservas
- **Cifrado Fuerte Local:** Los archivos adjuntos de billetes, pasaportes, contratos, seguros, visados y otros documentos (`Otro`) se cifran en disco con **AES-256-GCM / CBC** y respaldo seguro de claves.
- **Visor Amplio Integrado y "Abrir con otra app":** Tanto en la Bóveda de Documentos como en Reservas puedes previsualizar tus PDFs e imágenes a pantalla amplia o abrirlos directamente con cualquier aplicación externa de tu dispositivo Android (`FileProvider`) o Windows.
- **Reservas con Sincronización Opcional de Día y Hora:** Al registrar una reserva (vuelo, tren, autobús, hotel, restaurante, entrada, excursión u otro/a), puedes elegir si deseas sincronizarla con el itinerario seleccionando su **día y hora exactos** (o guardarla sin fecha de itinerario) y vincular su importe con tus gastos.
- **Perfil del Viajero Persistente y Visual:** Guardado persistente de tus datos de viajero y visualización directa de las fotografías de tu DNI/Pasaporte sin exponer bloques innecesarios de texto sensible.
- **Autenticación Biométrica Estricta:** Desbloqueo directo mediante huella digital o reconocimiento facial nativo, o mediante tu PIN propio de 6 dígitos en Wyfog derivado con 100.000 iteraciones de PBKDF2/SHA-256.
- **Aislamiento en Compartición:** Al compartir o exportar un viaje individual (`.trip` o QR), los documentos de la bóveda quedan **estrictamente excluidos** para prevenir cualquier filtración de datos sensibles.

### 6. Copias de Seguridad y Restauración Inteligente
- **Formato `.wyfogbackup`:** Resguardo integral en archivo comprimido que incluye la base de datos Isar y archivos multimedia.
- **Respaldos Flexibles con Aviso de Seguridad:** Permite generar copias con PIN (clave derivada PBKDF2/SHA-256 con HMAC de verificación) o sin PIN según preferencia del usuario. Si la copia contiene documentos confidenciales y se solicita sin PIN, el sistema advierte mediante un diálogo de confirmación informada.
- **Restauración sin Pérdida de Datos:** Soporte para restaurar reemplazando la base de datos o **combinando con viajes existentes**, resolviendo colisiones de entidades duplicadas.

### 7. Herramientas Auxiliares y Experiencias
- **Compartición Peer-to-Peer por QR y Archivo `.trip`:** Generación de códigos QR compactos al exportar un viaje y escáner QR integrado en la pantalla de inicio para importar viajes entre dispositivos sin intermediarios ni conexión a Internet.
- **Diario de Recuerdos con Descarga PNG Transparente:** Registro de recuerdos con vista en cuadrícula de postales y vista de lista con miniatura de portada, geolocalización limpia por nombre de localidad (`📍 Ciudad`), ventana de lectura en detalle y **descarga directa de la postal en formato PNG con fondo transparente en la Galería del dispositivo**.
- **Cuaderno de Viaje y Retos:** Notas rápidas, recomendaciones, cultura/datos locales y desafíos culturales y gastronómicos para enriquecer la inmersión en el destino.

---

## 📱 Plataformas Disponibles y Estado Beta

> [!WARNING]
> **Wyfog se encuentra actualmente en fase de pruebas beta.**
> Recomendamos mantener copias de respaldo de tus datos importantes mediante la opción integrada en Ajustes. Para más detalles, consulta [BETA.md](BETA.md).

| Plataforma | Estado | Requisitos Mínimos |
| :--- | :--- | :--- |
| **Android** | Beta Activa | Android 8.0 (Oreo) o superior (API 26+). |
| **Windows** | Beta Activa | Windows 10 (64 bits, versión 1809+) o Windows 11. |

*Nota sobre otras plataformas:* Las versiones para iOS y la aplicación web interactiva se encuentran fuera del alcance de esta fase inicial y no están disponibles públicamente. La carpeta `web/` de este proyecto corresponde exclusivamente al portal estático informativo de presentación.

---

## 🚀 Instalación y Puesta en Marcha

Las versiones compiladas para evaluación se publican en el apartado de **Releases** del repositorio oficial:

- **Instalación en Android (APK):**
  1. Descarga el paquete `Wyfog-beta-v1.0.0-android.apk` desde las *Releases* oficiales de GitHub.
  2. Abre el archivo en tu dispositivo y concede el permiso para instalar aplicaciones desde el navegador o explorador si te lo solicita.
  3. Al iniciar la aplicación por primera vez, el asistente de bienvenida solicitará los permisos de notificaciones (para recordatorios de itinerario) y ubicación (para el centrado del mapa).
  4. Configura tu PIN de seguridad de 6 dígitos cuando accedas por primera vez a la Bóveda Segura.
- **Instalación en Windows (Escritorio):**
  1. Descarga el instalador `Wyfog-beta-v1.0.0-windows.exe` desde las *Releases* oficiales de GitHub.
  2. Ejecuta el archivo descargado. Si Windows SmartScreen muestra un aviso preventivo por tratarse de un ejecutable reciente, pulsa en *"Más información"* y luego en *"Ejecutar de todas formas"*.
  3. Sigue los pasos del asistente de instalación y abre Wyfog desde el menú Inicio o el acceso directo del escritorio.

---

## 🔒 Privacidad y Transparencia Técnica

Wyfog no almacena tus datos en servidores corporativos propios. Todas tus notas, itinerarios y documentos residen exclusivamente en tu terminal.

Para funciones como descarga de mapas, previsión del tiempo o conversión de moneda, la aplicación se comunica directamente con servicios externos abiertos (OpenStreetMap, Open-Meteo, Frankfurter, Overpass, Nominatim).

Para conocer en detalle cada permiso solicitado, el alcance del cifrado y los servicios de red utilizados, consulta nuestra [Política de Privacidad Preliminar](PRIVACY.md).

---

## 🛠️ Procedimiento para Comunicar Errores y Sugerencias

Si durante tus pruebas beta encuentras un fallo de software (*bug*), un problema de diseño o una propuesta de mejora, dispones de dos vías:

1. **Formulario Rápido de Feedback (Recomendado, sin registro):** Envíanos tus opiniones o fallos en menos de 1 minuto a través del [**Formulario de Feedback de Wyfog (Tally)**](https://tally.so/r/zEygb8).
2. **Seguimiento Técnico en GitHub:**
   - Revisa las incidencias abiertas en la pestaña de [**Issues**](https://github.com/JulioMV23/Wyfog/issues) de GitHub para comprobar si ya ha sido notificado.
   - Abre un nuevo *Issue* utilizando las plantillas disponibles (`Reporte de Error` o `Solicitud de Mejora`), especificando tu dispositivo, versión de sistema operativo y los pasos exactos para reproducir el comportamiento.
3. **Importante:** Jamás adjuntes capturas de pantalla que contengan datos personales reales, pasaportes o billetes privados.
4. Consulta todos los detalles del proceso en [BETA.md](BETA.md).

---

## 🗺️ Hoja de Ruta Prudente

### Funcionalidades Actuales (Verificadas)
- [x] Motor de base de datos local Isar offline-first.
- [x] Onboarding limpio sin datos de prueba precargados.
- [x] Itinerarios por días con grupos de contingencia (Plan A, Plan B).
- [x] Dashboard dinámico en Modo en Vivo.
- [x] Bóveda documental cifrada con AES-256-GCM / CBC y acceso biométrico/PIN estricto.
- [x] Notificaciones y alarmas exactas en segundo plano (`USE_EXACT_ALARM`).
- [x] Mapas con OpenStreetMap y descarga de teselas por zonas de viaje.
- [x] Intercambio P2P de viajes mediante códigos QR y archivos `.trip`.
- [x] Sistema de copias de seguridad completas `.wyfogbackup` (con/sin PIN, detección de documentos sensibles y combinación de duplicados).
- [x] Solicitud automática y transparente de permisos al iniciar en Android.
- [x] Mapa mundial con Fog of War y GeoJSON integrado.
- [x] Control de presupuestos, conversor multidivisa y gastos grupales con reembolsos sincronizados por categoría.
- [x] Exportación a PDF (informes de viaje, gastos y lista de equipaje), descarga directa de postales de recuerdos en PNG transparente en galería y calendario ICS.

### Mejoras en Exploración para Versiones Posteriores
- [x] Empaquetado formal de distribución para Windows (instalador Inno Setup `.exe`).
- [ ] Sincronización voluntaria cifrada de extremo a extremo (E2EE) entre dispositivos del mismo usuario.
- [ ] Evaluación de viabilidad técnica para la versión de iOS y ecosistema Apple.
- [ ] Soporte para mapas vectoriales compactos MapLibre / PMTiles para reducir el tamaño de almacenamiento en disco.

---

## 📄 Licencia y Términos Legales

- **Propiedad y Derechos:** Wyfog es un software propietario. El código fuente de la aplicación se mantiene bajo desarrollo privado y este repositorio está destinado a su presentación, documentación y seguimiento de versiones beta. Consulta [LICENSE](LICENSE) para más detalles.
- **Términos de Uso:** El uso de las versiones de prueba beta se rige por los [Términos y Condiciones Preliminares](TERMS.md).
- **Atribución de Terceros:** Agradecemos profundamente a la comunidad de OpenStreetMap, al equipo de Flutter y a los mantenedores de paquetes de código abierto por sus invaluables contribuciones al ecosistema tecnológico.

---

<div align="center">
  <p>Desarrollado por <strong>JUDMAV</strong> • © 2026 JUDMAV. Todos los derechos reservados.</p>
  <p><em>Wyfog es una marca y software de la organización JUDMAV. La documentación de este repositorio se ofrece para información y soporte de la versión beta.</em></p>
</div>
