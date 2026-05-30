## Paso 1 de 3 — Añadir análisis SAST con Semgrep

¡El tutorial ha comenzado! 🎉

### Contexto

Este repositorio incluye el archivo `src/app.py` con tres vulnerabilidades de seguridad y las reglas Semgrep para detectarlas en `.semgrep/rules.yml`.

En este paso añadirás un **workflow de análisis estático (SAST)** para que Semgrep analice el código automáticamente en cada push.

### Tu tarea

Crea el archivo `.github/workflows/sast.yml` con el siguiente contenido:

```yaml
name: SAST con Semgrep
on:
  push:
    branches: [main]
  pull_request:

permissions:
  contents: read

jobs:
  semgrep:
    name: Análisis estático
    runs-on: ubuntu-latest
    container:
      image: semgrep/semgrep
    steps:
      - uses: actions/checkout@v4
      - run: semgrep scan --config=.semgrep/rules.yml --error src/
```

### Cómo hacerlo

**Opción A — Desde la interfaz web de GitHub:**
1. Ve a tu repositorio → **Add file** → **Create new file**
2. Nombre del archivo: `.github/workflows/sast.yml`
3. Pega el contenido de arriba
4. Haz click en **Commit changes** → **Commit directly to the `main` branch**

**Opción B — Desde la terminal:**
```bash
mkdir -p .github/workflows
# crea .github/workflows/sast.yml con el contenido de arriba
git add .github/workflows/sast.yml
git commit -m "ci: add Semgrep SAST workflow"
git push
```

### ¿Qué pasará?

Cuando hagas push de `sast.yml`:
- Semgrep analizará `src/app.py` con las reglas de `.semgrep/rules.yml`
- Encontrará **3 vulnerabilidades** — eso es lo esperado
- El workflow **fallará** (❌) porque existen hallazgos
- Verás los resultados en **Actions** → click en el run → click en el job `semgrep`
- Este README se actualizará al **Paso 2** ✅

> Si el workflow no aparece en Actions, ve a **Settings → Actions → Allow all actions** y vuelve a hacer push.

---
*Paso 1 de 3 · Tutorial de Seguridad en Pipelines*
