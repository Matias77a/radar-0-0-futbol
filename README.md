# Radar 0-0 — Fútbol en vivo

Radar gratuito para detectar partidos de fútbol que cumplen:
- Marcador 0-0
- Segundo tiempo
- Minuto configurable (por defecto 46–80)
- Todas las ligas que devuelva API-Football

## Cómo funciona

GitHub Actions consulta API-Football cada 15 minutos y guarda solamente los partidos que cumplen el filtro en `data/live.json`. GitHub Pages muestra esos datos desde el celular.

La API Key NO está dentro del código. Se guarda como secreto de GitHub llamado `API_FOOTBALL_KEY`.

## Instalación rápida

1. Crea un repositorio público en GitHub, por ejemplo `radar-0-0-futbol`.
2. Sube todos los archivos de este proyecto.
3. Ve a Settings → Secrets and variables → Actions → New repository secret.
4. Nombre: `API_FOOTBALL_KEY`
5. Valor: tu API Key de API-Football.
6. Ve a Actions y ejecuta manualmente `Actualizar radar` una vez.
7. Activa GitHub Pages desde Settings → Pages → Source: GitHub Actions.
8. Abre la URL de Pages desde Android.

## Importante

El plan gratuito de API-Football tiene un límite diario de consultas. El workflow está programado cada 15 minutos (96 ejecuciones/día) para mantenerse dentro de un límite de 100 consultas/día. Si el proveedor cambia el límite, ajusta el cron.

La actualización no es cada minuto: es aproximadamente cada 15 minutos. Esto es deliberado para respetar el límite gratuito.
