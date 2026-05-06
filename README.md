# Implementación de Autoload PSR-4 con Composer

Proyecto desarrollado para implementar carga automática de clases en PHP utilizando Composer y el estándar PSR-4.

# Objetivos

- Comprender el funcionamiento del estándar PSR-4.
- Configurar Composer para utilizar autoload.
- Organizar clases mediante namespaces.
- Eliminar el uso excesivo de include y require manuales.

# Tecnologías Utilizadas

- PHP
- Composer
- PSR-4

# Guía de Instalación

## 1. Clonar el repositorio

bash
git clone URL_DEL_REPOSITORIO

## 2. Entrar al proyecto

bash
cd nombre-del-proyecto

## 3. Instalar dependencias y generar autoload

bash
composer install

Este comando genera automáticamente la carpeta:

vendor/

y el archivo:

vendor/autoload.php

necesario para la carga automática de clases.

# Configuración de Composer

## Archivo composer.json

json
{
    "autoload": {
        "psr-4": {
            "App\\":"App/",
            "Database\\":"Database/"
        }
    }
}

# Implementación del Autoload

## Clase Usuario

php

namespace App;

Class User {

public function getName():string
{
    return "Dave";
}

}
?>

## Archivo Principal

php

use App\User;
use Database\Model\ProductModel;

require "vendor/autoload.php";

$user = new User;
echo $user->getName();

#Prueba de ejecucion
<img width="511" height="185" alt="image" src="https://github.com/user-attachments/assets/6489ad20-9536-42ed-9000-8143764927cf" />

# Conclusiones Técnicas

## Mantenibilidad

El uso de Composer y PSR-4 facilita agregar nuevas clases sin modificar archivos globales del proyecto, permitiendo una mejor organización y mantenimiento del código.

## Eficiencia de Memoria

La carga automática implementa un sistema de carga bajo demanda (Lazy Loading), permitiendo que las clases se carguen únicamente cuando son necesarias durante la ejecución.

## Estandarización

El estándar PSR-4 mejora el trabajo colaborativo al mantener una estructura organizada y reconocida internacionalmente para proyectos PHP.
