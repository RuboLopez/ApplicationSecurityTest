## ¡Tutorial completado! 🎉

¡Enhorabuena! Has completado los tres pasos del tutorial de seguridad en pipelines de GitHub Actions.

### Lo que has aprendido

| ✅ | Habilidad adquirida |
|---|---|
| ✅ | Configurar un workflow de **SAST con Semgrep** en GitHub Actions |
| ✅ | Identificar y corregir **SQL Injection** en código Python |
| ✅ | Identificar y corregir **Command Injection** con `os.system` |
| ✅ | Eliminar **credenciales hardcodeadas** del código fuente |
| ✅ | Activar **Dependabot** para monitorizar dependencias vulnerables |

### Conceptos clave

- **SAST** — Static Application Security Testing: análisis del código fuente sin ejecutarlo
- **SCA** — Software Composition Analysis: análisis de dependencias de terceros
- **SQL Injection** — el input del usuario se inyecta directamente en una consulta SQL; se evita con parámetros `?`
- **Command Injection** — el input llega a `os.system()` permitiendo ejecutar comandos arbitrarios; se evita con `subprocess.run(list)`
- **Hardcoded secrets** — credenciales en el código que pueden filtrarse en el historial de git; se usan variables de entorno en su lugar

### Añade tu badge al perfil de GitHub

Copia este badge y pégalo en el `README.md` de tu repositorio de perfil (`tu-usuario/tu-usuario`):

```markdown
![Security Pipeline Tutorial](https://img.shields.io/badge/Security_Pipeline_Tutorial-Completado_%E2%9C%85-4caf50?style=flat-square&logo=githubactions&logoColor=white)
```

Resultado: ![Security Pipeline Tutorial](https://img.shields.io/badge/Security_Pipeline_Tutorial-Completado_%E2%9C%85-4caf50?style=flat-square&logo=githubactions&logoColor=white)

> Ve a `github.com/tu-usuario/tu-usuario` (o créalo si no existe) y edita el `README.md` para añadirlo.

### ¿Listo para el siguiente nivel?

Has dominado los fundamentos. El siguiente tutorial cubre 10 disciplinas de DevSecOps de nivel enterprise:

| # | Disciplina | Herramienta |
|---|---|---|
| 1-2 | SAST + CI/CD Hardening | Semgrep, permisos mínimos |
| 3-4 | Container Scan + Fix | Trivy, Dockerfile hardening |
| 5-6 | IaC Scan + Fix | Checkov, Terraform |
| 7 | Secrets Detection | gitleaks |
| 8-9 | Falsos Positivos + Excepciones | nosemgrep, governance YAML |
| 10 | SBOM + Supply Chain | Syft, Grype |

**[🚀 Continuar con el Tutorial Avanzado de DevSecOps — 10 pasos](https://github.com/jgutierrezdtt/advanced-devsecops-tutorial)**

---

### Próximos pasos recomendados

1. **Activa Dependabot en tus repos reales** — revisa Security → Dependabot alerts
2. **Explora más reglas de Semgrep** — prueba `p/owasp-top-ten` o `p/django` según tu stack
3. **Prueba CodeQL** — análisis semántico más profundo disponible con GitHub Advanced Security
4. **Consulta el repo de pipelines** — workflows reutilizables de seguridad para toda la organización

---
*Tutorial completado · Seguridad en Pipelines de GitHub Actions*
