#  Dino Game AI - Algoritmos Genéticos

Implementación del clásico juego del dinosaurio de Chrome con entrenamiento mediante **algoritmos genéticos** y **redes neuronales** para juego autónomo.

![Python](https://img.shields.io/badge/Python-3.9-blue)
![Pygame](https://img.shields.io/badge/Pygame-2.0-green)
![AI](https://img.shields.io/badge/AI-Genetic_Algorithm-red)

##  Modos de Juego

| Tecla | Modo | Descripción |
|-------|------|-------------|
| `m` | **Manual** | Control con flechas del teclado |
| `c` | **Captura** | Manual + captura de screenshots para Tensorflow |
| `a` | **Tensorflow** | Modo automático usando modelo CNN |
| Otra | **Genético** | Entrenamiento con algoritmo genético + red neuronal |

##  Características del Algoritmo Genético

- **Población:** 150 dinosaurios por generación
- **Arquitectura de Red:** 5 → 24 → 16 → 3 (2 capas ocultas)
- **Inputs:** Distancia X/Y al obstáculo, velocidad, posición
- **Outputs:** SALTAR, AGACHARSE, CORRER
- **Fitness Inteligente:** Penaliza ineficiencia sin hacer trampa
- **Guardado Automático:** Progreso persistente entre sesiones

### Estrategias de Optimización

- ✅ Elitismo adaptativo (12.5% → 16.7%)
- ✅ Mutación decreciente (18% → 12%)
- ✅ Selección por fitness inteligente
- ✅ Diversidad inicial en pesos
- ✅ Neuronas especializadas en altura

##  Instalación y Uso
```bash
# Clonar repositorio
git clone https://github.com/Arguur/Dino-AI-Genetico.git
cd Dino-AI-Genetico

# Instalar dependencias (automático al ejecutar)
python main.py
```

**Dependencias:** `pygame`, `numpy`, `tensorflow` (opcional), `pyscreenshot` (opcional)

##  Resultados

- **Generaciones:** Entrenamiento continuo con guardado automático
- **Fitness:** Sistema inteligente que premia supervivencia eficiente
- **Progreso:** Historial de últimas 50 generaciones

## 🎓 Contexto Académico

**Materia:** Inteligencia Artificial II  
**Carrera:** Ingeniería en Mecatrónica  
**Universidad:** Universidad Nacional de Cuyo  
**Año:** 2024  

### Modificaciones Realizadas

-  Arquitectura de red mejorada (2 capas ocultas)
-  Sistema de fitness inteligente
-  Guardado/carga automático de progreso
-  Población aumentada (50 → 150)
-  Estrategias adaptativas de mutación

##  Detalles Técnicos

### Red Neuronal
```python
Entrada (5):  [dist_x, dist_y, velocidad, pos_y, vel_relativa]
Hidden 1 (24): ReLU + neuronas especializadas
Hidden 2 (16): ReLU + compresión
Salida (3):   Softmax → [JUMP, DUCK, RUN]
```

### Algoritmo Genético

1. **Evaluación:** Fitness inteligente (supervivencia + eficiencia)
2. **Selección:** Top 50% por ruleta ponderada
3. **Cruce:** Uniforme con máscaras aleatorias
4. **Mutación:** Gaussiana adaptativa (18% → 12%)
5. **Elitismo:** Preservar mejores individuos (12-17%)

##  Comandos Útiles
```bash
# Ejecutar modo genético (recomendado)
python main.py
# → Presionar cualquier tecla excepto 'm', 'c', 'a'

# Entrenar modelo Tensorflow (opcional)
python BuildTensorflowModel.py

# Jugar manualmente
python main.py  
# → Presionar 'm'
```

##  Métricas de Entrenamiento

El sistema muestra en tiempo real:
-  Dinosaurios vivos
-  Generación actual  
-  Mejor puntuación
-  Guardado automático cada generación

##  Licencia

Proyecto académico - Universidad Nacional de Cuyo 2024

---

 **Trabajo Práctico de IA II** - Algoritmos Genéticos + Redes Neuronales
