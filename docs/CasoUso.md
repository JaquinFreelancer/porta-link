# 📋 Casos de Uso - Plataforma de Portafolios Profesionales

> **Comentarios:**  
> - Estos casos de uso cubren todas las funcionalidades principales de la plataforma de portafolios y búsqueda de talento.
> - Se especifican los actores, escenarios principales y alternativos, y restricciones de seguridad.
> - Roles: `PROFESSIONAL`, `RECRUITER`, `COMPANY`, `ADMIN` (usuarios autenticados), `Visitante` (no autenticado).
> - Incluye validaciones, networking profesional, mensajería y análisis de rendimiento.

---

## Caso de Uso: Registro y Onboarding de Profesional

**Actor Principal:** Visitante  
**Escenario Principal:**  
1. El visitante accede a la página de registro desde el landing.
2. Selecciona el tipo de cuenta "Profesional" y completa datos básicos.
3. Proporciona información profesional (título, ubicación, área de especialización).
4. Acepta términos y condiciones, selecciona configuración de privacidad inicial.
5. El sistema crea la cuenta y envía email de verificación.
6. Al verificar email, accede al flujo de onboarding guiado.
7. Completa wizard: habilidades principales, experiencia clave, foto de perfil.
8. El sistema genera URL personalizada (@username) y activa el perfil.

**Escenarios Alternativos:**  
- Si el email ya existe, ofrece opción de login o recuperación.
- Puede saltarse pasos del onboarding y completarlos después.
- Puede importar información básica desde LinkedIn/GitHub.
- Registro con Google/GitHub para acelerar el proceso.

**Restricciones:**  
- Username único y validado en tiempo real.
- Verificación de email obligatoria para activar cuenta.
- Perfil mínimo requerido para aparecer en búsquedas públicas.

---

## Caso de Uso: Creación y Gestión de Proyecto en Portafolio

**Actor Principal:** PROFESSIONAL  
**Escenario Principal:**  
1. El profesional accede a su sección de portafolio desde el dashboard.
2. Selecciona "Crear nuevo proyecto" y completa información básica.
3. Añade descripción detallada, desafío resuelto y tecnologías utilizadas.
4. Sube imágenes del proyecto, establece imagen principal.
5. Configura enlaces (demo en vivo, repositorio, caso de estudio).
6. Selecciona habilidades relacionadas del catálogo del sistema.
7. Define visibilidad (público, privado, solo para conectados).
8. Guarda como borrador o publica inmediatamente.
9. El proyecto aparece en su portafolio y en búsquedas públicas.

**Escenarios Alternativos:**  
- Puede clonar proyecto existente como plantilla.
- Puede colaborar con otros profesionales en proyectos de equipo.
- Puede programar publicación para fecha específica.
- Puede crear versiones del proyecto para diferentes audiencias.

**Restricciones:**  
- Límite de proyectos según plan (gratuito vs premium).
- Validación de tipos de archivo y tamaños máximos.
- Moderación automática de contenido inapropiado.
- SEO optimizado con slug único generado automáticamente.

---

## Caso de Uso: Búsqueda Avanzada de Talento por Reclutador

**Actor Principal:** RECRUITER  
**Escenario Principal:**  
1. El reclutador accede al módulo de búsqueda avanzada.
2. Define criterios específicos: habilidades técnicas, años de experiencia, ubicación.
3. Aplica filtros adicionales: disponibilidad, salario esperado, trabajo remoto.
4. Ejecuta búsqueda y ve resultados ordenados por relevancia.
5. Revisa perfiles en vista de tarjetas con información clave.
6. Accede a perfiles completos de candidatos interesantes.
7. Guarda búsqueda con nombre personalizado para uso futuro.
8. Exporta lista de candidatos o los añade a proyecto de reclutamiento.
9. Configura alertas para recibir nuevos candidatos que coincidan.

**Escenarios Alternativos:**  
- Puede buscar por palabras clave en proyectos específicos.
- Puede filtrar por educación, certificaciones o empresas anteriores.
- Puede usar búsqueda booleana avanzada para criterios complejos.
- Puede ver candidatos similares a un perfil específico (recomendaciones).

**Restricciones:**  
- Acceso limitado según plan de suscripción de la empresa.
- Respeta configuraciones de privacidad de los profesionales.
- Rate limiting para prevenir scraping masivo.
- Log de todas las búsquedas para analytics y mejoras.

---

## Caso de Uso: Mensajería y Networking Profesional

**Actor Principal:** RECRUITER o COMPANY  
**Escenario Principal:**  
1. La empresa encuentra un profesional interesante en el directorio.
2. Accede al perfil público y selecciona "Enviar mensaje".
3. Completa formulario de contacto con asunto y mensaje personalizado.
4. Puede mencionar proyecto específico o oportunidad laboral.
5. El sistema valida que no sea spam y envía el mensaje.
6. El profesional recibe notificación por email y en la plataforma.
7. Si acepta, se inicia conversación privada entre ambos.
8. Pueden intercambiar mensajes, archivos y enlaces.
9. El profesional puede marcar conversación como oportunidad o spam.

**Escenarios Alternativos:**  
- El profesional puede tener mensajería restringida solo a verificados.
- Puede configurar respuestas automáticas cuando no está disponible.
- Puede bloquear remitentes específicos o dominios.
- Sistema de plantillas para mensajes frecuentes de reclutadores.

**Restricciones:**  
- Límite de mensajes por día según plan para prevenir spam.
- Detección automática de spam y contenido inapropiado.
- Los profesionales pueden reportar mensajes no solicitados.
- Encriptación de mensajes para proteger privacidad.

---

## Caso de Uso: Análisis de Rendimiento del Perfil

**Actor Principal:** PROFESSIONAL  
**Escenario Principal:**  
1. El profesional accede a su dashboard de analytics desde el menú.
2. Ve resumen de métricas clave: vistas de perfil, likes, mensajes recibidos.
3. Analiza tendencias temporales con gráficos interactivos.
4. Revisa demografía de visitantes: ubicación, tipo de empresa, roles.
5. Identifica proyectos más vistos y habilidades más buscadas.
6. Ve posicionamiento en búsquedas para diferentes términos.
7. Compara su rendimiento con promedios de su área.
8. Recibe recomendaciones personalizadas para mejorar visibilidad.
9. Puede exportar reportes para análisis externo.

**Escenarios Alternativos:**  
- Puede configurar alertas para métricas específicas.
- Puede ver analytics de proyectos individuales.
- Puede A/B testing de diferentes versiones de perfil.
- Puede integrar con Google Analytics para análisis más profundo.

**Restricciones:**  
- Analytics detallados solo disponibles en planes premium.
- Datos anonimizados para proteger privacidad de visitantes.
- Métricas históricas limitadas según antigüedad de la cuenta.
- Cumplimiento GDPR en manejo de datos de analytics.

---

## Caso de Uso: Verificación de Empresa y Reclutador

**Actor Principal:** COMPANY o RECRUITER  
**Escenario Principal:**  
1. La empresa completa su perfil básico en la plataforma.
2. Solicita verificación desde el panel de configuración.
3. Proporciona documentación oficial: registro mercantil, NIT, etc.
4. Sube logo oficial y enlaces a sitios web corporativos.
5. El equipo de moderación revisa la documentación.
6. Se valida información contra bases de datos públicas.
7. Si es aprobada, recibe insignia de "Empresa Verificada".
8. Obtiene acceso a funciones premium y mayor credibilidad.
9. Los reclutadores asociados también obtienen verificación derivada.

**Escenarios Alternativos:**  
- Puede usar verificación por dominio de email corporativo.
- Puede solicitar re-verificación si cambia información legal.
- Puede apelar si la verificación es rechazada.
- Verificación express para empresas Fortune 500 o reconocidas.

**Restricciones:**  
- Proceso manual que puede tomar 3-5 días hábiles.
- Requiere documentación oficial válida y actualizada.
- Una empresa puede tener múltiples reclutadores verificados.
- Verificación se revoca si se detecta información falsa.

---

## Caso de Uso: Gestión de Habilidades y Tendencias

**Actor Principal:** PROFESSIONAL  
**Escenario Principal:**  
1. El profesional accede a la sección de habilidades de su perfil.
2. Ve habilidades actuales con niveles de competencia asignados.
3. Busca nuevas habilidades en el catálogo del sistema.
4. Añade habilidades emergentes relevantes a su área.
5. Configura nivel de experiencia y años de práctica.
6. Puede reordenar habilidades por importancia.
7. Ve sugerencias basadas en habilidades existentes y tendencias.
8. Recibe alertas sobre habilidades trending en su industria.
9. Puede conectar habilidades con proyectos específicos como evidencia.

**Escenarios Alternativos:**  
- Puede importar habilidades desde perfiles de LinkedIn.
- Puede solicitar nuevas habilidades si no existen en el catálogo.
- Puede ocultar habilidades específicas sin eliminarlas.
- Puede agrupar habilidades por categorías personalizadas.

**Restricciones:**  
- Límite de habilidades principales según plan.
- Validación de habilidades contra catálogo curado.
- Evita saturación de habilidades irrelevantes.
- Sistema de endorsements futura implementación.

---

## Caso de Uso: Directorio Público y Descubrimiento

**Actor Principal:** Visitante o Usuario  
**Escenario Principal:**  
1. El visitante accede al directorio público desde la homepage.
2. Explora perfiles destacados y proyectos en tendencia.
3. Usa filtros básicos: ubicación, habilidades principales, disponibilidad.
4. Navega por categorías: Frontend, Backend, Design, Marketing, etc.
5. Ve preview de perfiles con información clave resumida.
6. Accede a perfil completo de profesionales interesantes.
7. Puede dar like a perfiles y proyectos que le gusten.
8. Comparte perfiles interesantes en redes sociales.
9. Si es reclutador, puede enviar mensaje de contacto directo.

**Escenarios Alternativos:**  
- Puede usar búsqueda por texto libre en biografías y proyectos.
- Puede filtrar por rangos salariales o tarifas por hora.
- Puede ver solo profesionales activos recientemente.
- Puede explorar por ubicaciones geográficas específicas.

**Restricciones:**  
- Solo muestra perfiles marcados como públicos.
- Respeta configuraciones de privacidad individuales.
- Paginación para manejar gran volumen de perfiles.
- SEO optimizado para indexación en buscadores.

---

## Caso de Uso: Integración con Sistemas Externos

**Actor Principal:** PROFESSIONAL  
**Escenario Principal:**  
1. El profesional accede al centro de integraciones.
2. Selecciona conectar con GitHub para importar repositorios.
3. Autoriza acceso a su cuenta GitHub mediante OAuth.
4. El sistema sincroniza repositorios públicos automáticamente.
5. Puede seleccionar qué repositorios mostrar como proyectos.
6. Configura sincronización automática para nuevos commits.
7. Similarmente conecta LinkedIn para importar experiencia laboral.
8. Puede configurar qué información sincronizar y con qué frecuencia.
9. Mantiene control granular sobre datos importados.

**Escenarios Alternativos:**  
- Puede desconectar integraciones en cualquier momento.
- Puede hacer sincronización manual en lugar de automática.
- Puede mapear campos personalizados entre sistemas.
- Puede configurar webhooks para actualizaciones en tiempo real.

**Restricciones:**  
- Solo integra con servicios que soportan OAuth seguro.
- Usuario mantiene control total sobre qué datos se importan.
- Sincronización respeta rate limits de APIs externas.
- Datos importados se pueden modificar localmente.

---

## Caso de Uso: Moderación de Contenido y Reportes

**Actor Principal:** Cualquier Usuario o ADMIN  
**Escenario Principal:**  
1. Un usuario encuentra contenido inapropiado en un perfil o proyecto.
2. Selecciona opción "Reportar" y especifica el tipo de problema.
3. Proporciona descripción detallada del problema encontrado.
4. El sistema genera ticket de reporte y notifica a moderadores.
5. El equipo de moderación revisa el contenido reportado.
6. Se toma acción apropiada: advertencia, ocultación o ban.
7. Se notifica al usuario reportado sobre la decisión.
8. El usuario que reportó recibe seguimiento de la resolución.
9. Se mantiene log de todas las acciones de moderación.

**Escenarios Alternativos:**  
- Puede usar moderación automática con AI para casos obvios.
- Usuario reportado puede apelar la decisión tomada.
- Puede implementar sistema de strikes antes de ban permanente.
- Comunidad puede votar sobre contenido borderline.

**Restricciones:**  
- Proceso de moderación transparente y justo.
- Cumplimiento con regulaciones de contenido locales.
- Protección de privacidad durante proceso de revisión.
- Escalación a moderadores senior para casos complejos.

---

## Caso de Uso: Exportación de Datos y Portabilidad

**Actor Principal:** PROFESSIONAL  
**Escenario Principal:**  
1. El profesional solicita exportación de sus datos personales.
2. Selecciona qué información incluir: perfil, proyectos, mensajes, analytics.
3. Elige formato de exportación: JSON, PDF, HTML estático.
4. El sistema genera paquete de datos de forma asíncrona.
5. Recibe notificación cuando la exportación está lista.
6. Descarga archivo comprimido con todos sus datos.
7. Puede usar estos datos para backup o migrar a otra plataforma.
8. La exportación incluye formato legible y machine-readable.
9. Puede solicitar eliminación completa de cuenta si lo desea.

**Escenarios Alternativos:**  
- Puede programar exportaciones automáticas periódicas.
- Puede exportar solo datos de fecha específica.
- Puede generar CV/resume automático en PDF desde perfil.
- Puede crear sitio web estático con su portafolio exportado.

**Restricciones:**  
- Cumplimiento completo con GDPR y regulaciones de privacidad.
- Proceso de eliminación irreversible requiere confirmación múltiple.
- Datos de otros usuarios (mensajes) respetan sus derechos.
- Periodo de gracia antes de eliminación definitiva.

---

## Caso de Uso: Sistema de Notificaciones Inteligentes

**Actor Principal:** Cualquier Usuario  
**Escenario Principal:**  
1. El sistema detecta actividad relevante para el usuario.
2. Evalúa configuraciones de notificación personalizadas.
3. Determina el canal apropiado: push, email, in-app.
4. Genera notificación personalizada según contexto.
5. Envía notificación respetando horarios y frecuencias.
6. Usuario puede interactuar directamente desde la notificación.
7. Sistema trackea engagement para optimizar futuras notificaciones.
8. Permite snooze, mark as read, o acciones específicas.
9. Aprende patrones de usuario para mejorar relevancia.

**Escenarios Alternativos:**  
- Puede agrupar notificaciones similares en digest.
- Puede usar AI para priorizar notificaciones importantes.
- Puede configurar quiet hours y no molestar.
- Puede personalizar completamente tipos y frecuencias.

**Restricciones:**  
- Respeta preferencias granulares de cada usuario.
- No envía spam o notificaciones irrelevantes.
- Cumple con regulaciones de comunicaciones digitales.
- Permite opt-out fácil de cualquier tipo de notificación.

---

## Buenas Prácticas y Consideraciones de Seguridad

- **Privacy by Design:** Control granular de visibilidad de información personal.
- **Content Security:** Validación y sanitización de todo contenido generado por usuarios.
- **Professional Standards:** Moderación proactiva para mantener calidad profesional.
- **Data Protection:** Encriptación de datos sensibles y cumplimiento GDPR.
- **Anti-Spam:** Sistemas inteligentes para prevenir mensajes no solicitados.
- **Search Optimization:** SEO profesional para maximizar descubrimiento.
- **Mobile-First:** Experiencia optimizada para dispositivos móviles.
- **Accessibility:** Cumplimiento WCAG para usuarios con discapacidades.
- **Performance:** Carga rápida y experiencia fluida en todos los dispositivos.
- **Analytics Privacy:** Métricas útiles respetando privacidad de visitantes.
- **Professional Networking:** Facilitación de conexiones laborales genuinas.
- **Career Growth:** Herramientas para desarrollo profesional continuo.

---