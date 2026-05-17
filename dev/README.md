# GymBro — App

App móvil y web para seguimiento de entrenamiento, peso y nutrición.

**Stack:** React Native + Expo · Firebase · TypeScript · NativeWind

## Estructura

```
dev/
├── apps/mobile/     ← App Expo (iOS + Android + Web)
├── firebase/        ← Reglas, índices y configuración de Firebase
└── .github/         ← GitHub Actions (CI/CD)
```

## Inicio rápido

```bash
cd apps/mobile
npm install
npx expo start          # abre el menú de Expo
npx expo start --web    # abre en navegador directamente
```

## Variables de entorno

Crea `apps/mobile/.env` con tus credenciales de Firebase:

```
EXPO_PUBLIC_FIREBASE_API_KEY=
EXPO_PUBLIC_FIREBASE_AUTH_DOMAIN=
EXPO_PUBLIC_FIREBASE_PROJECT_ID=
EXPO_PUBLIC_FIREBASE_STORAGE_BUCKET=
EXPO_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=
EXPO_PUBLIC_FIREBASE_APP_ID=
```

> Las variables `EXPO_PUBLIC_` son las únicas que Expo expone al bundle del cliente. Nunca uses claves privadas de servidor aquí.

## Firebase

Antes de correr la app necesitas:
1. Crear un proyecto en [Firebase Console](https://console.firebase.google.com)
2. Habilitar: Authentication (Email/Password), Firestore, Storage, Hosting
3. Copiar las credenciales al archivo `.env`
4. Desplegar las reglas: `firebase deploy --only firestore:rules`

## Deploy web

```bash
npx expo export --platform web
firebase deploy --only hosting
```
