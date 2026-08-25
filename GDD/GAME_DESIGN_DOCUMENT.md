# 🏙️ URBAN EXPLORER 3D - GAME DESIGN DOCUMENT (GDD)

**Versión:** 1.0  
**Fecha:** 2025  
**Estado:** En Desarrollo

---

## 📑 TABLA DE CONTENIDOS

1. [Visión General](#visión-general)
2. [Descripción del Juego](#descripción-del-juego)
3. [Mecánicas Principales](#mecánicas-principales)
4. [Sistemas Dinámicos](#sistemas-dinámicos)
5. [Narrativa](#narrativa)
6. [Progresión](#progresión)
7. [Arte y Sonido](#arte-y-sonido)
8. [Plataformas y Especificaciones Técnicas](#plataformas-y-especificaciones-técnicas)
9. [Cronograma de Desarrollo](#cronograma-de-desarrollo)

---

## 🎯 VISIÓN GENERAL

### Concepto
**Urban Explorer 3D** es un juego de exploración urbana en primera persona que simula una ciudad completa y dinámica con sistemas de IA avanzados, física realista y clima procedural.

### Géneros
- Exploración de mundo abierto
- Simulador urbano interactivo
- Sandbox de interacción social
- Simulador de conducción (opcional)

### Plataformas Objetivo
- **PC**: Windows 10/11, Linux (Vulkan)
- **Móvil**: iOS 15+, Android 11+

### Público Objetivo
- Edades 13+
- Jugadores interesados en exploración, simuladores urbanos
- Entusiastas de mundos abiertos dinámicos

---

## 🎮 DESCRIPCIÓN DEL JUEGO

### Premisa
El jugador es un explorador urbano que arriba a una metrópolis futurista llamada **MetroCulture City**. Su objetivo es explorar libremente, interactuar con NPCs, descubrir secretos, y experienciar una ciudad completamente viva y reactiva.

### Características Principales
- **Ciudad Procedural**: Generada dinámicamente con 10km x 10km de área explorable
- **Tráfico IA Realista**: Cientos de vehículos navegando con semáforos, colisiones y respeto a normas
- **500,000+ NPCs Simulados**: Cada uno con rutinas diarias, emociones y propósitos
- **Clima Dinámico**: Cambios de clima que afectan la física, visibilidad y comportamiento
- **Física Realista**: Gravedad, fricción, colisiones con daño realista
- **Ciclo Día/Noche**: 24 horas simuladas en ~45 minutos reales

---

## 🕹️ MECÁNICAS PRINCIPALES

### 1. MOVIMIENTO DEL JUGADOR

#### A Pie
```
- Caminar: Velocidad normal (5 m/s)
- Correr: 2x velocidad (10 m/s)
- Agacharse: Stealth, velocidad 2.5 m/s
- Saltar: 2 metros de altura
- Trepar: Edificios, escaleras, estructuras
- Natación: Ríos, lagos, piscinas
```

#### En Vehículos
```
- Coches civiles (4 tipos)
- Motos (velocidad y maniobrabilidad)
- Bicicletas
- Autobús público
- Taxi
- Vehículos de emergencia (no jugables inicialmente)
```

### 2. INTERACCIÓN URBANA

#### Entrada a Edificios
- Casas residenciales
- Oficinas comerciales
- Tiendas y negocios
- Restaurantes y bares
- Museos y galerías
- Estaciones de transporte

#### Interacción Social
- Diálogos con NPCs (ramificados)
- Toma de decisiones que afectan reputación
- Búsqueda de información
- Misiones secundarias

#### Fotografía y Exploración
- Sistema de fotografía (capturas in-game)
- Desafíos de exploración
- Descubrimiento de puntos de interés (POIs)
- Logros por exploración

### 3. MISIONES

#### Misiones Principales
- Narrativa central (20-30 horas de juego)
- Personajes con arcos argumentales
- Objetivos claros y progresión

#### Misiones Secundarias
- Tareas ciudadanas (entregar paquetes, ayudar NPCs)
- Investigaciones (encontrar personas desaparecidas)
- Desafíos (carreras, competencias)
- Historias personales de NPCs

#### Eventos Dinámicos
- Accidentes de tráfico
- Protestas callejeras
- Persecuciones policiales
- Celebraciones y festivales
- Desastres naturales (terremotos, inundaciones)

---

## ⚙️ SISTEMAS DINÁMICOS

### SISTEMA DE TRÁFICO IA

#### Red de Carreteras
- Mapa de callejones, avenidas y autopistas
- Señalización (señales de tráfico, marcas de carril)
- Zonas de estacionamiento
- Gasolineras, talleres

#### Vehículos Autónomos
- Cada vehículo tiene:
  - Ruta pathing (A* pathfinding)
  - Respeto a semáforos
  - Evasión de colisiones
  - Cambios de carril dinámicos
  - Sistema de combustible (se dañan si se quedan sin gasolina)

#### Reglas de Tráfico
- Velocidades límites por zona
- Estacionamiento regulado
- Comportamiento en intersecciones
- Reacciones a accidentes

### SISTEMA DE NPCs

#### Rutinas Diarias
Cada NPC tiene un horario (24 horas):
```
06:00 - Despertar, desayunar
08:00 - Ir al trabajo/escuela
09:00 - 17:00 - Trabajo/Actividad principal
12:00 - 13:00 - Almuerzo (algunos van a restaurantes)
17:00 - Regreso a casa
18:00 - 20:00 - Tiempo libre (compras, entretenimiento)
20:00 - 22:00 - Cena, actividades sociales
22:00 - Dormir
```

#### Emociones y Estados
- Felicidad: Afecta velocidad de movimiento y expresiones
- Frustración: Por tráfico congestionado, eventos negativos
- Energía: Determina actividad vs descanso
- Salud: Puede enfermar, necesita médicos

#### Interacción con Jugador
- Reaccionan a acciones del jugador
- Sistema de reputación
- Memoria de encuentros anteriores
- Diferentes diálogos según estado emocional

### SISTEMA DE CLIMA

#### Tipos de Clima
1. **Soleado**: Visibilidad excelente, NPCs activos
2. **Nublado**: Visibilidad normal, sin afectar físicas
3. **Lluvia**: Menor tracción vehículos (-30%), peatones lentos, reflexiones
4. **Tormenta**: Lluvia intensa, truenos, rayos, visibilidad reducida
5. **Nieve**: Máxima reducción de tracción (-50%), peatones muy lentos
6. **Niebla**: Visibilidad muy reducida, peligro en carreteras

#### Ciclo de Cambios
- Cambios graduales cada 5-30 minutos de juego
- Patrones estacionales (más lluvia en otoño)
- Eventos climáticos extremos aleatorios (1-5% probabilidad)

#### Impacto en Gameplay
- **Física**: Fricción dinámica, manejo de vehículos
- **Visibilidad**: FOV y render distance reducido
- **NPCs**: Comportamiento modificado (refugiarse, ir a casa)
- **Ambiente**: Sonidos de lluvia/viento, iluminación dinámica
- **Peligros**: Deslizamientos, inundaciones

---

## 📖 NARRATIVA

### Acto 1: Llegada
El jugador llega a MetroCulture City como turista. Se le introduce el mundo, los controles y se establece el tono de exploración.

### Acto 2: Inmersión
El jugador se engancha en misiones que revelan secretos de la ciudad. Descubre corporaciones poderosas, conspiración, e historia oculta.

### Acto 3: Conflicto
Eventos cataclísmicos sacuden la ciudad. El jugador debe elegir bandos, enfrentar personajes principales y determinar el futuro.

### Personajes Principales
- **Director Sato**: Alcalde corrupto
- **Dr. Elena Voronov**: Científica rebelde
- **Marcus "Trigger" Chen**: Criminal informante
- **Sarah Kim**: Periodista investigadora
- **Father Thomas**: Líder comunitario

---

## 📊 PROGRESIÓN

### Sistema de Experiencia
```
Acción                    | XP
--------------------------|-----
Descubrir POI              | 10
Completar misión menor     | 25
Completar misión principal | 100
Fotografiar evento único   | 15
Interactuar con NPC        | 5
```

### Niveles de Jugador
- Niveles 1-50
- Desbloqueables: Ubicaciones, vehículos, habilidades
- Logros por hito (nivel 10, 25, 50)

### Sistemas de Mejora
- **Habilidades**: Conducción, sigilo, reparación
- **Vehículos**: Mejoras de motor, manejo, estética
- **Herramientas**: Cámara mejor, GPS, escáner

---

## 🎨 ARTE Y SONIDO

### Estética Visual
- **Estilo**: Realismo futurista
- **Paleta de Colores**: Cyberpunk moderno con neons
- **Inspiración**: Blade Runner, Ghost in the Shell, Cyberpunk 2077

### Arquitectura
- Distrito céntrico: Rascacielos futuristas (100-200m)
- Barrio residencial: Edificios bajos (10-20m)
- Zona portuaria: Industria, almacenes
- Parques y plazas: Espacios verdes
- Suburbios: Baja densidad

### Audio
- **Música Ambiental**: Synth, lo-fi, ambiental
- **Efectos de Sonido**: Tráfico, pasos, diálogos
- **Diálogos**: Múltiples idiomas, lipSync
- **Señales Sonoras**: Semáforos, alarmas, emergencias

---

## 💻 PLATAFORMAS Y ESPECIFICACIONES TÉCNICAS

### PC (Windows/Linux)
**Mínimos:**
- CPU: Intel i7-10700K / Ryzen 5 3600
- GPU: RTX 2060 / RX 5700
- RAM: 16 GB
- SSD: 150 GB
- OS: Windows 10 64-bit / Ubuntu 20.04

**Recomendado:**
- CPU: Intel i9-12900K / Ryzen 9 5900X
- GPU: RTX 4080 / RX 7900 XT
- RAM: 32 GB
- SSD: 200 GB NVMe
- OS: Windows 11 / Ubuntu 22.04

### Móvil (iOS/Android)
**Mínimos:**
- RAM: 6 GB
- GPU: Apple A14 Bionic / Snapdragon 870
- Almacenamiento: 40 GB
- OS: iOS 15 / Android 11

**Recomendado:**
- RAM: 8+ GB
- GPU: Apple M1+ / Snapdragon 8 Gen 1+
- Almacenamiento: 50 GB
- OS: iOS 16+ / Android 13+

### Especificaciones Técnicas
- **Motor**: Unreal Engine 5 (PC) / Unity + DOTS (Móvil)
- **Resolución PC**: 1440p-4K a 60fps (mínimo 30fps)
- **Resolución Móvil**: 1080p a 30fps
- **Tamaño del Mapa**: 10 km x 10 km
- **Distancia de Render**: 2-5 km según plataforma
- **NPCs Activos**: 500-2000 simultáneamente

---

## 🗓️ CRONOGRAMA DE DESARROLLO

### FASE 1: Prototipo (Meses 1-2)

**Semana 1-4:**
- Configuración de proyecto
- Pipeline de arte básico
- Player controller (a pie)
- Generación procedural simple

**Semana 5-8:**
- Vehículos manejables (1-2 tipos)
- Ciclo día/noche
- Sistema de cámara
- Primeras misiones

### FASE 2: Sistemas Core (Meses 3-4)

**Semana 9-16:**
- Tráfico IA completo
- NPCs con rutinas
- Sistema de clima
- Física realista (vehículos y peatones)
- Sistema de guardado

### FASE 3: Contenido (Meses 5-6)

**Semana 17-24:**
- 50+ misiones
- Diálogos y cinemáticas
- 100+ edificios únicos
- Eventos dinámicos
- Sistema de emociones NPCs

### FASE 4: Pulido y Optimización (Meses 7-8)

**Semana 25-32:**
- Optimización móvil
- Testing y QA
- Sonido y música
- UI final
- Bugfixes

### FASE 5: Lanzamiento (Mes 9)

- Gold master
- Certificación plataformas
- Marketing
- Lanzamiento global

---

## 📋 CONTENIDO ENTREGABLE

### Antes del Lanzamiento
- [ ] GDD Completo (este documento)
- [ ] Diagramas UML de arquitectura
- [ ] Scripts C# listos para producción
- [ ] Asset pack inicial
- [ ] Guía de nivel
- [ ] Documento de arte (concept art, paleta de colores)

### Post-Lanzamiento (Actualizaciones)
- [ ] Nuevos distritos (expansión 1)
- [ ] Vehículos adicionales (50+)
- [ ] Misiones nuevas
- [ ] Eventos estacionales
- [ ] Mejoras de rendimiento

---

## ✅ CRITERIOS DE ÉXITO

### Jugabilidad
- [ ] Ciudad explorable sin lag
- [ ] 500+ NPCs activos simultáneamente
- [ ] Tráfico IA que respeta reglas
- [ ] Física realista en colisiones

### Contenido
- [ ] 50+ horas de contenido principal
- [ ] 100+ misiones variadas
- [ ] 20+ distritos únicos

### Técnico
- [ ] PC: 60fps a 1440p mínimo
- [ ] Móvil: 30fps a 1080p mínimo
- [ ] <5 segundos para cargar chunks
- [ ] Tamaño: <200GB PC, <50GB Móvil

### Comunidad
- [ ] 50K+ usuarios primer mes
- [ ] Rating 4.5+ en plataformas
- [ ] Comunidad activa en Discord/Foros

---

**FIN DEL DOCUMENTO**
