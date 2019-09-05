Criterio de sensiblidad
##########################


Insumos
*********

Biológica
===========

**Peso**:0.50

**Nombre del archivo**:


Vegetación acuatíca
-------------------------
    *Sensibilidad - biológica*

    Criterio: vegetacion acuatica 

    **peso**:0.34

    
    Esta capa representa la distancia a la que se encuentran los pastos marinos dentro de la costa, la distancia 
    va de 0 a 3000 metros. esta capa es procesada con una función de valor logística, quedando sus valores
    de 0 a 1.

    nombre del archivo: fv_v_acuatica_yuc.tif

    ``mínimo: 0.0
    máximo:1.00``

    función continua - Logística

    insumo: ifv_v_acuatica.tif

    .. note::
        Esta capa fue procesada en grass 7
    
    
    archivo json: fv_exp_bio_v_acuatica.json

    ``centro:1500,
    min:0,
    max:3000,
    saturacion: 3,
    k:0.0834999999999999``

    .. imagen:: ../recursos/fi_fv_sen_bio_v_acuatica.JPG



    **Metadatos**: |e_fv_v_acuatica_yuc|

    **Ruta**: SIG/desarrollo/sig_papiit/entregables/sensibilidad/biologica/v_acuatica_yuc/fv_v_acuatica_yuc.tif

    **issue**: |vegetacion_acuatica|

Vegetación costera
---------------------
    *Sensibilidad - Biológica*

    Criterio: Vegetación costera

    **peso** : 0.66

    **Nombre de la capa**:fv_costera_presencia.tif

    Esta capa representa la integración de las capas de presencia de 
    vegetación de duna constera con la capa de manglar.

    vegetacion costera = ifv_v_dunas_presencia(0.80) + ifv_v_manglar_presencia(0.20)

    **metadatos**

    **issue**



    
    Manglar
    ^^^^^^^
    *Sensibilidad - Biológica - Vegetación costera*

    **peso**: 0.20

    **Nombre del archivo**: ifv_manglar_presencia.tif
    
    Esta capa representa la presencia de manglar en la zona de estudio, es una función
    discreta donde el valor de pixel igual a 1.


    Duna costera
    ^^^^^^^^^^^^
    *Sensibilidad - Biológica - Vegetación costera*

    **peso**: 0.80
    
    **nombre_del_archivo**: ifv_dunas_presencia.tif

    Esta capa representa la presencia de vegetacion de dunas costeras en la zona de estudio, Es una función
    discreta donde el valor de pixel igual a 1.



Física
=======

**Peso**:0.50

**Nombre del archivo**:

Esta capa representa la integración de las capas Ancho de playa, Dunas costeras
Elevación y tipo de litoral con sus respectivos pesos. 

``Física = ancho_de_playa*0.33 + dunas_costeras*0.56 + elevacion*0.04 + tipo_litoral * 0.07``





Ancho de playa 
---------------
*Sensibilidad - Física*
    
    **Criterio**:

    **Peso**:0.33

    **Nombre del archivo**: fv_ancho_playa_yuc.tif

    Esta capa representa el ancho de playa en la costa. El insumo ocupado para la
    generación de esta capa corresponde a información dle POETY, se ocupo una función 
    logística para representar esta capa

    Función Continua - Logística

    ``min:0
    max:54
    center:23
    k:0.1325
    saturación:5``

    .. image:: ../recursos/fi_fv_sen_fis_ancho_playa.JPG
     

Dunas costeras
---------------
*Sensibilidad - Física*
    
    **Criterio**: dunas costeras

    **Peso**:0.56

    **Nombre del archivo**: fv_duna_yuc.tif

    Esta capa representa la presencia de dunas costeras en la costa, El insumo ocupado
    para la generación de esta capa corresponde a información del POETY combinado con 
    el ancho de playa.

Elevación 
---------------
*Sensibilidad - Física*
    
    **Criterio**:

    **Peso**:0.04

    **Nombre del archivo**:fv_elevacion.tif

    El insumo para la generación de esta capa proviene del Continuo de Elevaciones Mexicano (CEM) de INEGI,
    a la cual se le aplico una funcion de valor *concava creciente* 

    Funcion continua - Concava creciente

    arhivo json: 

    ``min:0
    max: 31
    gama: 0.01975
    saturacion: 13``


    .. image:: ../recursos/fi_fv_sen_fis_elev.JPG

Tipo de litoral
-----------------
*Sensibilidad - Física*
    
    **Criterio**:

    **Peso**:0.07

    **Nombre del archivo**: fv_tipo_litoral_yuc.tif

    Esta capa representa la presencia de diferentes tipos de litoral, estos fueron clasificados
    conforme a la siguiente tabla, el insumo ocupado es la capa de uso de suelo y vegetación 
    serie VI de INEGI

    ================================ ====================
    Tipo de Vegetación	              Tipo de litoral
    ================================ ====================
    Área desprovista de vegetación	  Arenoso
    Sin vegetación aparente	          Arenoso
    vegetación dunas costeras	      Arenoso
    Acuícola	                      Artificial
    Urbano construido	              Artificial
    Agua	                          Lodoso
    Peten	                          Lodoso
    Vegetación halofila, hidrofila	  Lodoso
    Agricultura de riego anual	      Vegetado
    Agricultura de riego permanente	  Vegetado
    Manglar	                          Vegetado
    Palmar, pastizal,manglar, tular	  Vegetado
    Vegetación secundaria (5 clases)  Vegetado
    ================================ ====================

    Quendando de esta forma los pesos asignados para cada categoría.


    ========= =========== ====
    Categoria Descripción Peso
    ========= =========== ====
    1         Arenoso     0.55
    2         Artificial  0.11
    3         Lodoso      1.00
    4         Vegetado    0.31
    ========= =========== ====
 
 
