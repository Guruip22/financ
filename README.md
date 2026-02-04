# MiInversiones AR - Portfolio Tracker

Un tracker de portfolio completo para inversiones en el mercado argentino (acciones locales, CEDEARs, bonos y notas).

## 🚀 Características

### Dashboard de Portfolio
- Vista consolidada de todas las posiciones
- Cards de resumen: Valor Total, Capital Invertido, P/L No Realizado, Rendimiento %
- Gráficos interactivos: distribución por activo (pie chart) y P/L por ticker (bar chart)
- Tabla detallada con precios actuales y P/L no realizado
- Botón para actualizar cotizaciones en tiempo real

### Gestión de Transacciones
- Formulario intuitivo para registrar compras y ventas
- Campos: Ticker, Tipo, Cantidad, Precio, Fecha, Comisiones, Notas
- Validación de datos y formato automático
- Conversión de ticker a mayúsculas

### Historial de Transacciones
- Vista completa de todas las operaciones
- Filtros por ticker y fecha
- Visualización de tipo de operación (compra/venta)
- Eliminar transacciones con confirmación
- Exportar a CSV

### Rendimientos Realizados (FIFO)
- Cálculo automático de P/L realizado usando método FIFO
- Vistas por período: Diario, Mensual, Anual
- Tablas con totales por período
- Gráficos de barras (P/L por período) y líneas (P/L acumulado)
- Cards de resumen: Total Realizado, Operaciones Cerradas, Mejor Período
- Detalle completo de todas las ventas con % de retorno
- Exportar a CSV

### Sistema de Alertas
- Configurar Stop Loss y Target Price por ticker
- Banner de alertas activadas cuando se alcanzan los precios objetivo
- Tabla con estado visual de cada alerta
- Indicadores de alerta disparada (rojo para stop loss, verde para target)

### Cotizaciones en Vivo
- Integración con data912.com para precios actualizados
- Soporte para acciones argentinas, CEDEARs, bonos y notas
- Actualización manual con botón
- Manejo de errores y valores "N/A" para activos sin cotización

### Diseño y UX
- Modo oscuro/claro con toggle
- Diseño responsive (mobile-first)
- Componentes Shadcn UI con Tailwind CSS
- Iconos lucide-react
- Formateo de moneda en ARS
- Colores semánticos: verde para ganancias, rojo para pérdidas

## 🛠️ Tecnologías

- **Next.js 15** (App Router)
- **TypeScript**
- **Tailwind CSS**
- **Shadcn UI** (componentes)
- **Recharts** (gráficos)
- **date-fns** (manejo de fechas)
- **lucide-react** (iconos)
- **localStorage** (persistencia)

## 📦 Instalación

```bash
# Clonar el repositorio
git clone <repository-url>

# Navegar al directorio
cd miinversiones-ar

# Instalar dependencias
npm install

# Ejecutar en desarrollo
npm run dev
```

Abrir [http://localhost:3000](http://localhost:3000) en el navegador.

## 🧮 Cálculo FIFO

El sistema implementa el método FIFO (First In, First Out) para calcular el P/L realizado:

1. Cuando se registra una venta, el sistema busca las compras más antiguas del mismo ticker
2. Calcula el precio promedio de compra ponderado incluyendo comisiones
3. Genera un registro de "closed trade" con:
   - Cantidad vendida
   - Precio promedio de compra
   - Precio de venta
   - P/L realizado (incluyendo todas las comisiones)
   - % de retorno

## 📊 Fuente de Datos

Las cotizaciones provienen de [data912.com](https://data912.com):
- `/live/arg_stocks` - Acciones argentinas
- `/live/arg_cedears` - CEDEARs
- `/live/arg_bonds` - Bonos
- `/live/arg_notes` - Notas

**Importante:** Los datos son educativos, con actualización aproximada de 20 segundos. No usar para trading real sin verificar con broker oficial.

## 💾 Almacenamiento

Todos los datos se almacenan localmente en el navegador usando localStorage:
- `transactions`: array de transacciones
- `closedTrades`: array de ventas con P/L realizado
- `alertas`: configuración de stop loss y targets por ticker

## ⚠️ Disclaimer

**Esta aplicación es solo para uso educativo y personal.**

- Los cálculos son aproximados y pueden contener errores
- No constituye asesoramiento financiero o de inversión
- Siempre verifique los datos con su broker oficial
- Consulte con un contador para temas impositivos

## 📝 Licencia

MIT

## 👤 Autor

Creado por [@Guru_itm](https://twitter.com/Guru_itm)
