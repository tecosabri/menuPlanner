# Guía de Contribución: Protocolo GitFlow

Este repositorio sigue una metodología estricta **GitFlow**.

## 🌲 Estructura de Ramas

| Rama | Propósito | Reglas |
|------|-----------|--------|
| `main` | **Producción**. Código estable y versionado. | ⛔️ Prohibido commit directo. Solo merges desde `develop` (release) o `hotfix`. |
| `develop` | **Integración**. Próximo release. | ⛔️ Prohibido commit directo. Solo PRs desde `feature/*`. |
| `feature/*` | Nuevas funcionalidades. | Nace de: `develop`. Merge a: `develop`. |
| `release/*` | Preparación de versión. | Nace de: `develop`. Merge a: `main` y `develop`. |
| `hotfix/*` | Parches urgentes en prod. | Nace de: `main`. Merge a: `main` y `develop`. |

## 🚀 Flujo de Trabajo

### 1. Iniciar una Feature
Siempre crea una rama descriptiva desde `develop`:
\`\`\`bash
git checkout develop
git pull origin develop
git checkout -b feature/nueva-funcionalidad
\`\`\`

### 2. Finalizar una Feature
1.  Sube tus cambios: `git push origin feature/nueva-funcionalidad`.
2.  Abre un **Pull Request** hacia \`develop\`.
3.  **Revisión requerida**: Al menos 1 aprobación.
4.  **Merge**: Usar "Squash and Merge" o "Merge commit" (No-FF) para mantener historia limpia.

### 3. Releases y Tags
El versionado se maneja mediante Tags en `main` (ej: `v1.0.0`) tras fusionar una rama de `release/*`.

---
**Nota**: Cualquier commit directo a `main` o `develop` será rechazado por las reglas de protección.
