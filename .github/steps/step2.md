## Paso 2 de 3 — Corregir las vulnerabilidades detectadas

¡Semgrep ha analizado tu código! 🔍

### Qué encontró Semgrep

Abre la pestaña **Actions** y revisa el último run de "SAST con Semgrep".  
Semgrep habrá detectado estas vulnerabilidades en `src/app.py`:

| # | Vulnerabilidad | Tipo | Línea aprox. |
|---|---------------|------|--------------|
| 1 | Credenciales hardcodeadas | Secrets | ~9-10 |
| 2 | SQL Injection | Inyección | ~19 |
| 3 | Command Injection (`os.system`) | Inyección | ~27 |

### Tu tarea

Abre `src/app.py` y aplica las siguientes tres correcciones:

---

#### Corrección 1 — Eliminar credenciales hardcodeadas

```python
# ❌ ANTES (vulnerable)
DB_PASSWORD = "admin123"
API_KEY = "sk-prod-abc123xyz789"

# ✅ DESPUÉS (seguro)
import os
DB_PASSWORD = os.environ.get("DB_PASSWORD", "")
API_KEY = os.environ.get("API_KEY", "")
```

---

#### Corrección 2 — SQL Injection → consulta parametrizada

```python
# ❌ ANTES (vulnerable)
query = "SELECT * FROM users WHERE name = '" + username + "'"
cursor.execute(query)

# ✅ DESPUÉS (seguro)
query = "SELECT * FROM users WHERE name = ?"
cursor.execute(query, (username,))
```

---

#### Corrección 3 — Command Injection → subprocess con lista de argumentos

```python
# ❌ ANTES (vulnerable)
os.system("ping -c 1 " + host)

# ✅ DESPUÉS (seguro)
import subprocess
subprocess.run(["ping", "-c", "1", host], check=True)
```

---

### Una vez aplicadas las correcciones

Haz push de los cambios:

```bash
git add src/app.py
git commit -m "fix: remediate SQL injection, command injection and hardcoded secrets"
git push
```

O desde la interfaz web: edita `src/app.py` directamente y haz commit en `main`.

El workflow verificará que las tres vulnerabilidades han sido corregidas y este README se actualizará al **Paso 3** ✅

---
*Paso 2 de 3 · Tutorial de Seguridad en Pipelines*
