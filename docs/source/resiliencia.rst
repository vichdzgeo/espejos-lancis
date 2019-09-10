Criterio de resiliencia
##########################

.. imagen:: ../recursos/vulnerabilidad_resiliencia_04sep2019.png

Insumos
*********

Biológica
===========

**Peso**:0.50

**Nombre del archivo**:


Biodiversidad
--------------
*Resiliencia - Biológica*

    **peso**:0.50

    **Nombre del arhivo**: fv_biodiversidad_yuc.tif


    Esta capa representa la presencia de vegetación costera en la zona de estudio.

    Funcion Discreta

    ========= ===================== ====
    Categoria Descripción           Peso
    ========= ===================== ====
    1         Dunas Costeras        0.33
    2         Manglar               1.00
    3         Tular                 0.09
    4         Vegetación de peten   0.31
    5         vegetación arbustiva  0.06
    ========= ===================== ====

    insumo de la funcion de valor: ifv_biodiversidad.tif
    donde los valores de pixel corresponden al número de la categoría descrita anteriormente.



Servicios ambientales
---------------------
    *Resiliencia - Biológica*

    **peso**: 0.50

    **Nombre del archivo**:

    Esta capa es el resultado de la integración de la capa de protección costera y la capa de Provisión

    ``servicios ambientales = proteccion_costera*0.75 + provision*0.25``


    Proteccion costera
    -------------------
    *Resiliencia - Biológica - Servicios ambientales*
    
    **Peso**:0.50

    **Nombre del archivo**:


        vegetacion acuatica
        ~~~~~~~~~~~~~~~~~~~~
        **Resiliencia - Biológica - Servicios ambientales - Protección costera*

        **Peso**:0.16

        **Nombre del archivo**: fv_v_acuatica.tif

        Esta capa representa la distancia a la que se encuentran los pastos marinos dentro de la costa, la distancia 
        va de 0 a 3000 metros. esta capa es procesada con una función de valor logística, quedando sus valores
        de 0 a 1.

        nombre del archivo:

        ``mínimo: 0.0
        máximo:1.00``

        función continua - Logística

        insumo:

        .. note::
            Esta capa fue procesada en grass 7
        
        
        archivo json: fv_exp_bio_v_acuatica.json

        ``centro:1500,
        min:0,
        max:3000,
        saturacion: 3,
        k:0.0834999999999999``

        .. image:: ../recursos/fi_fv_exp_bio_v_acuatica.JPG


        Dunas costeras
        ~~~~~~~~~~~~~~
        **Resiliencia - Biológica - Servicios ambientales - Protección costera*

        **Peso**:0.14

        **Nombre del archivo**:

        Manglar
        ~~~~~~~~
        **Resiliencia - Biológica - Servicios ambientales - Protección costera*

        **Peso**:0.70

        **Nombre del archivo**:

    Provisión
    ^^^^^^^^^^
    *Resiliencia - Biológica - Servicios ambientales*

    **Peso**:0.50

    **Nombre del archivo**:

    ========= ===================== ====
    Categoria Descripción           Peso
    ========= ===================== ====
    1         Dunas Costeras        0.19
    2         Manglar               0.56
    3         Tular                 0.05
    4         Vegetación de peten   0.17
    5         vegetación arbustiva  0.03
    ========= ===================== ====








Física
=======
*Resiliencia 
**Peso**:0.50

**Nombre del archivo**:

Esta capa representa la integración de las capas Ancho de playa, Dunas costeras
Elevación y tipo de litoral con sus respectivos pesos. 

``Física = ancho_de_playa*0.33 + dunas_costeras*0.56 + elevacion*0.04 + tipo_litoral * 0.07``





Ancho de playa 
---------------
*Resiliencia - Física*
    
    **Criterio**:

    **Peso**:0.62

    **Nombre del archivo**:

    Esta capa representa la presencia del ancho de playa en la costa.

Dunas costeras
---------------
*Resiliencia - Física*
    
    **Criterio**:

    **Peso**:0.27

    **Nombre del archivo**:

    Esta capa representa la presencia de dunas costeras en la costa, El insumo ocupado
    para la generación de esta capa corresponde a información del POETY

Elevación 
---------------
*Resiliencia - Física*
    
    **Criterio**:

    **Peso**:0.06

    **Nombre del archivo**:

    El insumo para la generación de esta capa proviene del Continuo de Elevaciones Mexicano (CEM) de INEGI,
    a la cual se le aplico una funcion de valor *concava decreciente* 

    Funcion continua - Concava creciente

    .. warning:: 
        por verificar


    arhivo json: 

    ``min: -8
    max: 25
    gama: 0.01975
    saturacion: ``


    .. imagen:: ../recursos/fi_fv_sen_fis_elevacion.JPG

Tipo de litoral
-----------------
*Resiliencia - Física*
    
    **Criterio**:

    **Peso**:0.05

    **Nombre del archivo**:

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
    1         Arenoso     0.28
    2         Artificial  0.05
    3         Lodoso      0.52
    4         Vegetado    0.15
    ========= =========== ====
 
