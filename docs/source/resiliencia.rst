Resiliencia
#######################

.. Capacidad del sistema de resisitir, absober y sobreponerse al impacto de una amenaza.

Modelo multicriterio
*********************

.. imagen:: ../recursos/vulnerabilidad_resiliencia_fv_23nov2020.png
    :align: center

Insumos
*********

Biológica
===========

Biodiversidad
--------------
*Resiliencia - Biológica*

    Clasificación de tipos de vegetación costera (a mayor biodiversidad, mayor resiliencia) 
    ejemplo: manglar, pastos marinos, vegetación duna, otros tipos de vegetación sumergible

    **peso local:** 0.50

    **insumo:** |ifv_biodiversidad_yuc.tif|


    **Definición:** Esta capa representa la presencia de vegetación costera en la zona de estudio.

    **Tipo de función:** Discreta

    .. imagen:: ../recursos/fv/fv_d_res_biodiversidad.png


    ========= ===================== ====
    Categoria Descripción            fv
    ========= ===================== ====
    1         Dunas Costeras        0.33
    2         Manglar               1.00
    3         Tular                 0.09
    4         Vegetación de peten   0.31
    5         vegetación arbustiva  0.06
    ========= ===================== ====
   
   
    **Resultado:** SIG/desarrollo/sig_papiit/entregables/resiliencia/biologica/biodiversidad_yuc/fv_biodiversidad_yuc_100m.tif

    **Nombre de la capa:** |fv_biodiversidad_yuc.tif|


    **issue:**  |Biodiversidad|


Servicios ambientales
---------------------
Presencia de tipos de vegetación que proveen protección a la línea de costa y hábitat (pastos marinos, dunas costeras y manglar)

**Protección costera**

Presencia de tipos de vegetación que proveen protección a la línea de costa (dunas costeras, manglares, humedales)

*Resiliencia - Biológica - Servicios ambientales*

**Peso local:** 0.75

**Insumos:**


    **Vegetación acúatica**
        
        *Resiliencia - Biológica - Servicios ambientales - Protección costera*

        **Peso local:** 0.16

        **Insumo:** ifv_v_acuatica.tif

        **Definición:** Distancia entre los pastos y la línea de costa 

        **Tipo de función:** continua - Logística invertida

        .. note::
            Esta capa fue procesada en grass 7


        archivo json: fv_exp_bio_v_acuatica.json

        ``centro:1500,
        min:0,
        max:3000,
        saturacion: 3,
        k:0.0834999999999999``

        .. image:: ../recursos/fv/fv_c_res_veg_acuatica.png

        
        **Resultado:** sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/prot_costera_yuc/fv_v_acuatica_yuc_100m.tif



        

    **Entidades protectoras**

        **Peso local:** 0.84
        
        **Definición:** Presencia de manglar y Dunas costeras que ofrece

        **Resultado:** sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/prot_costera_yuc/fv_entidades_protectoras.tif

        .. image:: ../recursos/fv/fv_d_res_ent_protector.png




**Provisión**

    *Resiliencia - Biológica - Servicios ambientales*

    Presencia de tipos de vegetación que proveen alimento, materias primas, recursos genéticos

    **Peso local**:0.50

    **Insumo:** |ifv_provision_yuc.tif|


    **Definición:**

    **Tipo de función:** Discreta 

        ========= ===================== ====
        Categoria Descripción           fv
        ========= ===================== ====
        1         Dunas Costeras        0.32
        2         Manglar               1.00
        3         Tular                 0.08
        4         Vegetación de peten   0.29
        5         vegetación arbustiva  0.05
        ========= ===================== ====


    **Resultado:** /sig_papiit/entregables/resiliencia/biologica/serv_ambientales_yuc/provision_yuc/fv_provision_yuc_100m.tif
  
    **Nombre de la capa:**  |fv_provision_yuc.tif| **falta metadato**
  
    **issue** |Provisión|



    

Física
=======



Elevación 
---------------
*Resiliencia - Física*
    


    **Peso local:**:0.60

    **Insumo:** |ifv_elev_yuc.tif|

    **Definición:**     El insumo para la generación de esta capa proviene del Continuo de Elevaciones Mexicano (CEM) de INEGI,
    a la cual se le aplico una funcion de valor *concava decreciente*

    **Tipo de función:** continua - Concava creciente

        arhivo json: 

        ``min: 0
        max: 31
        gama: 0.01975
        saturacion:``


         .. imagen:: ../recursos/fv/fv_c_res_elevacion.png

    **Resultado:** SIG/desarrollo/sig_papiit/entregables/resiliencia/fisica/elev_yuc/fv_elev_yuc.tif

    **Nombre de la capa:** |fv_elev_yuc.tif|

    **issue** |Elevación|
    
   

Tipo de litoral
-----------------
*Resiliencia - Física*
    
    **Peso local**:0.40

    
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
        Categoria Descripción fv
        ========= =========== ====
        1         Arenoso     0.54
        2         Artificial  1.00
        3         Lodoso      0.19
        4         Vegetado    1.00
        ========= =========== ====

    **Resultado:** SIG/desarrollo/sig_papiit/entregables/resiliencia/fisica/t_litoral_yuc/fv_tipo_litoral_yuc_v2.tif

    **Nombre de la capa:** |fv_tipo_litoral_yuc.tif|


    **issue** |Tipo de litoral|



**Resultado**
-------------------

``res_fisica = fv_ancho_playa_yuc * 0.62 + fv_duna_yuc * 0.27 + fv_elev_yuc * 0.06 + fv_tipo_litoral_yuc * 0.05``


Ruta: SIG/desarrollo/sig_papiit/entregables/resiliencia/salida/res_fisica.tif 


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