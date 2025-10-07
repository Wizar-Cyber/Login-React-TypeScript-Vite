🎨 Login React + TypeScript + Vite
¡Bienvenido! 👋
Este proyecto es una plantilla de inicio optimizada para crear un login básico con React y TypeScript. Está configurado sobre Vite para ofrecer una experiencia de desarrollo ultrarrápida con HMR (Hot Module Replacement).

✨ Características destacadas
Formulario de Login: Listo para usar y personalizar.

Entorno de Desarrollo Rápido: Configurado con Vite y React. Puedes elegir entre:

@vitejs/plugin-react (usa Babel).

@vitejs/plugin-react-swc (usa SWC para una compilación aún más rápida).

TypeScript y ESLint: Preconfigurados para un código limpio y seguro.

Tailwind CSS: Integrado para un estilizado moderno y eficiente.

Estructura Modular: Organizado de forma intuitiva para escalar tu proyecto fácilmente.

🚀 Cómo empezar
1. Clonar e Instalar Dependencias
```Bash

git clone https://github.com/Wizar-Cyber/Login-React-TypeScript-Vite.git
cd Login-React-TypeScript-Vite
npm install
# o yarn install / pnpm install
````
2. Modo Desarrollo
Ejecuta el siguiente comando para iniciar el servidor de desarrollo:

```
npm run dev
```
Luego, abre tu navegador en http://localhost:5173.

3. Build de Producción
Para compilar y previsualizar la versión final de tu aplicación:
```
npm run build
npm run preview
```
🗂 Estructura de Archivos Recomendada
```
public/
src/
 ├── components/    # Componentes reutilizables (Input, Button, etc.)
 ├── pages/         # Vistas o rutas del proyecto
 ├── App.tsx        # Componente raíz
 └── main.tsx       # Punto de entrada de la aplicación
vite.config.ts      # Configuración de Vite
tailwind.config.js  # Configuración de estilos de Tailwind
eslint.config.js    # Reglas y configuración de ESLint
tsconfig.*.json     # Configuración de TypeScript
```
👩‍💻 Ampliando la Configuración de ESLint
Para una aplicación de producción, se recomienda habilitar reglas de ESLint que reconozcan tipos para un análisis de código más profundo. Sigue estos pasos en tu archivo eslint.config.js:

1. Habilitar el Reconocimiento de Tipos
Configura la propiedad parserOptions para que ESLint sepa dónde encontrar la configuración de tu proyecto TypeScript.
````
#JavaScript

// eslint.config.js
import tseslint from 'typescript-eslint';

export default tseslint.config({
  languageOptions: {
    parserOptions: {
      project: ['./tsconfig.json', './tsconfig.node.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
});
````
2. Activar Reglas Basadas en Tipos
Reemplaza la configuración base tseslint.configs.recommended por una de las siguientes opciones:

tseslint.configs.recommendedTypeChecked: Set de reglas recomendadas basadas en tipos.

tseslint.configs.strictTypeChecked: Reglas aún más estrictas.

Opcional: Añade ...tseslint.configs.stylisticTypeChecked para reglas de estilo.

3. Integrar ESLint con React
Instala eslint-plugin-react y actualiza tu configuración para incluir sus reglas recomendadas, asegurándote de especificar tu versión de React.
```
#JavaScript

// eslint.config.js
import react from 'eslint-plugin-react';
import tseslint from 'typescript-eslint';

export default tseslint.config(
  // ...otras configuraciones que ya tengas
  {
    files: ['**/*.{js,mjs,cjs,jsx,mjsx,ts,tsx}'],
    settings: {
      react: { version: '18.2' } // Especifica tu versión de React
    },
    plugins: {
      react,
    },
    rules: {
      // Activa las reglas recomendadas del plugin de React
      ...react.configs.recommended.rules,
      ...react.configs['jsx-runtime'].rules,
      // Aquí puedes añadir o sobreescribir otras reglas
    },
  }
);
