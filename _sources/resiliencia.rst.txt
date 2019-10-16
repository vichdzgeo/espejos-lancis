Criterio de resiliencia
#######################


.. imagen:: ../recursos/vulnerabilidad_resiliencia_fv.png


Insumos
*********

Biológica
===========

Biodiversidad
--------------
*Resiliencia - Biológica*

    **peso local:** 0.50

    **insumo:** |ifv_biodiversidad_yuc.tif|


    **Definición:** Esta capa representa la presencia de vegetación costera en la zona de estudio.

    **Tipo de función:** Discreta

    .. imagen:: ../recursos/fv/fv_d_res_biodiversidad.png


    ========= ===================== ====
    Categoria Descripción           Peso
    ========= ===================== ====
    1         Dunas Costeras        0.33
    2         Manglar               1.00
    3         Tular                 0.09
    4         Vegetación de peten   0.31
    5         vegetación arbustiva  0.06
    ========= ===================== ====
   
   
    **Resultado:** SIG/desarrollo/sig_papiit/entregables/resiliencia/biologica/biodiversidad_yuc/fv_biodiversidad_yuc.tif

    **Nombre de la capa:** |fv_biodiversidad_yuc.tif|


    **issue:**  |Biodiversidad|


Servicios ambientales
---------------------

**Protección costera**


*Resiliencia - Biológica - Servicios ambientales*

**Peso local:** 0.75

**Insumos:**


    **Vegetación acúatica**
        
        *Resiliencia - Biológica - Servicios ambientales - Protección costera*

        **Peso local:** 0.16

        **Insumo:** ifv_v_acuatica.tif

        **Definición:** Distancia entre los pastos y la línea de costa 

        **Tipo de función:** continua - Logística

        .. note::
            Esta capa fue procesada en grass 7


        archivo json: fv_exp_bio_v_acuatica.json

        ``centro:1500,
        min:0,
        max:3000,
        saturacion: 3,
        k:0.0834999999999999``

        .. image:: ../recursos/fv/fv_c_res_veg_acuatica.png

        
        **Resultado:** sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/prot_costera_yuc/fv_v_acuatica_yuc.tif


        **Nombre de la capa:** fv_v_acuatica_yuc.tif

        



    **Dunas costeras**

        *Resiliencia - Biológica - Servicios ambientales - Protección costera*

        **Peso local:** 0.14

        **Insumo:** ifv_dunas_presencia_yuc.tif

        **Definición:** 

        **Tipo de función:**   Discreta (Presencia 1, ausencia 0)

        **Resultado:** /sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/prot_costera_yuc/fv_dunas_presencia_yuc.tif

        **Nombre de la capa:** fv_dunas_presencia_yuc.tif

       


                

    **Manglar**
    
        *Resiliencia - Biológica - Servicios ambientales - Protección costera*

        **Peso local**:0.70

        **Insumo:** ifv_manglar_presencia_yuc.tif

        **Definición:**

        **Tipo de función:** Discreta (Presencia 1, ausencia 0)

        **Resultado:**  /sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/prot_costera_yuc/fv_manglar_presencia_yuc.tif

        **Nombre de la capa:** fv_manglar_presencia_yuc.tif

    
    **Integración**

    fv_proteccion_costera = fv_v_acuatica_yuc * 0.16 + fv_dunas_presencia_yuc * 0.14 + fv_manglar_presencia_yuc * 0.70
        
    **Resultado**
    SIG/desarrollo/sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/prot_costera_yuc/fv_prot_costera_yuc.tif

    **Nombre de la capa:**  fv_prot_costera_yuc.tif **falta metadato**
  
    **issue** Protección costera **Agregar la liga del metadato**


**Provisión**

    *Resiliencia - Biológica - Servicios ambientales*

    **Peso local**:0.50

    **Insumo:** |ifv_provision_yuc.tif|


    **Definición:**

    **Tipo de función:** Discreta 

        ========= ===================== ====
        Categoria Descripción           Peso
        ========= ===================== ====
        1         Dunas Costeras        0.19
        2         Manglar               0.56
        3         Tular                 0.05
        4         Vegetación de peten   0.17
        5         vegetación arbustiva  0.03
        ========= ===================== ====


    **Resultado:** /sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/provision_yuc/fv_provision_yuc.tif
  
    **Nombre de la capa:**  |fv_provision_yuc.tif| **falta metadato**
  
    **issue** |Provisión|


    **Integración**

    serv_ambientales_yuc  = fv_prot_costera_yuc * 0.75 + fv_provision_yuc * 0.25 

    **Resultado**  

    SIG/desarrollo/sig_papiit/entregables/resiliencia/salida/serv_ambientales.tif

    


Resultado 
-----------
``res_biologica = fv_biodiversidad_yuc * 0.50 + serv_ambientales_yuc * 0.50``


Ruta:  SIG/desarrollo/sig_papiit/entregables/resiliencia/salida/res_biologica.tif


Física
=======

Ancho de playa 
---------------
*Resiliencia - Física*
    

    **Peso local:**:0.62

    **Insumo:** |ifv_ancho_playa_yuc.tif|

    **Definición:** Esta capa representa la presencia del ancho de playa en la costa.

    **Tipo de función:**

    .. imagen:: ../recursos/fv/fv_c_res_aplaya.png

    **Resultado:**

    **Nombre de la capa:** |fv_ancho_playa_yuc.tif|

    **issue** |Ancho de playa|

    

Dunas costeras
---------------
*Resiliencia - Física*
    
    **Peso local:**:0.27

    **Insumo:** |ifv_duna_yuc.tif|

    **Definición:** Esta capa representa la presencia de dunas costeras en la costa, El insumo ocupado
    para la generación de esta capa corresponde a información del POETY

    **Tipo de función:**

    **Resultado:**

    **Nombre de la capa:** |fv_duna_yuc.tif|

    **issue** |Dunas costeras|



Elevación 
---------------
*Resiliencia - Física*
    


    **Peso local:**:0.06

    **Insumo:** |ifv_elev_yuc.tif|

    **Definición:**     El insumo para la generación de esta capa proviene del Continuo de Elevaciones Mexicano (CEM) de INEGI,
    a la cual se le aplico una funcion de valor *concava decreciente*

    **Tipo de función:** continua - Concava creciente
        .. warning:: 
            por verificar


        arhivo json: 

        ``min: -8
        max: 25
        gama: 0.01975
        saturacion:``


         .. imagen:: ../recursos/fv/fv_c_res_elevacion.png

    **Resultado:** SIG/desarrollo/sig_papiit/entregables/resiliencia/fisica/elev_yuc/fv_elev_yuc.tif

    **Nombre de la capa:** |fv_elev_yuc.tif|

    **issue** |Elevación|
    
   

Tipo de litoral
-----------------
*Resiliencia - Física*
    
    **Peso local**:0.05

    
    **Insumo:** |ifv_tipo_litoral_yuc.tif|

    **Definición:** Esta capa representa la presencia de diferentes tipos de litoral, estos fueron clasificados
    conforme a la siguiente tabla, el insumo ocupado es la capa de uso de suelo y vegetación 
    serie VI de INEGI


    **Tipo de función:** Discreta

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

    **Resultado:** SIG/desarrollo/sig_papiit/entregables/resiliencia/fisica/t_litoral_yuc/fv_tipo_litoral_yuc.tif

    **Nombre de la capa:** |fv_tipo_litoral_yuc.tif|


    **issue** |Tipo de litoral|



**Resultado**
-------------------

``res_fisica = fv_ancho_playa_yuc * 0.62 + fv_duna_yuc * 0.27 + fv_elev_yuc * 0.06 + fv_tipo_litoral_yuc * 0.05``


Ruta: SIG/desarrollo/sig_papiit/entregables/resiliencia/salida/res_fisica.tif 



Integración
============

resiliencia = res_biologica * 0.50 + res_fisica * 0.50


Resultado
==========

SIG/desarrollo/sig_papiit/entregables/resiliencia/salida/resiliencia_yuc.tif


.. ligas

.. Biodiversidad


.. |ifv_biodiversidad_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/a138bbf7-edfd-4220-85f0-3758b3501d2b" target="_blank">ifv_biodiversidad_yuc.tif</a>

.. |fv_biodiversidad_yuc.tif| raw:: html 

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/eb347808-46b3-48b1-a536-5718fd7f560d" target="_blank">fv_biodiversidad_yuc.tif</a>


.. |Biodiversidad| raw:: html|

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/63" target="_blank">Biodiversidad</a>

.. Servicios ambientales
.. Protección costera 

.. raw:: html

    <a href= "" target="_blank"></a>
.. raw:: html 

    <a href= "" target="_blank"></a>

.. raw:: html 

    <a href= "" target="_blank"></a>


.. Provisión 

.. |ifv_provision_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/150afcd1-e2b3-4fd8-9818-ac123c311154" target="_blank">ifv_provision_yuc.tif</a>

.. |fv_provision_yuc.tif| raw:: html 

    <a href= "" target="_blank">fv_provision_yuc.tif</a>

.. |Provisión| raw:: html 

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/49" target="_blank">Provisión</a>


.. Fisica
.. Ancho de playa 

.. |ifv_ancho_playa_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/2ee70ef3-59d1-4ba7-8db2-c6e9e14342ff" target="_blank">ifv_ancho_playa_yuc.tif</a>

.. |fv_ancho_playa_yuc.tif| raw:: html 

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/67c144b7-7930-49e7-a9ef-c535c87d75ac" target="_blank">fv_ancho_playa_yuc.tif</a>

.. |Ancho de playa| raw:: html 

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/68" target="_blank">Ancho de playa</a>




.. Dunas costeras

.. |ifv_duna_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/0185f4bf-48d6-46c1-973d-917f41af9d46" target="_blank">ifv_duna_yuc.tif</a>

.. |fv_duna_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/f7f5efdf-c2c7-47b5-8a00-ffb5281d0007" target="_blank">fv_duna_yuc.tif</a>

.. |Dunas costeras| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/61" target="_blank">Dunas costeras</a>


.. Elevación 

.. |ifv_elev_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/c000fff6-e339-4a90-a0fa-1910086309d4" target="_blank">ifv_elev_yuc.tif</a>

.. |fv_elev_yuc.tif| raw:: html 

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/c000fff6-e339-4a90-a0fa-1910086309d4" target="_blank">fv_elev_yuc.tif</a>

.. |Elevación| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/58" target="_blank">Elevación</a>


.. Tipo de litoral 

.. |ifv_tipo_litoral_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/718b3df0-6f05-4a43-9278-e977b4549f45" target="_blank">ifv_tipo_litoral_yuc.tif</a>

.. |fv_tipo_litoral_yuc.tif| raw:: html 

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/cf4aebc2-c97c-490f-a166-1592da725a5c" target="_blank">fv_tipo_litoral_yuc.tif</a>

.. |Tipo de litoral| raw:: html 

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/54" target="_blank">Tipo de litoral</a>