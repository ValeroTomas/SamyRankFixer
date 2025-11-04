# 🧩 SamyRankFixer

**Versión:** 2.2.1  
**Autor:** Samy  
**Compatibilidad:** CounterStrikeSharp API v80+  
**Descripción:**  
Plugin de corrección y mejora del sistema de rangos de **K4-System**.  
Previene exploits de cambio de equipo, penaliza comportamientos sospechosos y otorga puntos por daño y desempeño al final de cada ronda.

---

## ⚙️ Funcionalidades principales

### 🔒 Anti-Exploit de Rank
- Detecta jugadores **CT** que se cambian a **espectador** o **terrorista** para evitar perder puntos.  
- Reasigna automáticamente al jugador a su equipo original (CT) y aplica penalización.  
- Notifica a los administradores del servidor del intento de evasión.

### 🩸 Sistema de Premios por Daño
- Acumula el daño total realizado por cada jugador durante la ronda.  
- Al finalizar la ronda:
  - Premia automáticamente al **Top 5** jugadores con más daño.
  - Otorga puntos adicionales cada **2500 de daño** infligido.  
- Evita entregas duplicadas mediante un **cooldown interno de 2 segundos**.

### 👥 Control de Jugadores
- Las penalizaciones y premios solo se aplican cuando hay una cantidad mínima de jugadores reales conectados (`MinPlayersForPenalty`).

---

## 🧰 Comandos de Consola

| Comando | Descripción | Ejemplo |
|----------|--------------|----------|
| `samyrankfixer_minplayers <n>` | Cambia el mínimo de jugadores requeridos para aplicar penalizaciones o premios. | `samyrankfixer_minplayers 10` |
| `samyrankfixer_penalty <n>` | Cambia la cantidad de puntos restados por penalización. | `samyrankfixer_penalty 5` |
| `samyrankfixer_cooldown <n>` | Define los segundos mínimos entre cambios de equipo. | `samyrankfixer_cooldown 30` |
| `samyrankfixer_toggle` | Activa o desactiva la prevención de cambio a espectador/terrorista. | `samyrankfixer_toggle` |
| `samyrankfixer_maxcts <n>` | Define el máximo de CT vivos para aplicar penalización. | `samyrankfixer_maxcts 3` |
| `samyrankfixer_pointsdmg <n>` | Puntos otorgados cada 2500 de daño. | `samyrankfixer_pointsdmg 2` |
| `samyrankfixer_pointstop1-5 <n>` | Define los puntos para cada posición del Top 5. | `samyrankfixer_pointstop1 50` |
| `samyrankfixer_status` | Muestra el estado y configuración actual. | `samyrankfixer_status` |

> ⚠️ Todos los comandos requieren permisos de administrador (`@css/root` o `@css/owner`).

---

## 🗂️ Configuración JSON

El archivo de configuración se genera automáticamente al iniciar el plugin:

**Ruta:**  
```
csgo/addons/counterstrikesharp/configs/SamyRankFixer.json
```

**Ejemplo de configuración:**
```json
{
  "PenaltyPoints": 5,
  "CooldownSeconds": 30,
  "PreventSpectatorSwitch": true,
  "MaxCtsForPenalty": 3,
  "MinPlayersForPenalty": 7,
  "PointsPerDmg": 2,
  "PointsPerTop1": 50,
  "PointsPerTop2": 30,
  "PointsPerTop3": 20,
  "PointsPerTop4": 10,
  "PointsPerTop5": 5
}
```

---

## 📜 Registro en consola
Cada cambio importante o evento clave (penalización, entrega de puntos, cambio de configuración) se muestra en la consola del servidor para facilitar el monitoreo.

---

## 🧩 Dependencias

- [CounterStrikeSharp API](https://github.com/roflmuffin/CounterStrikeSharp)
- [K4-System Shared API](https://github.com/samynxx/K4-System)

---

## 🏁 Notas

- El plugin **no interfiere** con el sistema de penalización existente de K4-System.  
- Diseñado para funcionar en servidores con modos **Zombie Escape** o similares.  
- Totalmente compatible con *hot reload* de CounterStrikeSharp.

---

**Desarrollado por Samy con ❤️ para la comunidad.**
