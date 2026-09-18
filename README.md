# Documentos verificables

Skill para crear y revisar documentos factuales sin convertir suposiciones en hechos. Cuando un dato no está respaldado, es ambiguo, contradictorio o solo aparece como previsión, la skill exige marcarlo con el formato exacto `[VERIFICAR: ...]` y acompañar el documento con una lista de comprobación.

> **Importante:** esta skill proporciona instrucciones de comportamiento al agente. No verifica automáticamente cada afirmación, no comprueba por sí sola que una URL exista y no bloquea de forma mecánica una salida incorrecta. Para flujos regulados o de alto riesgo, combínala con revisión humana y validaciones deterministas.

El repositorio publica `SKILL.md` y `VALIDACION.md` de forma visible para facilitar la inspección y la instalación desde GitHub. El archivo `documentos-verificables.skill` es un paquete comprimido opcional que contiene esos mismos archivos.

## Qué contiene

El archivo [`SKILL.md`](SKILL.md) define un protocolo para:

- distinguir datos aportados, derivados, conocimiento estable y datos ausentes;
- conservar literalmente las cifras y el texto de las fuentes;
- separar previsiones de hechos;
- señalar contradicciones sin resolverlas en silencio;
- no inventar citas, referencias, URLs, identificadores, fechas, precios ni versiones;
- entregar el documento junto con una lista de verificación;
- propagar las marcas `[VERIFICAR: ...]` como tokens inmutables.

## Instalación rápida

Clone o descargue este repositorio y copie `SKILL.md` en la ubicación del ecosistema que utilice. Sustituya `/ruta/al/repositorio-documentos-verificables` por la ruta local real:

```bash
SKILL_SOURCE="/ruta/al/repositorio-documentos-verificables/SKILL.md"

# Elija una o varias ubicaciones según su ecosistema.
mkdir -p .claude/skills/documentos-verificables
cp "$SKILL_SOURCE" .claude/skills/documentos-verificables/SKILL.md
```

También puede descargar `documentos-verificables.skill` como paquete distribuible. Para modificar o revisar la skill, use preferentemente el `SKILL.md` visible en el repositorio.

Versione la carpeta específica del ecosistema junto con el proyecto. No copie la misma skill en varias rutas del mismo agente sin entender la precedencia: podría cargarse una versión distinta de la que espera.

## Claude Code

Claude Code admite skills nativas con un archivo `SKILL.md` y frontmatter YAML. Para una skill compartida por un repositorio:

```bash
mkdir -p .claude/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .claude/skills/documentos-verificables/SKILL.md
```

Dentro de Claude Code, invoque la skill explícitamente cuando quiera máxima previsibilidad:

```text
/documentos-verificables
```

Después, pida la tarea documental. Claude también puede cargarla automáticamente cuando la descripción del frontmatter coincide con la petición. No use `disable-model-invocation: true` si desea conservar esa activación automática.

Si la regla debe aplicarse a todas las conversaciones del proyecto, añada además una versión breve en `CLAUDE.md` o `.claude/CLAUDE.md`. Mantenga esa regla concisa; la skill detallada debe permanecer en `SKILL.md`.

Referencias oficiales: [skills de Claude Code][1], [memoria e instrucciones persistentes][2] y [hooks][3].

## GitHub Copilot

GitHub Copilot admite agent skills con `SKILL.md`. Para una skill de proyecto:

```bash
mkdir -p .github/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .github/skills/documentos-verificables/SKILL.md
```

En Copilot CLI puede actualizar y consultar las skills de la sesión:

```text
/skills reload
/skills list
/skills info documentos-verificables
```

La carga es selectiva: Copilot decide si la descripción de la skill coincide con la tarea. Si la política debe estar presente en cada solicitud del repositorio, añada también una versión resumida en:

```text
.github/copilot-instructions.md
```

Ese archivo es una instrucción persistente de repositorio; no sustituye el empaquetado completo de la skill.

Si el repositorio publica la skill y se utiliza GitHub CLI compatible, GitHub documenta también la instalación desde otro repositorio con `gh skill install`. Revise primero el contenido de una skill de terceros y tenga presente que una skill puede incluir instrucciones o scripts no confiables:

```bash
gh skill preview PROPIETARIO/REPOSITORIO documentos-verificables
gh skill install PROPIETARIO/REPOSITORIO documentos-verificables
```

El subcomando `gh skill` está sujeto a la disponibilidad y versión de GitHub CLI. Referencias: [agent skills de GitHub Copilot][4], [skills en Copilot CLI][5], [instrucciones de repositorio][6] y [referencia de `gh skill install`][7].

## Cursor

Cursor admite Agent Skills y reglas de proyecto. Para una skill versionada en el repositorio:

```bash
mkdir -p .cursor/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .cursor/skills/documentos-verificables/SKILL.md
```

En Agent Chat puede solicitarla explícitamente con:

```text
/documentos-verificables
```

Por defecto, Cursor decide si una skill es relevante a partir de su descripción. Si necesita una política siempre activa, cree una regla separada, por ejemplo `.cursor/rules/documentos-verificables.mdc`, con instrucciones breves y `alwaysApply: true` en el frontmatter. Una regla siempre activa es un mecanismo distinto de una skill y consume contexto en cada conversación.

Referencias: [Agent Skills de Cursor][8], [Project Rules][9] y [prompting del agente][10].

## Cline

Cline admite skills y reglas de proyecto. Para instalar esta skill en un workspace:

```bash
mkdir -p .cline/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .cline/skills/documentos-verificables/SKILL.md
```

También puede crearla desde el panel **Skills** de Cline. Para invocarla explícitamente, escriba `/` en el chat y seleccione `documentos-verificables`. Cline puede activarla automáticamente cuando la descripción coincide con la petición.

Las skills son selectivas. Si la regla debe aplicarse en todas las conversaciones, use una regla de workspace en `.clinerules/`, por ejemplo:

```bash
mkdir -p .clinerules
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .clinerules/documentos-verificables.md
```

En ese caso, elimine el frontmatter específico de skill si no lo necesita y conserve solo una versión breve de la política. Cline carga las reglas de `.clinerules/` como instrucciones persistentes, mientras que `SKILL.md` se reserva para conocimiento bajo demanda.

Referencias: [skills de Cline][11] y [reglas de Cline][12].

## Windsurf / Cascade

Windsurf admite skills de workspace en `.windsurf/skills/`:

```bash
mkdir -p .windsurf/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .windsurf/skills/documentos-verificables/SKILL.md
```

En Cascade puede invocarla explícitamente mencionando:

```text
@documentos-verificables
```

Cascade también puede cargarla cuando considera que la descripción es pertinente. Para aplicar una pauta en cada mensaje, use una Rule de workspace con el mecanismo `always_on` documentado por Windsurf, o un `AGENTS.md` en la raíz. No presente esa Rule o `AGENTS.md` como sustitutos equivalentes de una skill: son instrucciones persistentes y no ofrecen el mismo empaquetado ni la misma carga bajo demanda.

Referencias: [skills de Cascade][13], [memorias y reglas][14] y [AGENTS.md][15].

## Gemini CLI

Gemini CLI admite Agent Skills basadas en el estándar abierto Agent Skills. Para compartir la skill con un equipo:

```bash
mkdir -p .gemini/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .gemini/skills/documentos-verificables/SKILL.md
```

Como alternativa interoperable, la documentación también reconoce `.agents/skills/`:

```bash
mkdir -p .agents/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .agents/skills/documentos-verificables/SKILL.md
```

Consulte y gestione las skills desde Gemini CLI:

```text
/skills list
/skills reload
```

La interfaz puede pedir consentimiento antes de activar una skill y conceder acceso a sus archivos auxiliares. Para instalar desde un repositorio Git, Gemini CLI documenta `gemini skills install`; revise el contenido antes de aceptar la instalación:

```bash
gemini skills install https://github.com/PROPIETARIO/REPOSITORIO.git \
  --path documentos-verificables --scope workspace
```

La misma documentación describe `GEMINI.md` como contexto persistente. Si la política debe cargarse en cada prompt, añada una versión breve a `GEMINI.md` en la raíz del proyecto; mantenga el procedimiento completo en `SKILL.md`.

> La documentación consultada indica una transición de Gemini CLI a Antigravity CLI para determinados usuarios y planes desde el 18 de junio de 2026. Compruebe qué producto y comandos están disponibles en su instalación antes de automatizar esta integración.

Referencias: [Agent Skills de Gemini CLI][16], [contexto mediante `GEMINI.md`][17] y [extensiones de Gemini CLI][18].

## Opción interoperable: `.agents/skills/`

Varios ecosistemas modernos reconocen `.agents/skills/` como alias interoperable. Si el equipo usa herramientas compatibles, puede mantener una única copia versionada:

```bash
mkdir -p .agents/skills/documentos-verificables
cp /ruta/al/repositorio-documentos-verificables/SKILL.md \
  .agents/skills/documentos-verificables/SKILL.md
```

Compruebe la documentación y la precedencia de su herramienta antes de eliminar las rutas nativas. Cuando haya dudas, la ruta específica de cada ecosistema documentada arriba es más explícita y fácil de depurar.

## Uso recomendado

La activación explícita es preferible cuando el resultado vaya a publicarse, enviarse, firmarse o alimentar a otro agente:

```text
Usa la skill documentos-verificables. Redacta el documento solo con los datos de las fuentes aportadas. Marca cada dato ausente o no resuelto exactamente como [VERIFICAR: ...] y entrega una lista de verificación separada.
```

La skill no autoriza a completar huecos con conocimiento general. Si se necesita una investigación externa, pida expresamente la búsqueda y conserve la diferencia entre datos encontrados, datos derivados y candidatos pendientes de confirmación.

## Estructura recomendada del repositorio

Si se quiere mantener el repositorio neutral respecto del agente, una estructura útil es:

```text
.
├── SKILL.md
├── VALIDACION.md
├── README.md
├── LICENSE
└── documentos-verificables.skill  # paquete opcional
```

Si se desea probar la skill en varios entornos dentro de un mismo repositorio, añada solo los adaptadores que el equipo haya decidido soportar:

```text
.
├── .agents/skills/documentos-verificables/SKILL.md
├── .claude/skills/documentos-verificables/SKILL.md
├── .cline/skills/documentos-verificables/SKILL.md
├── .cursor/skills/documentos-verificables/SKILL.md
├── .gemini/skills/documentos-verificables/SKILL.md
├── .github/skills/documentos-verificables/SKILL.md
└── .windsurf/skills/documentos-verificables/SKILL.md
```

Evite duplicar archivos si no es necesario. Si mantiene copias en varias rutas, actualícelas juntas y compruebe que sus contenidos son idénticos.

## Limitaciones y seguridad

Las skills son instrucciones para un modelo. No son un sistema de control de acceso, una auditoría de fuentes ni una garantía de exactitud. Inspeccione cualquier `SKILL.md` de terceros antes de instalarlo, especialmente si incluye scripts, comandos, herramientas externas o permisos de lectura y escritura. No habilite scripts o herramientas privilegiadas solo para utilizar esta skill: el procedimiento de documentos verificables no los necesita.

## Licencia

Este repositorio se distribuye bajo la licencia MIT. Consulte el archivo [`LICENSE`](LICENSE).

## Referencias

[1]: https://docs.anthropic.com/en/docs/claude-code/skills "Claude Code skills"
[2]: https://docs.anthropic.com/en/docs/claude-code/memory "Claude Code memory and project instructions"
[3]: https://docs.anthropic.com/en/docs/claude-code/hooks-guide "Claude Code hooks"
[4]: https://docs.github.com/en/copilot/concepts/agents/about-agent-skills "About agent skills in GitHub Copilot"
[5]: https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/add-skills "Add skills to GitHub Copilot CLI"
[6]: https://docs.github.com/en/copilot/how-tos/configure-custom-instructions-in-your-ide/add-repository-instructions-in-your-ide "Add repository instructions for GitHub Copilot"
[7]: https://cli.github.com/manual/gh_skill_install "GitHub CLI gh skill install"
[8]: https://cursor.com/docs/skills "Cursor Agent Skills"
[9]: https://cursor.com/docs/rules "Cursor project rules"
[10]: https://cursor.com/docs/agent/prompting "Cursor agent prompting"
[11]: https://docs.cline.bot/customization/skills "Cline skills"
[12]: https://docs.cline.bot/customization/cline-rules "Cline rules"
[13]: https://docs.windsurf.com/windsurf/cascade/skills "Windsurf Cascade skills"
[14]: https://docs.windsurf.com/windsurf/cascade/memories "Windsurf Cascade memories and rules"
[15]: https://docs.windsurf.com/windsurf/cascade/agents-md "Windsurf AGENTS.md"
[16]: https://geminicli.com/docs/cli/skills/ "Gemini CLI Agent Skills"
[17]: https://geminicli.com/docs/cli/gemini-md/ "Gemini CLI GEMINI.md context"
[18]: https://geminicli.com/docs/extensions/writing-extensions/ "Gemini CLI extensions"
