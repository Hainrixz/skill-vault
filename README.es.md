# Skill Vault

**Tu biblioteca personal de skills para Claude Code.**

[Read this in English](README.md)

---

## ¿Qué es esto?

Imagina que tienes una caja grande de juguetes, pero en lugar de juguetes, guarda **skills** — habilidades especiales que hacen a Claude Code más inteligente.

La gente comparte miles de skills en internet todos los días. ¿El problema? Están regados por todos lados. Encuentras uno en GitHub, otro en skills.sh, otro que alguien compartió en X... y luego olvidas dónde los guardaste. O peor — algunos pueden ser dañinos.

**Skill Vault** es tu caja de juguetes organizada y segura para skills. Hace tres cosas:

1. **Guarda y organiza** tus skills en carpetas etiquetadas
2. **Revisa cada skill** antes de guardarlo (como un guardia de seguridad para tu computadora)
3. **Te ayuda a encontrar el skill correcto** cuando estás construyendo algo

Eso es todo. Clónalo, ábrelo con Claude, y empieza a coleccionar.

---

## Cómo Empezar

```bash
git clone https://github.com/Hainrixz/skill-vault.git
cd skill-vault
claude
```

Sin instalaciones. Sin configuración. Sin dependencias. Solo ábrelo y listo.

---

## Cómo Funciona

Cuando abres este proyecto con Claude Code, el agente **Vault Master** toma el control. Piensa en él como tu bibliotecario personal que:

- **Acepta skills** de cualquier lugar — pega una URL, pega el contenido, o solo dile el nombre
- **Analiza cada skill** con una lista de verificación de seguridad de 13 puntos y lo califica: SEGURO, PRECAUCIÓN o PELIGROSO
- **Lo archiva** en la carpeta de categoría correcta automáticamente
- **Encuentra skills para ti** cuando describes lo que estás construyendo

### Comandos

| Comando | ¿Qué hace? |
|---------|------------|
| `/vault-add` | Guardar un nuevo skill (desde URL, contenido pegado, o nombre) |
| `/vault-search` | Buscar en tu vault por palabra clave |
| `/vault-recommend` | Describe tu proyecto, recibe skills que te sirvan |
| `/vault-discover` | Encontrar nuevos skills en internet |
| `/vault-list` | Ver todo lo que hay en tu vault |
| `/vault-stats` | Estadísticas del vault + verificación de salud |
| `/vault-remove` | Eliminar un skill |

---

## Estructura de Carpetas

Los skills se guardan en carpetas por categoría. Cada skill tiene su propio archivo con metadata, análisis de seguridad, instrucciones de instalación y el contenido original preservado.

```
categories/
├── automation/          # Bots de navegador, scripts, automatizaciones
├── code-quality/        # Linting, refactorización, revisiones
├── design-ui/           # Componentes UI, sistemas de diseño, CSS
├── devops-deploy/       # Docker, CI/CD, infraestructura
├── documentation/       # READMEs, docs de API, changelogs
├── organization/        # Gestión de proyectos, planificación
├── productivity/        # Herramientas de texto, notas, flujos de trabajo
├── research/            # Investigación web, recopilación de datos
├── testing/             # Tests unitarios, E2E, QA
└── web-development/     # React, Next.js, Vue, APIs
```

¿No ves una categoría que encaje? El Vault Master crea nuevas automáticamente.

---

## Seguridad

Cada skill es escaneado antes de entrar a tu vault. El Vault Master revisa:

- Comandos peligrosos (`rm -rf`, ejecución pipe-to-shell)
- Robo de credenciales (lectura de llaves SSH, tokens de AWS, API keys)
- Exfiltración de datos (envío de tus archivos a servidores externos)
- Código ofuscado (payloads ocultos en base64 o hex)
- Permisos excesivamente amplios
- Intentos de inyección de prompts

| Calificación | ¿Qué significa? |
|--------------|-----------------|
| **SEGURO** | Limpio — no se detectaron operaciones riesgosas |
| **PRECAUCIÓN** | Algo de riesgo — revisa los hallazgos antes de usar |
| **PELIGROSO** | Bandera roja — se te advertirá antes de guardarlo |

Metodología completa en [`security-rubric.md`](security-rubric.md).

---

## Ejemplo de Uso

```
Tú:     /vault-add https://github.com/anthropics/skills/tree/main/skill-creator
Vault:  Analizando skill... Calificación: SEGURO
        Guardado en: categories/productivity/skill-creator.md
        Agregado al catálogo.

Tú:     /vault-recommend Estoy construyendo una app e-commerce con Next.js
Vault:  De tu vault, te recomiendo:
        - shadcn-ui (design-ui) [SEGURO] — Componentes UI
        - playwright-cli (testing) [PRECAUCIÓN] — Testing E2E
        - vercel-deploy (devops-deploy) [SEGURO] — Despliegue

Tú:     /vault-discover optimización SEO
Vault:  Encontré 3 skills en skills.sh:
        - seo-audit [SEGURO] — Análisis SEO técnico
        - meta-tags-generator [SEGURO] — Meta tags automáticos
        ¿Agregar alguno? (s/n)
```

---

## Contribuir

1. Haz fork de este repo
2. Agrega skills con `/vault-add` o crea entradas manualmente en `categories/` usando la plantilla en `templates/skill-entry.md`
3. Envía un PR

---

## Creado por

[Todo de IA](https://todoia.com) por [@soyenriquerocha](https://instagram.com/soyenriquerocha) — Construyendo herramientas para la comunidad de IA.

## Licencia

MIT
