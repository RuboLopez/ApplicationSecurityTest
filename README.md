## Paso 3 de 3 — Configurar Dependabot

¡Las vulnerabilidades del código están corregidas! 🛡️

### Contexto

El archivo `requirements.txt` tiene dependencias con versiones antiguas que contienen vulnerabilidades conocidas.  
**Dependabot** monitoriza las dependencias de tu proyecto y abre Pull Requests automáticos cuando hay versiones más seguras disponibles.

### Tu tarea

Crea el archivo `.github/dependabot.yml` con el siguiente contenido:

```yaml
version: 2
updates:
  - package-ecosystem: pip
    directory: "/"
    schedule:
      interval: weekly
    open-pull-requests-limit: 5
    labels:
      - "dependencies"
      - "security"
```

### Cómo hacerlo

**Opción A — Desde la interfaz web:**
1. Ve a tu repositorio → **Add file** → **Create new file**
2. Nombre del archivo: `.github/dependabot.yml`
3. Pega el contenido de arriba
4. Haz click en **Commit changes** → **Commit directly to the `main` branch**

**Opción B — Desde la terminal:**
```bash
# crea .github/dependabot.yml con el contenido de arriba
git add .github/dependabot.yml
git commit -m "ci: enable Dependabot for Python dependencies"
git push
```

### ¿Qué pasará?

- Dependabot comenzará a monitorizar `requirements.txt`
- En las próximas horas abrirá PRs para actualizar `flask` y `requests` a versiones seguras
- Si el repositorio es público verás las alertas en **Security → Dependabot alerts**

Este README se actualizará a **¡Completado!** en cuanto detecte el archivo ✅

---
*Paso 3 de 3 · Tutorial de Seguridad en Pipelines*
