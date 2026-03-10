# Sistema de Diagramas BPMN Interactivos
## Universidad de Caldas - Sistema Financiero

### 📋 Archivos del Sistema

1. **index.html** - Página principal con lista de procesos
2. **editor.html** - Editor BPMN completo para crear/editar diagramas
3. **presupuesto.html** - Visor del proceso de Programación Presupuestal
4. **presupuesto.bpmn** - Archivo BPMN del proceso
5. **template-bpmn.html** - Plantilla para crear nuevos visores

### 🚀 Características

✅ **Editor Interactivo**
- Crear diagramas BPMN desde cero
- Editar diagramas existentes
- Guardar en el navegador (localStorage)
- Importar/Exportar archivos .bpmn

✅ **Visores Interactivos**
- Zoom in/out
- Pan (arrastrar el diagrama)
- Exportar a SVG
- Swim lanes (carriles)
- Subflujos y elementos BPMN completos

### 📝 Cómo Convertir tus Diagramas Actuales

#### Opción 1: Usar el Editor (Recomendado)
1. Abre `editor.html`
2. Crea un nuevo diagrama
3. Usa la paleta lateral para agregar:
   - Pool (contenedor principal)
   - Lanes (carriles para cada actor)
   - Tareas, eventos, gateways
   - Flujos de secuencia
4. Guarda el diagrama
5. Exporta como .bpmn

#### Opción 2: Crear Archivo .bpmn Manualmente
1. Copia `presupuesto.bpmn` como base
2. Modifica los elementos:
   - Cambia nombres de lanes
   - Ajusta tareas y eventos
   - Actualiza flujos de secuencia
3. Guarda con nuevo nombre (ej: `ingresos.bpmn`)

#### Opción 3: Usar Herramientas Externas
- Camunda Modeler (https://camunda.com/download/modeler/)
- bpmn.io (https://demo.bpmn.io/)
- Exporta como .bpmn y coloca en la carpeta

### 🔧 Crear un Nuevo Visor

1. **Copia la plantilla:**
   ```
   Copia template-bpmn.html → nuevo-proceso.html
   ```

2. **Edita el HTML:**
   - Reemplaza `[NOMBRE DEL PROCESO]` con el nombre
   - Reemplaza `[TÍTULO DEL PROCESO]` con el título
   - Reemplaza `[DESCRIPCIÓN DEL PROCESO]` con la descripción
   - Cambia `[NOMBRE_ARCHIVO].bpmn` por tu archivo .bpmn

3. **Agrega la tabla de actividades:**
   ```html
   <tr>
       <td>1</td>
       <td>Nombre Actividad</td>
       <td>Responsable</td>
       <td>Descripción detallada</td>
   </tr>
   ```

4. **Actualiza index.html:**
   Agrega una nueva card apuntando a tu nuevo HTML

### 📦 Estructura de Archivos .bpmn

Los archivos .bpmn son XML con esta estructura:
```xml
<bpmn:definitions>
  <bpmn:collaboration>
    <bpmn:participant name="Nombre del Pool"/>
  </bpmn:collaboration>
  <bpmn:process>
    <bpmn:laneSet>
      <bpmn:lane name="Actor 1"/>
      <bpmn:lane name="Actor 2"/>
    </bpmn:laneSet>
    <bpmn:startEvent/>
    <bpmn:task name="Tarea 1"/>
    <bpmn:endEvent/>
    <bpmn:sequenceFlow/>
  </bpmn:process>
  <bpmndi:BPMNDiagram>
    <!-- Información visual -->
  </bpmndi:BPMNDiagram>
</bpmn:definitions>
```

### 🎨 Elementos BPMN Disponibles

- **Eventos:** Start, End, Intermediate
- **Tareas:** Task, User Task, Service Task, Manual Task
- **Gateways:** Exclusive, Parallel, Inclusive
- **Flujos:** Sequence Flow, Message Flow
- **Artefactos:** Data Object, Group, Annotation
- **Pools y Lanes:** Para organizar responsabilidades

### 💡 Tips

1. **Usa el editor** para crear diagramas complejos visualmente
2. **Guarda frecuentemente** - los diagramas se almacenan en localStorage
3. **Exporta tus diagramas** como .bpmn para respaldo
4. **Usa nombres descriptivos** en tareas y lanes
5. **Mantén los diagramas simples** - divide procesos complejos en subflujos

### 🔄 Migrar Diagramas Existentes

Para tus 4 diagramas actuales:
1. ✅ presupuesto.html - Ya convertido
2. ⏳ ingresos-transferencias.html - Por convertir
3. ⏳ modificaciones-presupuestales.html - Por convertir
4. ⏳ financiacion-faltante.html - Por convertir

**Proceso:**
1. Abre cada HTML actual
2. Identifica actores (lanes) y actividades (tasks)
3. Usa el editor para recrear el diagrama
4. Exporta como .bpmn
5. Crea el visor usando la plantilla

### 📚 Recursos

- Documentación bpmn.io: https://bpmn.io/toolkit/bpmn-js/
- Especificación BPMN 2.0: https://www.omg.org/spec/BPMN/2.0/
- Ejemplos: https://demo.bpmn.io/

### ⚙️ Requisitos Técnicos

- Navegador moderno (Chrome, Firefox, Edge)
- JavaScript habilitado
- Conexión a internet (para cargar librerías CDN)
- Servidor web local o hosting (para cargar archivos .bpmn)

### 🌐 Despliegue

Para usar en producción:
1. Sube todos los archivos a tu servidor web
2. Asegúrate que los archivos .bpmn sean accesibles
3. Configura CORS si es necesario
4. Considera descargar las librerías localmente para mejor rendimiento
