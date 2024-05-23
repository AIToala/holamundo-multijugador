# BACKUP
# Pasantías AITB.

## Introducción
Modulo de documentación de la pasantía de la empresa **IPSP**, en el cual se detallan los procesos y actividades realizadas durante el periodo de pasantía.

## Objetivo
El objetivo de la pasantía es realizar el backend y frontend de la funcionalidad de **Guia de Remision** en la sección de **Transferencia de Bodega**. La guia de remision debe ser generada en formato PDF y debe contener la información requerida por el SRI.

## Información requerida
La información requerida para la guia de remision en transferencia de bodega es la siguiente:
- **Información de la empresa**: Nombre de la empresa, Razón Social de la empresa, Nombre Comercial de la empresa, RUC, Direccion de Matriz, Información Adicional (Telefono, Ciudad, Provincia).
- **Información del Transportista**: Nombre del transportista, RUC, Placa del vehiculo.
- **Información del Conductor**: Nombre del conductor, Cedula del conductor, Licencia del conductor.
- **Información de la Guia de Remision**: Numero de guia de remision, Fecha de emision, Fecha de inicio de transporte, Fecha de fin de transporte, Punto de partida, Punto de llegada, Motivo de traslado, Observaciones.
- **Información de la Mercaderia**: Cantidad, Descripcion, Código.
- **información SRI**: Autorización SRI (Número de Autorización), Clave Acceso, Fecha de Autorización, Agente de Retención, Contribuyente Especial.

## Funcionalidades a realizar
- **Generación de Guia de Remision**: Se generara la guia de remision en la sección de **Transferencia de Bodega**.
- **Visualización de Guia de Remision**: Se podra visualizar la guia de remision en formato PDF en la sección de **Transferencia de Bodega**.
- **Validacion de Guia de Remision**: Se validara la guia de remision en el backend antes de ser guardada en la sección de **Transferencia de Bodega**.
- **Guardado de Guia de Remision**: Se podra guardar la guia de remision en formato PDF en la sección de **Transferencia de Bodega**.

## Funcionalidades a reutilizar
- **Reutilización de Funcionalidades de Exportación**: Se reutilizaran funcionalidades de exportación para la generación de la guia de remision en la sección de **Transferencia de Bodega**.
- **Reutilización de Funcionalidades de SRI**: Se reutilizaran funcionalidades de SRI para la generación de la guia de remision en la sección de **Transferencia de Bodega**.

## Entregables
- [ ] Documentación de la funcionalidad a realizar.
- [x] Template de comprobante para la guia de remision requerida en seccion Transferencia de Bodega.
- [ ] Controladores, modelos y vistas para crear lo necesario para el backend de la funcionalidad a realizar.
- [x] Pruebas de validacion unitarias para la guia de remision en transferencia de bodega.
- [ ] Rutas API para MovimientoInventarioController o un nuevo controlador para la guia de remision en transferencia de bodega.
- [ ] Metodos necesarios para la guia de remision en transferencia de bodega en store de inventarioConsumo.
- [ ] Chequeo de llamadas a funciones del controlador de SRI en la vista .vue para la guia de remision en transferencia de bodega.
- [ ] Tabla que relacione GuiaRemisionCab con MovimientoInventario/SolicitudTransferenciaBodega para su respectiva visualizacion de ser requerida.
- [ ] Generación de la guia de remision en la sección de **Transferencia de Bodega**.

## Actividades
- [x] Revision de template de comprobante para la guia de remision requerida en seccion Transferencia de Bodega utilizando guias de remision antiguas e informacion provenientes del SRI.
- [x] Revisar controladores, modelos y vistas para crear lo necesario para el backend de la funcionalidad a realizar (Guia de Remision en Transferencia de Bodega).
- [x] Crear pruebas de validacion o unitarias para la guia de remision en transferencia de bodega.
- [x] Estudiar PHPUnit y Mocking para crear tests de validacion o unitarias para la guia de remision en transferencia de bodega apropiados.
- [x] Chequear si funcionalidades existentes en exportacion pueden ser reutilizadas para la guia de remision en transferencia de bodega.
- [x] Crear controlador que valide XML de guia de remision en transferencia de bodega. (TransferenciaGuiaRemisionController)
- [ ] Agregar de ser necesario las rutas API para MovimientoInventarioController o un nuevo controlador para la guia de remision en transferencia de bodega.
- [ ] *PENDIENTE DE CREAR* Crear Tabla que relacione GuiaRemisionCab con MovimientoInventario/SolicitudTransferenciaBodega.
- [x] Crear una regla para Validator que realice todos los metodos de validacion de documentos XML para la guia de remision y a futuro de todos los documentos. Evitando de esta forma escribir el mismo codigo en diferentes controladores. Preguntar cual opcion es la mas viable.
- [x] Verificar que la regla para validacion cumpla con los requerimientos de la guia de remision en transferencia de bodega.
- [ ] Preguntar cual opcion es la mas viable para realizar validacion de documentos XML en la guia de remision en transferencia de bodega. Las opciones son usar la regla de validacion creada usando Validator (BACKEND), validaciones en la vista TransferenciaBodega (FRONTEND) o enviar directamente el XML a SRI para su validacion.

## Dudas
- No existe conexion entre GuiaRemisionCab y MovimientoInventario/SolicitudTransferenciaBodega. ¿Como se conectaran estos modelos?
- No es posible realizar tests con la version phpunit y collision actuales. ¿Se puede realizar downgrade de estas dependencias?
- Existe una tabla que proporciona la configuración de los documentos XML en la base de datos, la cual es util para crear plantilla PDF de guia de remisión. El mismo esta en la carpeta de exportaciones. ¿Se puede reutilizar esta tabla para la guia de remision en transferencia de bodega?
- Storage es local? ¿Se puede utilizar para guardar los XML de guia de remision en transferencia de bodega?
- Al realizar el guardado de una Guia de Remision mediante el metodo updateGuiaRemision de SRIController, se requiere crear un nuevo request para generar clave acceso y se realiza un log de lo ingresado o actualizado. PuntoEmision?
- Proceso entendido de la generación de la guia de remision en la sección de **Transferencia de Bodega**:
  - [x] Se valida la guia de remision en el backend antes de ser guardada.
  - [ ] Se guarda la guia de remision en la base de datos como GuiaRemisionTransfBodega.
  - [ ] Se guarda los detalles de la guia de remision en la base de datos como GuiaRemisionTransfBodegaDet.
  - [ ] Se previsualiza la guia de remision en formato PDF.
  - [ ] Se edita / actualiza la guia de remision en la base de datos en funcion de los cambios realizados en la transferencia de bodega.
  - [ ] Al borrar el movimiento de transferencia de bodega, se borrara la guia de remision asociada.
  - [ ] Se aprueba la guia de remision en la sección de **Transferencia de Bodega**.
  - [ ] Se genera XML de guia de remision en la sección de **Transferencia de Bodega**.
  - [ ] Se envia a SRI para la revision de guia de remision en la sección de **Transferencia de Bodega**.
  - [ ] Se comprueba con multiples llamadas a SRI si la guia de remision fue validada.
  - [ ] Se aprueba la guia de remision en la sección de **Transferencia de Bodega**.

## Notas
### Metodos a revisar
- generateXML: /app/Http/Controllers/SRIController.php
- updateGuiaRemision: /app/Http/Controllers/SRIController.php
- aprobarGuiaRemision: /app/Http/Controllers/SRIController.php
- editarGuiaRemision: /app/Http/Controllers/SRIController.php
- getGuiaRemision: /app/Http/Controllers/SRIController.php
### Rutas API a revisar
- inventario_consumo: /api/admin/inventario-consumo
### Store a revisar
- inventarioConsumo: /resources/js/store/inventarioConsumo
### Formatos
- Formato de Guia de Remision (PDF) - pdfs/comercial/guiaRemision.blade.php

### Dependencias con problemas
- **"nunomaduro/collision": "^7.5"** - Requiere Laravel 10.X
- **"phpunit/phpunit": "^10.0.14"**

Solucion temporal:
Downgrade de phpunit/phpunit a ^9.2.4 y nunomaduro/collision a ^6.1

### Similitudes para mejorar Codigo
