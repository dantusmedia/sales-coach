# Sales Coach IA — Guía de despliegue en Vercel

## Lo que necesitas
- Una cuenta gratuita en vercel.com
- Tu API key de Anthropic (la encuentras en console.anthropic.com)

---

## Pasos (5 minutos)

### 1. Sube el proyecto a Vercel

Ve a https://vercel.com/new y elige **"Deploy from your computer"** o arrastra la carpeta entera del proyecto.

Alternativamente, si tienes la CLI instalada:
```
npx vercel --prod
```

### 2. Añade tu API key como variable de entorno

En el dashboard de Vercel, ve a tu proyecto → **Settings** → **Environment Variables** y añade:

| Nombre | Valor |
|--------|-------|
| `ANTHROPIC_API_KEY` | `sk-ant-api03-TUKEY...` |

### 3. Redespliega

Después de añadir la variable, haz clic en **Redeploy** en el dashboard.

### 4. Comparte la URL

Vercel te da una URL pública tipo `https://sales-coach-xxx.vercel.app`. Esa es la que compartes.

---

## Estructura del proyecto

```
sales-coach/
├── api/
│   └── chat.js        ← función serverless (aquí vive tu API key, segura)
├── public/
│   └── index.html     ← la app que ven tus usuarios
└── vercel.json        ← configuración de rutas
```

---

## Costes estimados

- Vercel: **gratis** (plan hobby)
- Anthropic: aproximadamente **$0.003 por conversación completa** con claude-sonnet

Si tienes 100 usuarios al día haciendo 10 turnos cada uno → ~$3/día.
Puedes poner un límite de gasto en console.anthropic.com → Billing → Usage limits.
