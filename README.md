# Cómo suministrar la información

Este archivo es el instructivo del prompt. Completarlo y pegarlo en el chat cuando se pida la documentación de un caso de uso de Ansible. No forma parte del README del caso: el README se genera a partir de [README.md](README.md).

Reglas de llenado:

- Escriba solo lo que existe en el caso. Si un dato no se conoce, ponga `Pendiente` o deje el campo vacío. No reutilice nombres de otro proyecto.
- Un bloque `## Caso` por cada caso de uso que deba quedar en el mismo README.
- Rutas de playbook tal como están en el repositorio.
- En credenciales, el nombre de la variable de entorno. Nunca la contraseña, el token ni la llave.
- En el diagrama, los pasos en orden. El agente genera el `.drawio` y el `.png` con el estilo de [ejemplo_flujo.drawio](ejemplo_flujo.drawio).

```markdown
## Caso

Nombre:
Objetivo en una frase:
Sistemas que participa (AAP y los externos):
Camino de fallo, si existe:

### Pre-requisitos

- Consolas con privilegio:
- Inventario de ejecución:
- Red, paquetes o catálogos que deben existir antes de lanzar el job:

### Actividades

| Tarea | Estado | Responsable |
|:------|:-------|:------------|
|  |  |  |

### Pasos

Un bloque por nodo, en orden.

- Nombre del paso:
  Playbook:
  Cuándo corre: Run on success | Run on fail | Run always
  Desde qué nodo:
  En paralelo con:
  Qué hace:
  - 
  Qué publica hacia el workflow:

### Archivos

Árbol o lista. Marque los que no son playbook (plantilla, vars, paquete, EE).

### Execution Environment

Incluir solo si el EE es propio del caso.

- Ruta de la definición:
- Dependencias:
- Nombre y etiqueta de la imagen:

### Colecciones

-

### Job templates

| Nombre | Playbook | Credenciales (tipo y variables de entorno) | EE, si tiene nombre propio |
|:-------|:---------|:-------------------------------------------|:---------------------------|
|  |  |  |  |

### Workflow

- Nombre:
- Inventario:
- Si no hay workflow y es un solo job, escribir: sin workflow

| Nodo | Nombre | Playbook | Condición |
|:-----|:-------|:---------|:----------|
|  |  |  |  |

### Survey

Si no hay survey, escribir: sin survey.

| # | Pregunta | Variable | Tipo | Requerida | Valor por defecto | Opciones |
|:--|:---------|:---------|:-----|:----------|:------------------|:---------|
|  |  |  |  |  |  |  |

Opciones del survey que todavía no tienen tareas:

### Variables

#### Extra vars

| Variable | Descripción | Tipo | Usado en | ¿Está en el survey? | Valor si no llega |
|:---------|:------------|:-----|:---------|:--------------------|:------------------|
|  |  |  |  |  |  |

#### Credenciales de entorno

| Variable | Qué autentica | Usado en |
|:---------|:--------------|:---------|
|  |  |  |

#### Fijas en el playbook

| Variable | Descripción | Tipo | Definida en |
|:---------|:------------|:-----|:------------|
|  |  |  |  |

#### Dinámicas (set_fact / set_stats)

| Variable | Qué publica y quién la consume | Tipo | Definida en |
|:---------|:-------------------------------|:-----|:------------|
|  |  |  |  |

### Consideraciones

- Orden obligatorio entre nodos:
- Valores por defecto:
- Límites conocidos:

### Referencia

Tabla propia del caso, si existe. Si no existe, escribir: sin tabla.

| Clave | Valor |
|:------|:------|
|  |  |

Cómo se elige la fila:

### Diagrama

- Título: CU - <nombre>
- Pasos y decisiones, en orden:
- Qué flecha es éxito y cuál es fallo:
- Pasos en paralelo, si los hay:
```
