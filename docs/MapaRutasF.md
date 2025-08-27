# 🗺️ Mapa de rutas Frontend - Plataforma de Portafolios Profesionales

> **Comentarios:**  
> - Este mapa define las rutas principales de la interfaz web para la plataforma de portafolios profesionales y búsqueda de talento.
> - Se basa en la estructura y entidades del ERD proporcionado y las mejores prácticas de UX profesional.
> - Indica si la ruta es pública, requiere autenticación, o es específica para roles (PROFESSIONAL, RECRUITER, COMPANY, ADMIN).
> - Diseño responsive optimizado para profesionales tech, empresas y reclutadores.

---

## Rutas públicas (accesibles para cualquier visitante)

| Ruta                       | Página/Componente                | Descripción                                         |
|----------------------------|----------------------------------|-----------------------------------------------------|
| `/`                        | LandingPage                      | Página principal con showcases de talento          |
| `/about`                   | AboutPage                        | Información sobre la plataforma                    |
| `/how-it-works`            | HowItWorksPage                   | Cómo funciona para profesionales y empresas        |
| `/pricing`                 | PricingPage                      | Planes premium y características                    |
| `/directory`               | PublicDirectory                  | Directorio público de profesionales                |
| `/directory/featured`      | FeaturedProfiles                 | Perfiles destacados del mes                        |
| `/projects`                | PublicProjects                   | Galería pública de proyectos destacados            |
| `/skills`                  | SkillsDirectory                  | Directorio de habilidades y tecnologías            |
| `/search`                  | PublicSearch                     | Búsqueda pública de talento                        |
| `/companies`               | CompaniesDirectory               | Directorio de empresas registradas                 |
| `/blog`                    | BlogPage                         | Blog con contenido para profesionales              |
| `/help`                    | HelpCenter                       | Centro de ayuda y documentación                    |
| `/contact`                 | ContactPage                      | Formulario de contacto y soporte                   |
| `/legal/privacy`           | PrivacyPolicy                    | Política de privacidad                              |
| `/legal/terms`             | TermsOfService                   | Términos y condiciones                              |
| `/404`                     | NotFound                         | Página de error no encontrada                       |

---

## Rutas de autenticación y registro

| Ruta                       | Página/Componente                | Descripción                                        | Acceso    |
|----------------------------|----------------------------------|----------------------------------------------------|-----------|
| `/login`                   | Login                            | Formulario de login                                | Pública   |
| `/register`                | Register                         | Registro de nuevo usuario                          | Pública   |
| `/register/professional`   | ProfessionalRegister             | Registro específico para profesionales            | Pública   |
| `/register/company`        | CompanyRegister                  | Registro específico para empresas                  | Pública   |
| `/register/recruiter`      | RecruiterRegister                | Registro específico para reclutadores             | Pública   |
| `/register/success`        | RegistrationSuccess              | Confirmación de registro exitoso                  | Pública   |
| `/verify-email/:token`     | EmailVerification                | Verificación de email con token                   | Pública   |
| `/forgot-password`         | ForgotPassword                   | Solicitar recuperación de contraseña              | Pública   |
| `/reset-password/:token`   | ResetPassword                    | Formulario para restablecer contraseña            | Pública   |
| `/logout`                  | LogoutHandler                    | Acción de cierre de sesión                        | Usuarios  |

---

## Rutas del dashboard principal (requieren autenticación)

| Ruta                       | Página/Componente                | Descripción                                        | Roles      |
|----------------------------|----------------------------------|----------------------------------------------------|------------|
| `/dashboard`               | MainDashboard                    | Dashboard principal según tipo de usuario         | Usuarios   |
| `/dashboard/professional`  | ProfessionalDashboard            | Dashboard específico para profesionales           | PROFESSIONAL |
| `/dashboard/company`       | CompanyDashboard                 | Dashboard específico para empresas                | COMPANY    |
| `/dashboard/recruiter`     | RecruiterDashboard               | Dashboard específico para reclutadores            | RECRUITER  |
| `/dashboard/analytics`     | AnalyticsDashboard               | Panel de análisis y estadísticas                  | Usuarios   |
| `/dashboard/notifications` | NotificationCenter               | Centro de notificaciones                           | Usuarios   |
| `/settings`                | UserSettings                     | Configuración general del usuario                 | Usuarios   |
| `/settings/account`        | AccountSettings                  | Configuración de cuenta y seguridad               | Usuarios   |
| `/settings/privacy`        | PrivacySettings                  | Configuración de privacidad                       | Usuarios   |
| `/settings/notifications`  | NotificationSettings             | Configuración de notificaciones                   | Usuarios   |

---

## Rutas de perfil profesional

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/profile`                 | MyProfile                        | Vista de mi perfil completo                       | PROFESSIONAL      |
| `/profile/edit`            | EditProfile                      | Editar información básica del perfil              | PROFESSIONAL      |
| `/profile/setup`           | ProfileSetup                     | Wizard de configuración inicial                   | PROFESSIONAL      |
| `/profile/preview`         | ProfilePreview                   | Vista previa del perfil público                   | PROFESSIONAL      |
| `/profile/analytics`       | ProfileAnalytics                 | Estadísticas detalladas del perfil                | PROFESSIONAL      |
| `/profile/visibility`      | VisibilitySettings               | Configuración de visibilidad del perfil           | PROFESSIONAL      |
| `/@:username`              | PublicProfile                    | Perfil público por username                       | Público           |
| `/@:username/projects`     | UserProjects                     | Proyectos públicos del usuario                    | Público           |
| `/@:username/contact`      | ContactForm                      | Formulario de contacto directo                    | Público           |

---

## Rutas de habilidades y experiencia

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/profile/skills`          | SkillsManagement                 | Gestión de habilidades y tecnologías              | PROFESSIONAL      |
| `/profile/skills/add`      | AddSkills                        | Agregar nuevas habilidades                         | PROFESSIONAL      |
| `/profile/experience`      | ExperienceManagement             | Gestión de experiencia laboral                     | PROFESSIONAL      |
| `/profile/experience/add`  | AddExperience                    | Agregar experiencia laboral                        | PROFESSIONAL      |
| `/profile/experience/:id/edit` | EditExperience               | Editar experiencia específica                      | PROFESSIONAL      |
| `/profile/education`       | EducationManagement              | Gestión de formación académica                     | PROFESSIONAL      |
| `/profile/education/add`   | AddEducation                     | Agregar formación académica                        | PROFESSIONAL      |
| `/profile/education/:id/edit` | EditEducation                 | Editar formación específica                        | PROFESSIONAL      |
| `/profile/certifications`  | CertificationsManagement         | Gestión de certificaciones                         | PROFESSIONAL      |
| `/profile/certifications/add` | AddCertification              | Agregar certificación                              | PROFESSIONAL      |
| `/profile/certifications/:id/edit` | EditCertification        | Editar certificación específica                    | PROFESSIONAL      |

---

## Rutas de proyectos y portafolio

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/portfolio`               | MyPortfolio                      | Vista general de mi portafolio                     | PROFESSIONAL      |
| `/portfolio/projects`      | ProjectsManagement               | Gestión de proyectos del portafolio               | PROFESSIONAL      |
| `/portfolio/projects/new`  | CreateProject                    | Crear nuevo proyecto                               | PROFESSIONAL      |
| `/portfolio/projects/:id`  | ProjectDetail                    | Vista detallada del proyecto propio               | PROFESSIONAL      |
| `/portfolio/projects/:id/edit` | EditProject                  | Editar proyecto                                    | PROFESSIONAL      |
| `/portfolio/projects/:id/images` | ProjectImageManager          | Gestión de imágenes del proyecto                   | PROFESSIONAL      |
| `/portfolio/projects/:id/analytics` | ProjectAnalytics          | Estadísticas del proyecto                          | PROFESSIONAL      |
| `/projects/:slug`          | PublicProjectDetail              | Vista pública de proyecto por slug                 | Público           |
| `/portfolio/organize`      | OrganizePortfolio                | Organizar y reordenar proyectos                    | PROFESSIONAL      |
| `/portfolio/settings`      | PortfolioSettings                | Configuración del portafolio                       | PROFESSIONAL      |

---

## Rutas de búsqueda y directorio

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/explore`                 | ExplorePage                      | Explorar perfiles y proyectos destacados          | Público           |
| `/explore/professionals`   | ProfessionalsDirectory           | Directorio de profesionales                       | Público           |
| `/explore/companies`       | CompaniesDirectory               | Directorio de empresas                             | Público           |
| `/explore/projects`        | ProjectsDirectory                | Galería de proyectos públicos                     | Público           |
| `/explore/skills/:skill`   | SkillBasedDirectory              | Profesionales por habilidad específica            | Público           |
| `/search/advanced`         | AdvancedSearch                   | Búsqueda avanzada con filtros                     | Público           |
| `/search/results`          | SearchResults                    | Resultados de búsqueda                             | Público           |
| `/search/saved`            | SavedSearches                    | Búsquedas guardadas                                | RECRUITER, COMPANY|
| `/search/save`             | SaveSearch                       | Guardar búsqueda actual                            | RECRUITER, COMPANY|
| `/filters`                 | FilterOptions                    | Opciones de filtrado disponibles                  | Público           |
| `/trending`                | TrendingPage                     | Tendencias en habilidades y proyectos             | Público           |

---

## Rutas de perfiles empresariales

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/company/profile`         | CompanyProfile                   | Vista del perfil de empresa                       | COMPANY           |
| `/company/profile/edit`    | EditCompanyProfile               | Editar perfil de empresa                          | COMPANY           |
| `/company/profile/setup`   | CompanySetup                     | Configuración inicial de empresa                  | COMPANY           |
| `/company/team`            | CompanyTeam                      | Gestión del equipo de reclutadores                | COMPANY           |
| `/company/team/invite`     | InviteRecruiter                  | Invitar reclutador a la empresa                   | COMPANY           |
| `/company/analytics`       | CompanyAnalytics                 | Estadísticas empresariales                        | COMPANY           |
| `/company/verification`    | CompanyVerification              | Proceso de verificación empresarial               | COMPANY           |
| `/company/hiring`          | HiringDashboard                  | Panel de contratación                              | COMPANY           |
| `/companies/:slug`         | PublicCompanyProfile             | Perfil público de empresa                         | Público           |

---

## Rutas de reclutadores

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/recruiter/profile`       | RecruiterProfile                 | Vista del perfil de reclutador                    | RECRUITER         |
| `/recruiter/profile/edit`  | EditRecruiterProfile             | Editar perfil de reclutador                       | RECRUITER         |
| `/recruiter/profile/setup` | RecruiterSetup                   | Configuración inicial de reclutador               | RECRUITER         |
| `/recruiter/searches`      | RecruiterSearches                | Gestión de búsquedas de talento                   | RECRUITER         |
| `/recruiter/candidates`    | CandidatesList                   | Lista de candidatos potenciales                   | RECRUITER         |
| `/recruiter/placements`    | PlacementHistory                 | Historial de colocaciones exitosas                | RECRUITER         |
| `/recruiter/analytics`     | RecruiterAnalytics               | Estadísticas de actividad del reclutador          | RECRUITER         |
| `/recruiter/verification`  | RecruiterVerification            | Proceso de verificación de reclutador             | RECRUITER         |
| `/recruiters/:username`    | PublicRecruiterProfile           | Perfil público de reclutador                      | Público           |

---

## Rutas de mensajería y contacto

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/messages`                | MessagesCenter                   | Centro de mensajes y conversaciones               | Usuarios          |
| `/messages/conversations`  | ConversationsList                | Lista de conversaciones                            | Usuarios          |
| `/messages/conversation/:id` | ConversationDetail             | Vista de conversación específica                   | Usuarios          |
| `/messages/compose`        | ComposeMessage                   | Componer nuevo mensaje                             | Usuarios          |
| `/messages/compose/:username` | DirectMessage                 | Mensaje directo a usuario específico              | Usuarios          |
| `/messages/archived`       | ArchivedMessages                 | Mensajes archivados                                | Usuarios          |
| `/messages/blocked`        | BlockedConversations             | Conversaciones bloqueadas                          | Usuarios          |
| `/messages/settings`       | MessageSettings                  | Configuración de mensajería                       | Usuarios          |
| `/inbox`                   | InboxOverview                    | Vista general del inbox                            | Usuarios          |

---

## Rutas de interacciones sociales

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/likes`                   | MyLikes                          | Perfiles y proyectos que he dado like             | Usuarios          |
| `/likes/received`          | ReceivedLikes                    | Likes recibidos en mi perfil                      | PROFESSIONAL      |
| `/views`                   | ProfileViews                     | Quién ha visto mi perfil                          | PROFESSIONAL      |
| `/following`               | FollowingList                    | Perfiles que sigo                                  | Usuarios          |
| `/followers`               | FollowersList                    | Usuarios que me siguen                             | Usuarios          |
| `/activity`                | ActivityFeed                     | Feed de actividad de usuarios seguidos            | Usuarios          |
| `/recommendations`         | Recommendations                  | Recomendaciones personalizadas                     | Usuarios          |
| `/bookmarks`               | BookmarkedProfiles               | Perfiles guardados como favoritos                 | RECRUITER, COMPANY|

---

## Rutas de analytics y estadísticas

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/analytics`               | AnalyticsOverview                | Vista general de estadísticas                     | PROFESSIONAL      |
| `/analytics/profile`       | ProfileAnalytics                 | Análisis detallado del perfil                     | PROFESSIONAL      |
| `/analytics/projects`      | ProjectsAnalytics                | Estadísticas de todos los proyectos               | PROFESSIONAL      |
| `/analytics/visitors`      | VisitorAnalytics                 | Análisis de visitantes del perfil                 | PROFESSIONAL      |
| `/analytics/engagement`    | EngagementMetrics                | Métricas de engagement                             | PROFESSIONAL      |
| `/analytics/search`        | SearchRankings                   | Posicionamiento en búsquedas                      | PROFESSIONAL      |
| `/analytics/export`        | ExportAnalytics                  | Exportar datos de analytics                       | PROFESSIONAL      |
| `/insights`                | PersonalizedInsights             | Insights personalizados con IA                    | PROFESSIONAL      |

---

## Rutas de administración (solo ADMIN)

| Ruta                       | Página/Componente                | Descripción                                        | Roles      |
|----------------------------|----------------------------------|----------------------------------------------------|------------|
| `/admin`                   | AdminPanel                       | Panel principal de administración                  | ADMIN      |
| `/admin/dashboard`         | AdminDashboard                   | Dashboard administrativo                           | ADMIN      |
| `/admin/users`             | UserManagement                   | Gestión de usuarios de la plataforma              | ADMIN      |
| `/admin/users/:id`         | UserDetail                       | Detalle de usuario específico                     | ADMIN      |
| `/admin/companies`         | CompanyManagement                | Gestión de empresas registradas                   | ADMIN      |
| `/admin/verification`      | VerificationQueue                | Cola de verificaciones pendientes                 | ADMIN      |
| `/admin/reports`           | ReportsManagement                | Gestión de reportes y moderación                  | ADMIN      |
| `/admin/content`           | ContentModeration                | Moderación de contenido                            | ADMIN      |
| `/admin/skills`            | SkillsAdministration             | Administración de habilidades del sistema         | ADMIN      |
| `/admin/analytics`         | PlatformAnalytics                | Analytics de toda la plataforma                   | ADMIN      |
| `/admin/settings`          | SystemSettings                   | Configuraciones del sistema                       | ADMIN      |
| `/admin/logs`              | AuditLogs                        | Logs de auditoría                                  | ADMIN      |
| `/admin/announcements`     | AnnouncementManager              | Gestión de anuncios para usuarios                 | ADMIN      |

---

## Rutas de configuración y herramientas

| Ruta                       | Página/Componente                | Descripción                                        | Roles              |
|----------------------------|----------------------------------|----------------------------------------------------|-------------------|
| `/tools`                   | ToolsCenter                      | Centro de herramientas para profesionales         | PROFESSIONAL      |
| `/tools/portfolio-builder` | PortfolioBuilder                 | Constructor visual de portafolio                   | PROFESSIONAL      |
| `/tools/resume-generator`  | ResumeGenerator                  | Generador de CV desde perfil                      | PROFESSIONAL      |
| `/tools/project-analyzer`  | ProjectAnalyzer                  | Analizador de rendimiento de proyectos            | PROFESSIONAL      |
| `/tools/skill-tracker`     | SkillTracker                     | Seguimiento de progreso en habilidades            | PROFESSIONAL      |
| `/integrations`            | IntegrationsCenter               | Centro de integraciones                            | Usuarios          |
| `/integrations/github`     | GitHubIntegration                | Integración con GitHub                             | PROFESSIONAL      |
| `/integrations/linkedin`   | LinkedInIntegration              | Integración con LinkedIn                           | Usuarios          |
| `/export`                  | DataExport                       | Exportación de datos personales                   | Usuarios          |

---

## Rutas especiales y funcionales

| Ruta                       | Página/Componente                | Descripción                                        | Acceso     |
|----------------------------|----------------------------------|----------------------------------------------------|------------|
| `/embed/:username`         | EmbeddedProfile                  | Perfil embebible en otros sitios                  | Público    |
| `/embed/project/:slug`     | EmbeddedProject                  | Proyecto embebible                                 | Público    |
| `/qr/:username`            | QRProfile                        | Perfil accesible por código QR                    | Público    |
| `/share/:username`         | ShareProfile                     | Página optimizada para compartir perfil           | Público    |
| `/api-docs`                | APIDocumentation                 | Documentación de la API pública                   | Público    |
| `/status`                  | SystemStatus                     | Estado de servicios de la plataforma              | Público    |
| `/maintenance`             | MaintenancePage                  | Página de mantenimiento                            | Sistema    |

---

## Rutas de onboarding y ayuda

| Ruta                       | Página/Componente                | Descripción                                        | Roles      |
|----------------------------|----------------------------------|----------------------------------------------------|------------|
| `/welcome`                 | WelcomePage                      | Página de bienvenida para nuevos usuarios         | Usuarios   |
| `/onboarding`              | OnboardingFlow                   | Flujo de onboarding personalizado                 | Usuarios   |
| `/onboarding/professional` | ProfessionalOnboarding           | Onboarding específico para profesionales          | PROFESSIONAL |
| `/onboarding/company`      | CompanyOnboarding                | Onboarding específico para empresas               | COMPANY    |
| `/onboarding/recruiter`    | RecruiterOnboarding              | Onboarding específico para reclutadores           | RECRUITER  |
| `/getting-started`         | GettingStarted                   | Guía de primeros pasos                             | Usuarios   |
| `/tutorials`               | TutorialsCenter                  | Centro de tutoriales interactivos                 | Usuarios   |
| `/best-practices`          | BestPractices                    | Mejores prácticas para perfiles exitosos          | Usuarios   |
| `/success-stories`         | SuccessStories                   | Historias de éxito de usuarios                    | Público    |

---

## Consideraciones y buenas prácticas

- **Responsive Design:** Todas las rutas optimizadas para desktop, tablet y móvil.
- **Progressive Web App (PWA):** Funcionalidad offline para visualización de perfiles.
- **SEO Optimization:** URLs amigables, meta tags dinámicos, structured data.
- **Deep Linking:** Enlaces directos a secciones específicas de perfiles.
- **Lazy Loading:** Carga diferida de imágenes y componentes pesados.
- **Infinite Scroll:** En listados de directorio y búsquedas.
- **Real-time Updates:** Notificaciones en tiempo real para mensajes y likes.
- **Accessibility:** Cumplimiento WCAG para usuarios con discapacidades.
- **Multi-language:** Soporte para múltiples idiomas.
- **Dark Mode:** Tema oscuro para mejor experiencia visual.
- **Keyboard Navigation:** Navegación completa por teclado.
- **Social Sharing:** Integración con redes sociales para compartir perfiles.
- **Analytics Tracking:** Seguimiento de interacciones para mejorar UX.
- **Error Boundaries:** Manejo elegante de errores con fallbacks útiles.
- **Performance Monitoring:** Métricas de rendimiento en tiempo real.

---