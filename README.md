# FESTIVAL CONTROL · React Native + Expo Web + Amplify

Aplicación para gestionar eventos de un festival. Mantiene la identidad visual del cuaderno 04-PILARES-SERVERLESS: fondo `#090909`, cards `#151515`, acento `#FF2F92`, confirmado `#39D98A` y retrasado `#F5C542`.

## Inicio rápido

```bash
npm install
npx expo install --fix
npm run web
```

## Exportación para AWS Amplify Hosting

```bash
npm run build:web
```

El resultado estático se genera en `dist/`. En Amplify: conectar GitHub, rama `main` y usar `amplify.yml`. La fase backend del build despliega los recursos de Gen 2; el rol de servicio de Amplify debe tener permisos para aprovisionarlos.

## Backend de Amplify

El backend está definido con Amplify Gen 2 en `amplify/`: `data/resource.ts` declara el modelo `FestivalEvent` y `backend.ts` lo registra. El modelo permite crear, consultar, actualizar y eliminar eventos.

```bash
npm run sandbox
```

Este comando inicia el sandbox de desarrollo de Amplify y requiere credenciales de AWS configuradas. El acceso a los datos usa una API key pública para facilitar la demo; no debe usarse para datos sensibles ni en producción. La interfaz actual todavía usa datos locales y no está conectada a este backend.

## Prueba de alumno

1. Abrir **Eventos** y filtrar por escenario o artista.
2. Crear `TECHNO TITANS`, escenario `MAIN STAGE`, hora `21:45` y estado `CONFIRMED`.
3. Editar el evento y cambiar la hora a `23:00`.
4. Cambiar el estado a `DELAYED`.
5. Eliminar el evento.

**Datos simulados en memoria:** los cambios se pierden al recargar la página. Las operaciones no son HTTP reales. Para probar el despliegue automático, cambiar el subtítulo de la aplicación, hacer commit y push y observar el nuevo build en Amplify.

## Referencia docente

https://github.com/albertohdezakkari/04-PILARES-SERVERLESS
