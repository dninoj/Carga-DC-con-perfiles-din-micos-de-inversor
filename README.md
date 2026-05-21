# Carga-DC-con-perfiles-din-micos-de-inversor

Este repositorio contiene los archivos del modelo y la simulación utilizados en el proyecto de emulación de perfiles de carga dinámicos (residencial e industrial) sobre el bus DC de un inversor, utilizando la plataforma Typhoon HIL 604.

## Archivos incluidos

| Archivo | Descripción |
|---------|-------------|
| `esquematico_final.tse` | Esquemático final de Typhoon HIL. Incluye la fuente DC (baterías), medidor de corriente, inversor EPC Power y la carga variable trifásica con adaptaciones mediante buses *join* y tabla dinámica. |
| `scada.cus` | Archivo de proyecto SCADA de Typhoon HIL. Contiene la configuración de visualización en tiempo real (corriente DC, corrientes AC, señales de la carga variable) y los ajustes de adquisición de datos (sample rate = 100 sps, duración = 700 s). |
| `DG_247_Factory-rel-6de948b-3898934689.epz` | Modelo del inversor EPC Power utilizado en el esquemático. Corresponde al nodo 247 del entorno de Typhoon HIL, configurado para una potencia nominal de 500 kW. |

## Requisitos

- Typhoon HIL Control Center (versión 2023.1 o superior)
- Typhoon HIL 604 (hardware) o simulador offline

## Uso básico

1. Abrir `esquematico_final.tse` en Typhoon HIL Schematic Editor.
2. Compilar y cargar el modelo en el hardware HIL 604 o en modo offline.
3. Abrir `scada.cus` desde HIL SCADA para visualizar las señales y configurar la adquisición de datos.

## Notas

- El perfil de carga original de 24 horas se redujo a 12 minutos por limitaciones de memoria del hardware.
- Los valores de potencia activa (P) y reactiva (Q) se adaptaron mediante buses *join* para que la carga variable trifásica los interprete correctamente.
- El esquemático incluye particiones y núcleos dedicados para evitar sobrecarga del HIL.

## Referencias

Para más detalles sobre la metodología, resultados y análisis, consultar el informe completo asociado a este repositorio.

---

**Autores:** Juan Felipe Hernández, Daniel Esteban Niño Jimenez, Juan Jose Castillo Urbano  
**Universidad de los Andes** - Bogotá, Colombia
