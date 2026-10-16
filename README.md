# U1-S02-A01 — Patrones de diseño

Proyecto Flutter en `ecotrack_patrones/`.

## Identificación de Patrones y Renombrado de Archivos

| Archivo Original | Patrón Identificado | Nuevo Nombre de Archivo | Descripción / Explicación |
| :--- | :--- | :--- | :--- |
| `consumo_memoria.dart` | **Repository** | `repository.dart` | Oculta la fuente de datos mediante la interfaz `AlmacenConsumo`. |
| `medidor_texto.dart` | **Adapter** | `adapter.dart` | Adapta el formato String (`"12.5 L"`) de `MedidorLegado` a `double` en `LectorMedidor`. |
| `aviso_semanal.dart` | **Factory** | `factory.dart` | Centraliza la creación del objeto `Aviso` mediante constructores `factory` (`Aviso.paraMeta`, etc.). |
| `tope_lectura.dart` | **Strategy** | `strategy.dart` | Define la interfaz `ReglaTope` e intercambia algoritmos/reglas (`TopeAgua`, `TopeLuz`) dinámicamente. |
| `registro_paneles.dart` | **Observer** | `observer.dart` | Usa `ChangeNotifier` y `ListenableBuilder` para notificar a los paneles (`PanelHistorial`, `PanelMeta`) cuando cambia el estado. |
| `lab_guardar.dart` | **Inyección de dependencias** | `inyeccion_dependencias.dart` | La pantalla `PantallaRegistro` recibe su dependencia `FuenteLab` desde el exterior (vía constructor). |

## Redirecciones del Menú (`main.dart`)

1. **Repository** &rarr; `PantallaConsumo`
2. **Adapter** &rarr; `PantallaMedidor`
3. **Factory** &rarr; `PantallaAviso`
4. **Strategy** &rarr; `PantallaTope`
5. **Observer** &rarr; `PantallaPaneles`
6. **Inyección de dependencias** &rarr; `PantallaLab`
