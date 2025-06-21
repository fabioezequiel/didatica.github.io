# 馃И Flujo de Trabajo con Git y Pull Requests

Este proyecto utiliza un flujo de trabajo basado en ramas para mantener el c贸digo limpio, organizado y listo para producci贸n.



## 馃尦 Estructura de Ramas

| Rama        | Prop贸sito                                                                |
|-------------|--------------------------------------------------------------------------|
| `main`      | C贸digo listo para producci贸n; representa la versi贸n estable y final.     |
| `dev`       | Desarrollo; se integra y prueba nuevas funcionalidades antes de pasarlas a producci贸n. |
| `feature/*` | Ramas para nuevas funcionalidades; se crean desde `dev`.                 |
| `bugfix/*`  | Ramas para corregir errores detectados en la etapa de desarrollo (`dev`).  |
| `hotfix/*`  | Ramas para correcciones urgentes en producci贸n; se crean desde `main` y se fusionan en `dev` posteriormente. |


## 馃彿锔?Convenciones para nombrar Commits

Se utiliza el formato `<tipo>: <descripci贸n breve>`:



### 鉁?Nuevas Funcionalidades (`feat:`)
- `feat:add-cart`
- `feat:add-product-endpoint`
- `feat:create-auth-module`


### 馃悰 Correcci贸n de Errores (`fix:`)
- `fix:fix-login`
- `fix:fix-product-dto`
- `fix:fix-validation-error`


### 鈿?Mejoras de Rendimiento (`perf:`)
- `perf:optimize-image-loading`
- `perf:optimize-db-queries`
- `perf:reduce-bundle-size`


### 馃洜锔?Cambios en Build o Deploy (`build:`)
- `build:add-dockerfile`
- `build:configure-build-system`
- `build:setup-deploy-scripts`


### 馃 Integraci贸n Continua (`ci:`)
- `ci:setup-github-actions`
- `ci:fix-ci-build`
- `ci:update-pipeline`


### 馃摑 Documentaci贸n (`docs:`)
- `docs:update-readme`
- `docs:add-api-docs`
- `docs:update-changelog`


### 鈾伙笍 Refactorizaci贸n `(refactor:`)
- `refactor:rename-variable`
- `refactor:reorganize-services`
- `refactor:simplify-function`


### 馃帹 Estilos y Formato (`style:`)
- `style:apply-prettier`
- `style:fix-indentation`
- `style:update-code-formatting`

### 鉁?Pruebas (`test:`)
- `test:add-new-tests`
- `test:fix-failing-tests`
- `test:update-test-cases`




## 馃Х Convenciones para nombrar Ramas

Se utiliza el formato `<tipo>/<descripci贸n>`:

### 鉁?Funcionalidades Nuevas (`feature/`)

- `feature/add-cart`  
- `feature/add-product-endpoint`  
- `feature/create-auth-module`

### 馃悰 Correcci贸n de Errores en Desarrollo (`bugfix/`)

- `bugfix/fix-login`  
- `bugfix/fix-product-dto`  
- `bugfix/fix-validation-error`

### 馃毃 Parche Urgente en Producci贸n (`hotfix/`)

- `hotfix/fix-env-vars`  
- `hotfix/fix-payment-gateway`


## 馃攣 Flujo de Trabajo

### 1. Crear una Nueva Rama para la Funcionalidad o Correcci贸n

1. Desde la rama `dev`, actualiza y crea la nueva rama:

   ```bash
   git checkout dev
   git pull origin dev
   git checkout -b feature/nueva-funcionalidad
    ```
2. Realiza tus cambios, commits y sube la rama:

    ```bash 
    git push -u origin feature/nueva-funcionalidad
    ```

## 2. Crear el Pull Request (PR)
- Para funcionalidades y correcciones:
Se crea un PR desde la rama feature/* o bugfix/* hacia la rama dev.

- Validaciones del PR:
    - C贸digo limpio y sin comentarios innecesarios

    - Ausencia de archivos sensibles (por ejemplo, .env)

    - PR con nombre y descripci贸n claros

    - Pruebas locales o con tests automatizados

## 3. Integrar Cambios en Producci贸n
- Cuando la rama dev est茅 aprobada y probada, se crea un PR de dev hacia main para desplegar la versi贸n estable en producci贸n.

## 4. Manejo de Hotfixes en Producci贸n
1. Para corregir un error urgente en producci贸n:

```bash
git checkout main
git pull origin main
git checkout -b hotfix/nombre-del-hotfix
```
2. Realiza los cambios, commits y sube la rama:
```bash
git push -u origin hotfix/nombre-del-hotfix
```
3. Crea un PR de hotfix/* hacia main.

**Importante**: Una vez fusionado, integra el hotfix tambi茅n en dev para sincronizar las correcciones.
a





