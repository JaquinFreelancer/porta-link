# 🛣️ Mapa de rutas Backend (API RESTful) - Plataforma de Portafolios Profesionales

> **Comentarios:**  
> - Este mapa describe las rutas principales de la API para la plataforma de portafolios profesionales y búsqueda de talento.  
> - Basado en el modelo relacional y entidades del ERD proporcionado.
> - Roles soportados: `PROFESSIONAL`, `RECRUITER`, `COMPANY`, `ADMIN` (usuarios autenticados), y `guest` (no autenticado).
> - Autenticación JWT, control granular de permisos, búsqueda avanzada y mensajería integrada.

---

## Rutas públicas (sin autenticación)

| Método | Ruta                             | Descripción                                      | Roles       |
|--------|----------------------------------|--------------------------------------------------|-------------|
| GET    | /api/health                      | Estado del sistema y servicios                   | Todos       |
| POST   | /api/auth/register               | Registro de nuevo usuario profesional            | Todos       |
| POST   | /api/auth/login                  | Login y obtención de token JWT                   | Todos       |
| POST   | /api/auth/password-reset         | Solicitar recuperación de contraseña             | Todos       |
| POST   | /api/auth/password-reset/confirm | Confirmar recuperación de contraseña             | Todos       |
| GET    | /api/profiles/public             | Listar perfiles públicos (directorio)            | Todos       |
| GET    | /api/profiles/:username          | Ver perfil público por username                  | Todos       |
| GET    | /api/projects/featured           | Proyectos destacados públicos                    | Todos       |
| GET    | /api/skills                      | Listar todas las habilidades disponibles         | Todos       |
| GET    | /api/skills/trending             | Habilidades más populares/tendencia              | Todos       |
| GET    | /api/search/profiles             | Búsqueda pública de perfiles con filtros         | Todos       |
| GET    | /api/search/projects             | Búsqueda pública de proyectos                    | Todos       |

---

## Rutas de autenticación y usuario

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| POST   | /api/auth/logout                 | Logout (invalidar sesión/token)                  | Usuarios          |
| POST   | /api/auth/refresh                | Refrescar token JWT                              | Usuarios          |
| GET    | /api/auth/me                     | Obtener datos del usuario autenticado           | Usuarios          |
| PUT    | /api/auth/profile                | Editar perfil básico del usuario                | Usuarios          |
| PUT    | /api/auth/change-password        | Cambiar contraseña                               | Usuarios          |
| POST   | /api/auth/verify-email           | Verificar email con token                        | Todos             |
| POST   | /api/auth/resend-verification    | Reenviar email de verificación                   | Usuarios          |
| GET    | /api/dashboard                   | Dashboard personalizado según tipo de usuario   | Usuarios          |
| GET    | /api/notifications               | Listar notificaciones del usuario               | Usuarios          |
| PUT    | /api/notifications/:id/read      | Marcar notificación como leída                   | Usuarios          |
| DELETE | /api/notifications/:id           | Eliminar notificación                            | Usuarios          |
| PUT    | /api/user/settings               | Actualizar configuraciones de usuario           | Usuarios          |

---

## Rutas de perfil profesional

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/profile                     | Ver perfil propio completo                      | Usuarios          |
| PUT    | /api/profile                     | Actualizar perfil profesional                   | PROFESSIONAL      |
| POST   | /api/profile/avatar              | Subir foto de perfil                             | Usuarios          |
| POST   | /api/profile/cover               | Subir imagen de portada                          | Usuarios          |
| PUT    | /api/profile/availability        | Actualizar estado de disponibilidad             | PROFESSIONAL      |
| PUT    | /api/profile/visibility          | Cambiar visibilidad del perfil                  | PROFESSIONAL      |
| GET    | /api/profile/analytics           | Estadísticas del perfil (vistas, likes)         | PROFESSIONAL      |
| GET    | /api/profile/completeness        | Porcentaje de completitud del perfil            | PROFESSIONAL      |
| POST   | /api/profile/social-links        | Añadir enlace de red social                      | PROFESSIONAL      |
| DELETE | /api/profile/social-links/:id    | Eliminar enlace de red social                    | PROFESSIONAL      |
| GET    | /api/profile/views               | Historial de visualizaciones del perfil         | PROFESSIONAL      |
| GET    | /api/profile/likes               | Usuarios que dieron like al perfil              | PROFESSIONAL      |

---

## Rutas de habilidades y experiencia

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/profile/skills              | Listar habilidades del usuario                  | Usuarios          |
| POST   | /api/profile/skills              | Añadir habilidad al perfil                      | PROFESSIONAL      |
| PUT    | /api/profile/skills/:id          | Actualizar nivel de habilidad                   | PROFESSIONAL      |
| DELETE | /api/profile/skills/:id          | Eliminar habilidad del perfil                   | PROFESSIONAL      |
| PUT    | /api/profile/skills/reorder      | Reordenar habilidades                            | PROFESSIONAL      |
| GET    | /api/profile/work-experience     | Listar experiencia laboral                       | Usuarios          |
| POST   | /api/profile/work-experience     | Añadir experiencia laboral                       | PROFESSIONAL      |
| PUT    | /api/profile/work-experience/:id | Actualizar experiencia laboral                   | PROFESSIONAL      |
| DELETE | /api/profile/work-experience/:id | Eliminar experiencia laboral                     | PROFESSIONAL      |
| GET    | /api/profile/education           | Listar educación/formación                       | Usuarios          |
| POST   | /api/profile/education           | Añadir formación académica                       | PROFESSIONAL      |
| PUT    | /api/profile/education/:id       | Actualizar formación académica                   | PROFESSIONAL      |
| DELETE | /api/profile/education/:id       | Eliminar formación académica                     | PROFESSIONAL      |
| GET    | /api/profile/certifications      | Listar certificaciones                           | Usuarios          |
| POST   | /api/profile/certifications      | Añadir certificación                             | PROFESSIONAL      |
| PUT    | /api/profile/certifications/:id  | Actualizar certificación                         | PROFESSIONAL      |
| DELETE | /api/profile/certifications/:id  | Eliminar certificación                           | PROFESSIONAL      |

---

## Rutas de proyectos y portafolio

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/projects                    | Listar proyectos del usuario autenticado        | PROFESSIONAL      |
| POST   | /api/projects                    | Crear nuevo proyecto                             | PROFESSIONAL      |
| GET    | /api/projects/:id                | Ver detalle del proyecto propio                 | PROFESSIONAL      |
| GET    | /api/projects/:slug/public       | Ver proyecto público por slug                    | Todos             |
| PUT    | /api/projects/:id                | Actualizar proyecto                              | PROFESSIONAL      |
| DELETE | /api/projects/:id                | Eliminar proyecto                                | PROFESSIONAL      |
| PUT    | /api/projects/:id/visibility     | Cambiar visibilidad del proyecto                | PROFESSIONAL      |
| PUT    | /api/projects/:id/featured       | Marcar/desmarcar como destacado                  | PROFESSIONAL      |
| POST   | /api/projects/:id/images         | Subir imágenes al proyecto                       | PROFESSIONAL      |
| PUT    | /api/projects/:id/images/:imageId| Actualizar imagen del proyecto                   | PROFESSIONAL      |
| DELETE | /api/projects/:id/images/:imageId| Eliminar imagen del proyecto                     | PROFESSIONAL      |
| POST   | /api/projects/:id/attachments    | Subir archivos al proyecto                       | PROFESSIONAL      |
| DELETE | /api/projects/:id/attachments/:fileId | Eliminar archivo del proyecto               | PROFESSIONAL      |
| POST   | /api/projects/:id/skills         | Asociar habilidad al proyecto                   | PROFESSIONAL      |
| DELETE | /api/projects/:id/skills/:skillId| Desasociar habilidad del proyecto               | PROFESSIONAL      |
| PUT    | /api/projects/reorder            | Reordenar proyectos en el portafolio            | PROFESSIONAL      |
| POST   | /api/projects/:id/like           | Dar/quitar like al proyecto público             | Usuarios          |
| GET    | /api/projects/:id/analytics      | Estadísticas del proyecto                        | PROFESSIONAL      |

---

## Rutas de búsqueda y directorio

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/search/professionals        | Búsqueda avanzada de profesionales              | Todos             |
| GET    | /api/search/companies            | Búsqueda de empresas registradas                 | Todos             |
| GET    | /api/search/projects             | Búsqueda de proyectos públicos                  | Todos             |
| GET    | /api/search/skills               | Búsqueda de habilidades                          | Todos             |
| POST   | /api/search/save                 | Guardar búsqueda personalizada                   | RECRUITER, COMPANY|
| GET    | /api/search/saved                | Listar búsquedas guardadas                       | RECRUITER, COMPANY|
| PUT    | /api/search/saved/:id            | Actualizar búsqueda guardada                     | RECRUITER, COMPANY|
| DELETE | /api/search/saved/:id            | Eliminar búsqueda guardada                       | RECRUITER, COMPANY|
| POST   | /api/search/saved/:id/run        | Ejecutar búsqueda guardada                       | RECRUITER, COMPANY|
| GET    | /api/search/suggestions          | Sugerencias de búsqueda basadas en IA           | RECRUITER, COMPANY|
| GET    | /api/directory/featured          | Profesionales destacados del directorio         | Todos             |
| GET    | /api/directory/trending          | Perfiles con mayor actividad                     | Todos             |
| GET    | /api/directory/filters           | Opciones de filtrado disponibles                | Todos             |

---

## Rutas de perfiles empresariales

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/company/profile             | Ver perfil de empresa propio                    | COMPANY           |
| PUT    | /api/company/profile             | Actualizar perfil de empresa                    | COMPANY           |
| POST   | /api/company/logo                | Subir logo de la empresa                         | COMPANY           |
| POST   | /api/company/cover               | Subir imagen de portada empresarial             | COMPANY           |
| POST   | /api/company/verify              | Solicitar verificación de empresa               | COMPANY           |
| PUT    | /api/company/hiring-status       | Actualizar estado de contratación               | COMPANY           |
| POST   | /api/company/locations           | Añadir ubicación/oficina                         | COMPANY           |
| DELETE | /api/company/locations/:id       | Eliminar ubicación                               | COMPANY           |
| POST   | /api/company/benefits            | Añadir beneficio ofrecido                        | COMPANY           |
| DELETE | /api/company/benefits/:id        | Eliminar beneficio                               | COMPANY           |
| GET    | /api/company/analytics           | Estadísticas del perfil empresarial             | COMPANY           |

---

## Rutas de reclutadores

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/recruiter/profile           | Ver perfil de reclutador propio                 | RECRUITER         |
| PUT    | /api/recruiter/profile           | Actualizar perfil de reclutador                 | RECRUITER         |
| POST   | /api/recruiter/verify            | Solicitar verificación de reclutador            | RECRUITER         |
| PUT    | /api/recruiter/specialization    | Actualizar especialización                       | RECRUITER         |
| GET    | /api/recruiter/placements        | Historial de colocaciones exitosas              | RECRUITER         |
| POST   | /api/recruiter/placements        | Registrar colocación exitosa                     | RECRUITER         |
| GET    | /api/recruiter/preferences       | Preferencias de búsqueda                         | RECRUITER         |
| PUT    | /api/recruiter/preferences       | Actualizar preferencias de búsqueda              | RECRUITER         |
| GET    | /api/recruiter/analytics         | Estadísticas de actividad del reclutador        | RECRUITER         |

---

## Rutas de mensajería y contacto

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/conversations               | Listar conversaciones del usuario               | Usuarios          |
| POST   | /api/conversations               | Iniciar nueva conversación                       | Usuarios          |
| GET    | /api/conversations/:id           | Ver conversación específica                      | Usuarios          |
| PUT    | /api/conversations/:id/archive   | Archivar conversación                            | Usuarios          |
| PUT    | /api/conversations/:id/block     | Bloquear conversación                            | Usuarios          |
| GET    | /api/conversations/:id/messages  | Listar mensajes de conversación                 | Usuarios          |
| POST   | /api/conversations/:id/messages  | Enviar mensaje en conversación                   | Usuarios          |
| PUT    | /api/messages/:id/read           | Marcar mensaje como leído                        | Usuarios          |
| POST   | /api/messages/:id/reply          | Responder a mensaje específico                   | Usuarios          |
| POST   | /api/messages/attachments        | Subir archivo adjunto a mensaje                  | Usuarios          |
| GET    | /api/conversations/unread        | Conteo de conversaciones no leídas               | Usuarios          |
| POST   | /api/contact/:username           | Enviar mensaje de contacto a perfil público     | Usuarios          |
| POST   | /api/messages/:id/report         | Reportar mensaje inapropiado                     | Usuarios          |

---

## Rutas de interacciones sociales

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| POST   | /api/profiles/:id/like           | Dar like a perfil                                | Usuarios          |
| DELETE | /api/profiles/:id/like           | Quitar like de perfil                            | Usuarios          |
| GET    | /api/profiles/:id/likes          | Ver usuarios que dieron like                     | Usuarios          |
| POST   | /api/profiles/:id/view           | Registrar visualización de perfil               | Sistema           |
| GET    | /api/profiles/:id/views          | Estadísticas de visualizaciones                  | Propietario       |
| POST   | /api/projects/:id/like           | Dar like a proyecto                              | Usuarios          |
| DELETE | /api/projects/:id/like           | Quitar like de proyecto                          | Usuarios          |
| GET    | /api/projects/:id/likes          | Ver usuarios que dieron like al proyecto        | Usuarios          |
| POST   | /api/profiles/:id/follow         | Seguir perfil (futura implementación)           | Usuarios          |
| DELETE | /api/profiles/:id/follow         | Dejar de seguir perfil                           | Usuarios          |
| GET    | /api/user/following              | Perfiles que sigo                                | Usuarios          |
| GET    | /api/user/followers              | Usuarios que me siguen                           | Usuarios          |

---

## Rutas de analytics y estadísticas

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/analytics/profile           | Estadísticas detalladas del perfil              | PROFESSIONAL      |
| GET    | /api/analytics/projects          | Estadísticas de todos los proyectos             | PROFESSIONAL      |
| GET    | /api/analytics/projects/:id      | Estadísticas de proyecto específico             | PROFESSIONAL      |
| GET    | /api/analytics/visitors          | Análisis de visitantes del perfil               | PROFESSIONAL      |
| GET    | /api/analytics/search-rankings   | Posicionamiento en búsquedas                    | PROFESSIONAL      |
| GET    | /api/analytics/engagement        | Métricas de engagement (likes, vistas)          | PROFESSIONAL      |
| GET    | /api/analytics/trends            | Tendencias de visualización                      | PROFESSIONAL      |
| GET    | /api/analytics/demographics      | Demografía de visitantes                         | PROFESSIONAL      |
| POST   | /api/analytics/events            | Registrar evento personalizado                   | Sistema           |
| GET    | /api/analytics/export            | Exportar datos de analytics                      | PROFESSIONAL      |

---

## Rutas de administración

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/admin/dashboard             | Dashboard principal de administración           | ADMIN             |
| GET    | /api/admin/users                 | Listar todos los usuarios                       | ADMIN             |
| GET    | /api/admin/users/:id             | Ver detalle de usuario específico               | ADMIN             |
| PUT    | /api/admin/users/:id/status      | Cambiar estado de usuario                        | ADMIN             |
| PUT    | /api/admin/users/:id/verify      | Verificar usuario/empresa                        | ADMIN             |
| GET    | /api/admin/reports               | Listar reportes pendientes                       | ADMIN             |
| PUT    | /api/admin/reports/:id           | Resolver reporte                                 | ADMIN             |
| GET    | /api/admin/analytics             | Analytics generales de la plataforma            | ADMIN             |
| GET    | /api/admin/skills                | Gestión de habilidades del sistema              | ADMIN             |
| POST   | /api/admin/skills                | Crear nueva habilidad                            | ADMIN             |
| PUT    | /api/admin/skills/:id            | Actualizar habilidad                             | ADMIN             |
| DELETE | /api/admin/skills/:id            | Eliminar habilidad                               | ADMIN             |
| GET    | /api/admin/system-settings       | Configuraciones del sistema                      | ADMIN             |
| PUT    | /api/admin/system-settings       | Actualizar configuraciones                       | ADMIN             |
| GET    | /api/admin/logs                  | Logs de auditoría del sistema                    | ADMIN             |
| POST   | /api/admin/announcements         | Crear anuncio para usuarios                      | ADMIN             |
| GET    | /api/admin/content-moderation    | Panel de moderación de contenido                 | ADMIN             |

---

## Rutas de reportes y moderación

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| POST   | /api/reports/profile             | Reportar perfil inapropiado                     | Usuarios          |
| POST   | /api/reports/project             | Reportar proyecto inapropiado                   | Usuarios          |
| POST   | /api/reports/message             | Reportar mensaje inapropiado                    | Usuarios          |
| GET    | /api/reports/my-reports          | Ver mis reportes enviados                        | Usuarios          |
| GET    | /api/moderation/queue            | Cola de contenido por moderar                    | ADMIN             |
| PUT    | /api/moderation/approve/:id      | Aprobar contenido reportado                      | ADMIN             |
| PUT    | /api/moderation/reject/:id       | Rechazar/eliminar contenido                      | ADMIN             |
| POST   | /api/moderation/ban-user         | Banear usuario por violaciones                   | ADMIN             |
| POST   | /api/moderation/warn-user        | Enviar advertencia a usuario                     | ADMIN             |

---

## Rutas de archivos y multimedia

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| POST   | /api/upload/avatar               | Subir foto de perfil                             | Usuarios          |
| POST   | /api/upload/cover                | Subir imagen de portada                          | Usuarios          |
| POST   | /api/upload/project-image        | Subir imagen de proyecto                         | PROFESSIONAL      |
| POST   | /api/upload/project-attachment   | Subir archivo adjunto a proyecto                | PROFESSIONAL      |
| POST   | /api/upload/message-attachment   | Subir archivo a mensaje                          | Usuarios          |
| POST   | /api/upload/certificate          | Subir imagen de certificación                    | PROFESSIONAL      |
| POST   | /api/upload/company-logo         | Subir logo de empresa                            | COMPANY           |
| GET    | /api/files/:id                   | Descargar/ver archivo                            | Autorizado        |
| DELETE | /api/files/:id                   | Eliminar archivo                                 | Propietario       |
| GET    | /api/upload/presigned-url        | Obtener URL firmada para upload directo         | Usuarios          |

---

## Rutas de integración y webhook

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/integrations                | Listar integraciones disponibles                | Usuarios          |
| POST   | /api/integrations/github         | Conectar cuenta de GitHub                        | PROFESSIONAL      |
| DELETE | /api/integrations/github         | Desconectar GitHub                               | PROFESSIONAL      |
| POST   | /api/integrations/linkedin       | Conectar cuenta de LinkedIn                      | Usuarios          |
| DELETE | /api/integrations/linkedin       | Desconectar LinkedIn                             | Usuarios          |
| POST   | /api/integrations/portfolio-sync | Sincronizar datos externos                       | PROFESSIONAL      |
| POST   | /api/webhooks/github             | Webhook para eventos de GitHub                   | Sistema           |
| POST   | /api/webhooks/linkedin           | Webhook para eventos de LinkedIn                 | Sistema           |

---

## Rutas de exportación y backup

| Método | Ruta                             | Descripción                                      | Roles             |
|--------|----------------------------------|--------------------------------------------------|-------------------|
| GET    | /api/export/profile              | Exportar datos del perfil                       | Usuarios          |
| GET    | /api/export/projects             | Exportar portafolio completo                     | PROFESSIONAL      |
| GET    | /api/export/messages             | Exportar conversaciones                          | Usuarios          |
| GET    | /api/export/analytics            | Exportar datos de analytics                      | Usuarios          |
| POST   | /api/data/download-request       | Solicitar descarga de todos los datos           | Usuarios          |
| POST   | /api/data/delete-account         | Solicitar eliminación de cuenta                  | Usuarios          |
| GET    | /api/data/gdpr-compliance        | Información de cumplimiento GDPR                 | Usuarios          |

---

## Notas de seguridad y buenas prácticas

- **Autenticación JWT:** Refresh tokens, expiración configurable, blacklist de tokens.
- **Rate limiting:** Protección contra abuso en endpoints de búsqueda y mensajería.
- **Validación de archivos:** Tipos permitidos, tamaños máximos, escaneo de malware.
- **Privacy by design:** Control granular de visibilidad de perfil y proyectos.
- **GDPR compliance:** Exportación y eliminación de datos personales.
- **Content moderation:** Sistema de reportes y moderación automatizada.
- **Search optimization:** Índices optimizados, cache de búsquedas frecuentes.
- **Analytics privacy:** Anonimización de datos sensibles, opt-out disponible.
- **Multi-device support:** Sincronización de sesiones, logout remoto.
- **Professional networking:** Protección contra spam, verificación de identidad.

---