# 🔔 Sistema de Notificaciones iOS Shortcuts

## ⚠️ Problema con PWAs en iOS
Las notificaciones de PWAs **NO funcionan en background** en iOS. Solo funcionan cuando la app está abierta.

## ✅ Solución: iOS Shortcuts + Automatizaciones

### **Método 1: Shortcut Manual (funciona siempre)**

1. Abre la app **Shortcuts** (Atajos) en tu iPhone
2. Toca el **+** para crear nuevo Shortcut
3. Agrega estas acciones:

```
Acción 1: "Obtener fecha actual"
└─ Formato: Personalizado "HH"

Acción 2: "Obtener fecha actual"  
└─ Formato: Personalizado "EEEE"

Acción 3: "Si" [Hora] "es igual a" "14"
    └─ "Mostrar notificación"
        ├─ Título: "🎯 Routine Tracker"
        ├─ Cuerpo: "Ahora: Trabajo"
        └─ Sonido: Predeterminado

[Repetir para cada hora...]
```

4. Guárdalo como "Routine Checker"

### **Método 2: Automatización (mejor opción)**

1. Abre **Shortcuts** → **Automatización** (pestaña del medio)
2. Toca **+** → **Crear automatización personal**
3. Selecciona **Hora del día**
4. Configura:
   - **Hora**: 7:00 AM
   - **Repetir**: Todos los días
   - **Ejecutar inmediatamente**: ✅ ACTIVADO

5. Agrega acción: **Mostrar notificación**
   - Título: "🍳 Desayunar"
   - Cuerpo: "7:00 - 8:00"

6. Repite para CADA hora de tu rutina:
   - 7:00 → Desayunar
   - 8:00 → Entrenar  
   - 9:00 → Trabajo
   - 12:00 → Almuerzo
   - 17:00 → Ingles/Flex (según día)
   - 19:00 → Leetcode
   - 22:00 → Cena

### **Método 3: Shortcut Avanzado con Diccionario**

Crea UN SOLO shortcut inteligente:

```
Acción 1: Diccionario
{
  "Monday": {
    "7": "Desayunar",
    "8": "Entrenar",
    "9": "Trabajo",
    "12": "Almuerzo",
    "17": "Ingles",
    "19": "Leetcode",
    "22": "Cena"
  },
  "Tuesday": { ... },
  ...
}

Acción 2: Obtener fecha → Formato "EEEE"
Acción 3: Obtener fecha → Formato "HH"
Acción 4: Obtener valor para "Día" de Diccionario
Acción 5: Obtener valor para "Hora" de subdicionario
Acción 6: Mostrar notificación con resultado
```

## 🎯 Configuración recomendada:

**Para que funcione perfectamente:**

1. ✅ Crea automatizaciones para: 7:00, 8:00, 12:00, 17:00, 19:00, 22:00
2. ✅ Activa "Ejecutar inmediatamente" 
3. ✅ Permite notificaciones de Shortcuts
4. ✅ Mantén la PWA en background como respaldo

**Ventajas:**
- ✅ Funciona incluso con el iPhone bloqueado
- ✅ Funciona sin internet
- ✅ Funciona aunque la app esté cerrada
- ✅ Es 100% confiable

**Desventajas:**
- ❌ Debes configurar cada hora manualmente
- ❌ No se adapta automáticamente si cambias la rutina

## 🔗 Shortcut pre-configurado

Voy a crear un archivo .shortcut que puedes importar directamente.

