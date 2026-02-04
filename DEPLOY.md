# Guía de Despliegue

## Desarrollo Local

```bash
npm install
npm run dev
```

La aplicación estará disponible en http://localhost:3000

## Producción

### Vercel (Recomendado)

1. Hacer push del código a GitHub
2. Ir a [vercel.com](https://vercel.com)
3. Importar el repositorio
4. Vercel detectará automáticamente Next.js
5. Deploy

### Otros proveedores

```bash
# Build
npm run build

# Start
npm start
```

## Variables de Entorno

No se requieren variables de entorno para la aplicación básica.

## Consideraciones

- La app usa localStorage, por lo que los datos son específicos del navegador
- Las cotizaciones vienen de data912.com (no requiere API key)
- El fetch a data912.com puede fallar si hay CORS issues en producción

## Optimizaciones Recomendadas

1. Implementar caché de precios (15-20 segundos)
2. Considerar un backend para persistencia multi-dispositivo
3. Implementar autenticación si se quiere compartir entre dispositivos
4. Usar un proxy backend para evitar problemas de CORS con data912.com
