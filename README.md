# 🎨 Login React + TypeScript + Vite

¡Bienvenido!  
Este proyecto es una plantilla elegante y funcional para un **login básico** con React, TypeScript y Vite.  
Está lista para que la personalices y escales según tus necesidades.

---

## ✨ Características destacadas

- 🔑 Formulario de inicio de sesión listo para usarse  
- ⚡ Configuración mínima y rápida con **Vite + React + HMR**  
- 📏 **ESLint + TypeScript** preconfigurados  
- 🎨 Integración con **Tailwind CSS** (o el CSS que prefieras)  
- 🧩 Estructura modular fácil de escalar  
- 🚀 Compatibilidad con **@vitejs/plugin-react** (Babel) y **@vitejs/plugin-react-swc** (SWC) para Fast Refresh  

---

## 🚀 Cómo empezar

### Clonar e instalar dependencias

```bash
git clone https://github.com/Wizar-Cyber/Login-React-TypeScript-Vite.git
cd Login-React-TypeScript-Vite
npm install
# o yarn install / pnpm install
````
Modo desarrollo
````
npm run dev
````
Abre en tu navegador: http://localhost:5173

Producción
````
npm run build
npm run preview
````
🗂 Estructura recomendada

````
public/
src/
 ├── components/      # Componentes reutilizables (Input, Button, LoginForm, etc.)
 ├── pages/           # Vistas o rutas del proyecto
 ├── App.tsx          # Componente raíz
 └── main.tsx         # Punto de entrada
vite.config.ts        # Configuración de Vite
tailwind.config.js    # Configuración de estilos (si usas Tailwind)
eslint.config.js      # Reglas de lint
tsconfig.*.json       # Configuración de TypeScript
````
👩‍💻 Configuración avanzada de ESLint
Para entornos de producción, se recomienda aprovechar las capacidades de TypeScript + ESLint.

1. Parser Options
En eslint.config.js configura parserOptions:
````
js
Copiar código
export default tseslint.config({
  languageOptions: {
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
````
2. Reglas con tipos
````
Reemplaza tseslint.configs.recommended por:

tseslint.configs.recommendedTypeChecked o

tseslint.configs.strictTypeChecked

Opcional: añade ...tseslint.configs.stylisticTypeChecked para incluir reglas de estilo.
````
3. eslint-plugin-react
Instala y configura el plugin oficial de React:
````
npm install eslint-plugin-react --save-dev
````
En eslint.config.js:
````
js
import react from 'eslint-plugin-react'

export default tseslint.config({
  settings: { react: { version: '18.3' } },
  plugins: { react },
  rules: {
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
````
📌 Notas finales
Puedes cambiar Tailwind por tu framework de estilos favorito.

Si necesitas un entorno más complejo, amplía la configuración con Redux, React Query, Zustand, etc.

Este boilerplate busca ser minimalista pero listo para producción.
