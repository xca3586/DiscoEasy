[[_TOC_]]
# Forum  
https://www.lesimprimantes3d.fr/forum/topic/10887-sticky-derni%C3%A8re-version-marlin-pour-discoeasy-200/


# Outils de génération
Il faut installer **VSCode**  
https://code.visualstudio.com/

Puis le plugin **Platformio IDE** dans VSCode  
https://github.com/platformio/platformio-vscode-ide.git

# Version GitHhub
https://github.com/MarlinFirmware/Marlin/tree/2.0.x  
https://github.com/MarlinFirmware/Marlin/releases/tag/2.0.8.1

# Configuration DiscoEasy MKS Base 1.5 (matériel non modifié) 
## Fichier platformio.ini  
```
default_envs = mega2560
```
## Fichier Marlin/Configuration.h  
```
#define SERIAL_PORT 0
#define MOTHERBOARD BOARD_MKS_BASE_15
#define DEFAULT_NOMINAL_FILAMENT_DIA 1.75
//temp sensor fil blanc -> NTC100k donc ??? 18 après test
#define TEMP_SENSOR_0 18
#define  DEFAULT_Kp 32.48
#define  DEFAULT_Ki 6.4
#define  DEFAULT_Kd 41.25
#define USE_XMIN_PLUG
#define USE_YMAX_PLUG
#define USE_ZMIN_PLUG
#define X_DRIVER_TYPE  A4988
#define Y_DRIVER_TYPE  A4988
#define Z_DRIVER_TYPE  A4988
#define E0_DRIVER_TYPE A4988
#define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 2560, 98 }
#define DEFAULT_MAX_FEEDRATE          { 500, 500, 4, 170 }
#define DEFAULT_MAX_ACCELERATION      { 3000,1000,20,10000}
#define CLASSIC_JERK
#define DEFAULT_XJERK 10.0
#define DEFAULT_YJERK 10.0
#define DEFAULT_ZJERK 0.4
#define DEFAULT_EJERK 5.0



 
#define FIX_MOUNTED_PROBE 
#define Z_SAFE_HOMING
#define NOZZLE_TO_PROBE_OFFSET { 0, 21, 0 }
#define X_HOME_DIR -1
#define Y_HOME_DIR 1
#define Z_HOME_DIR -1
#define X_BED_SIZE 200
#define Y_BED_SIZE 200
#define X_MIN_POS 0
#define Y_MIN_POS 0
#define Z_MIN_POS 0
#define X_MAX_POS X_BED_SIZE
#define Y_MAX_POS Y_BED_SIZE
#define Z_MAX_POS 200
#define AUTO_BED_LEVELING_BILINEAR

#define X_MIN_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
#define Y_MIN_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
#define Z_MIN_ENDSTOP_INVERTING true // Set to true to invert the logic of the endstop.
#define X_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
#define Y_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
#define Z_MAX_ENDSTOP_INVERTING false // Set to true to invert the logic of the endstop.
#define Z_MIN_PROBE_ENDSTOP_INVERTING true // Set to true to invert the logic of the probe.

#define INVERT_X_DIR false
#define INVERT_Y_DIR false
#define INVERT_Z_DIR false

#define EEPROM_SETTINGS
#define SDSUPPORT
#define REPRAP_DISCOUNT_FULL_GRAPHIC_SMART_CONTROLLER

#define SOFT_PWM_SCALE 0
#define FAN_SOFT_PWM
```

## Fichier Marlin/Configuration_adv.h
```
#define E0_AUTO_FAN_PIN 7
```