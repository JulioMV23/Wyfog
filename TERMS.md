# TÉRMINOS Y CONDICIONES DE USO PRELIMINARES (FASE BETA)
## Wyfog — Asistente de Viajes Personal

*Última actualización: Noviembre de 2026*  
*Estado: Versión preliminar de evaluación para pruebas de software beta.*

---

### 1. DESCRIPCIÓN GENERAL DEL SERVICIO

Wyfog es una aplicación de software para dispositivos móviles (Android) y de escritorio (Windows) diseñada como un asistente organizativo de viajes. Su propósito es ayudar al usuario a planificar itinerarios, archivar documentos de viaje de forma local, supervisar presupuestos y gastos, gestionar listas de equipaje y guardar recuerdos fotográficos o culturales bajo un modelo prioritariamente local (*local-first*).

El acceso, descarga, instalación y uso de la versión beta de Wyfog implica la aceptación de los presentes términos preliminares.

---

### 2. NATURALEZA EXPERIMENTAL Y ESTADO BETA

> [!WARNING]
> Wyfog se encuentra actualmente en **fase de pruebas beta (versión experimental)**.
> - La aplicación puede experimentar interrupciones imprevistas, fallos de funcionamiento (*bugs*), incompatibilidades con versiones específicas de sistemas operativos o pérdida de datos locales durante actualizaciones de esquema.
> - La arquitectura, las pantallas, los formatos de archivo y las características están sujetos a modificaciones, mejoras o sustitución sin previo aviso.
> - El software se ofrece para su prueba y evaluación personal, no debiendo utilizarse como único medio crítico o irreemplazable de organización en viajes de alto riesgo o sin copias de resguardo.

---

### 3. RESPONSABILIDAD DEL USUARIO Y VERIFICACIÓN DE INFORMACIÓN

Wyfog es una herramienta de asistencia y apoyo; **no es una agencia de viajes, ni una aerolínea, ni una autoridad consular ni un servicio oficial de emergencias**.

El usuario reconoce y acepta de forma expresa que es su responsabilidad exclusiva:
1. **Comprobar Documentación y Requisitos:** Verificar directamente ante embajadas, consulados y autoridades de transporte la validez de visados, pasaportes, requisitos sanitarios, normativas de aduana y coberturas de seguros médicos.
2. **Confirmar Horarios y Reservas:** Cotejar los horarios de salida de vuelos, trenes, autobuses, excursiones o reservas hoteleras con las fuentes oficiales y tarjetas de embarque proporcionadas por los operadores. Wyfog no actualiza en tiempo real retrasos de tráfico aéreo o cancelaciones salvo consulta manual de servicios de terceros si estuviesen disponibles.
3. **Custodia de Copias Originales y Respaldos:** Mantener copias de seguridad periódicas de sus datos (mediante la función de exportación `.wyfogbackup` o copias físicas/digitales externas). Wyfog no se responsabiliza de la pérdida de información debida a averías del terminal, borrado accidental o desinstalación de la app.
4. **Notificaciones y Alarmas:** Wyfog utiliza los servicios de alarmas exactas del sistema (`USE_EXACT_ALARM`) para emitir avisos de actividades y transportes. Sin embargo, factores ajenos a la aplicación (modos de ahorro extremo de energía del fabricante del dispositivo, apagado accidental o batería agotada) pueden impedir la entrega oportuna de un aviso. El usuario debe mantener sus métodos habituales de alarma para eventos críticos.
5. **Navegación y Orientación:** La cartografía mostrada en Wyfog se basa en fuentes comunitarias de OpenStreetMap. **Wyfog no es un sistema de navegación para emergencias, navegación marítima, montañismo extremo ni sustituto de las indicaciones oficiales de tráfico**. El usuario debe atender siempre a la señalización física real y a las directrices de las autoridades locales.

---

### 4. LIMITACIONES DE MAPAS Y SERVICIOS EXTERNOS

Wyfog integra datos cartográficos, meteorológicos y tipos de cambio procedentes de fuentes y proveedores externos:
- **Mapas y Lugares (OpenStreetMap, Nominatim, Overpass):** Los datos pueden contener imprecisiones, aperturas o cierres de establecimientos no actualizados o límites territoriales aproximados. Wyfog no garantiza la exactitud absoluta ni la disponibilidad ininterrumpida de los servidores de descarga de teselas cartográficas.
- **Previsión Meteorológica (Open-Meteo):** Los datos meteorológicos constituyen predicciones numéricas que pueden variar respecto a las condiciones atmosféricas reales locales.
- **Conversión de Divisas (Frankfurter / BCE):** Los tipos de cambio se obtienen como referencia informativa estándar y no representan ofertas contractuales de entidades bancarias o casas de cambio.

---

### 5. SEGURIDAD Y CUSTODIA DE LA BÓVEDA DOCUMENTAL

Wyfog implementa algoritmos de cifrado simétrico (AES-256-GCM / CBC) y control biométrico nativo estricto o mediante PIN propio de 6 dígitos para salvaguardar la Bóveda Segura en el dispositivo:
- El usuario es el único responsable de recordar su código PIN y mantener protegidas las credenciales de desbloqueo de su dispositivo.
- Si el usuario olvida su PIN y no tiene configurada la biometría o pierde el terminal sin una copia de seguridad protegida, los archivos cifrados en la bóveda no podrán ser recuperados por los desarrolladores de Wyfog, ya que estos carecen de claves de recuperación remotas o accesos secundarios (*backdoors*).
- Wyfog no garantiza invulnerabilidad absoluta frente a terminales con sistemas operativos manipulados (*root*, *jailbreak* o *malware* en el dispositivo).

---

### 6. PROPIEDAD INTELECTUAL Y USO PERMITIDO

1. **Titularidad:** Wyfog, sus marcas, logotipo, interfaz gráfica, esquemas de diseño y documentación técnica son propiedad exclusiva de sus desarrolladores, de conformidad con lo expuesto en el archivo `LICENSE`.
2. **Uso Autorizado:** Se concede una licencia limitada, personal, revocable, no exclusiva e intransferible para instalar y utilizar los binarios beta de Wyfog con fines privados y no comerciales de evaluación.
3. **Conductas Prohibidas:** Queda prohibido descompilar, realizar ingeniería inversa, distribuir copias modificadas no autorizadas, extraer masivamente datos protegidos o utilizar el software para actividades ilícitas.

---

### 7. LIMITACIÓN DE RESPONSABILIDAD

En la máxima medida permitida por la legislación aplicable:
- Wyfog se suministra "tal cual" (*as is*) y "según disponibilidad" (*as available*), sin garantías de ningún tipo, ya sean expresas o implícitas, sobre comerciabilidad, adecuación a un fin determinado o ausencia de errores.
- Los desarrolladores no serán responsables de daños directos, indirectos, incidentales, punitivos o consecuenciales derivados de la imposibilidad de uso de la aplicación, cancelaciones de viajes, pérdidas de vuelos, pérdida de datos o discrepancias en la cartografía durante el uso de la versión beta.
- Nada en estos términos pretende limitar derechos irrenunciables que asistan al usuario en su condición de consumidor de acuerdo con la legislación de su país de residencia.

---

### 8. REVISIÓN Y CANAL DE INCIDENCIAS

- **Contacto e informes de error:** Si detectas fallos técnicos, incoherencias de datos o problemas de rendimiento durante tus pruebas beta, te animamos a reportarlos a través del gestor de incidencias (*Issues*) del repositorio público en GitHub.
- **Evolución legal:** El presente texto es un borrador informativo para la fase de pruebas y será adaptado y formalizado jurídicamente con anterioridad a cualquier lanzamiento comercial o de producción final.

---

<div align="center">
  <p>© 2026 <strong>JUDMAV</strong> • Términos de Uso de Wyfog</p>
</div>
