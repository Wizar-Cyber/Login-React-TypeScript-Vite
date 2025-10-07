
# 🎨 Login React + TypeScript + Vite

¡Bienvenido! Este proyecto es una plantilla elegante y funcional para un **login básico** con React, TypeScript y Vite, lista para que la personalices a tu gusto.

---

## ✨ Características destacadas

- Formulario de inicio de sesión listo para usarse  
- Configuración con Vite + React + HMR  
- ESLint + TypeScript preconfigurados  
- Integración con Tailwind CSS (o tu CSS favorito)  
- Estructura modular fácil de escalar  

---

## 🚀 Cómo empezar

```bash
# Clona el repositorio
git clone https://github.com/Wizar-Cyber/Login-React-TypeScript-Vite.git
```
# Entra al folder del proyecto
```bash
cd Login-React-TypeScript-Vite
```
# Instala dependencias
```bash
npm install
# o yarn install / pnpm install
````

Para desarrollo:
```bash
npm run dev
```

Visita en tu navegador: http://localhost:5173

Para producción:
```bash
npm run build
npm run preview
````
🗂 Estructura recomendada
```bash
public/  
src/
 ├── components/     # Componentes reutilizables (Input, Button, LoginForm, etc.)
 ├── pages/          # Vistas o rutas del proyecto
 ├── App.tsx         # Componente raíz
 └── main.tsx        # Punto de entrada
vite.config.ts       # Configuración de Vite
tailwind.config.js   # Configuración de estilos (si usas Tailwind)
eslint.config.js     # Reglas de lint
tsconfig.*.json      # Configuración de TypeScript
````
👩‍💻 Mejora de ESLint para producción

Para que ESLint aproveche los tipos:

En eslint.config.js, asegúrate de que parserOptions.project incluya tsconfig.node.json y tsconfig.app.json

Cambia tseslint.configs.recommended por recommendedTypeChecked o strictTypeChecked

Puedes sumar ...tseslint.configs.stylisticTypeChecked para reglas de estilo

Instala y configura eslint-plugin-react con sus reglas recomendadas:
```bash
import react from 'eslint-plugin-react'

export default tseslint.config({
  settings: { react: { version: '18.x' } },
  plugins: { react },
  rules: {
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})

