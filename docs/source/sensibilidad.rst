Susceptibilidad
##########################

Modelo multicriterio
*********************

.. imagen:: ../recursos/vulnerabilidad_susceptibilidad_1sep2020_fv.png
    :align: center


Insumos
*********

Biológica
===========

Vegetación costera
---------------------
    *susceptibilidad - Biológica*

    **peso local** : 0.66

    **Definición:** integración de las capas de presencia de vegetación de duna constera con la capa de manglar.
    

Insumos
^^^^^^^^^

    **Manglar**

        *susceptibilidad - Biológica - Vegetación costera*

        **peso local:** 1.0

        **Insumo:**  ifv_manglar_presencia_yuc.tif
        
        **Definición:** presencia de manglar en la zona de estudio

        **Tipo de función:** Binaria

    **Duna costera**

    *susceptibilidad - Biológica - Vegetación costera*

        **peso local:**: 0.25
        
        **Insumo**: ifv_dunas_presencia_yuc.tif

        **Definición:** presencia de vegetacion de dunas costeras en la zona de estudio

        **Tipo de función:** Binaria


**Resultado:**: SIG/desarrollo/sig_papiit/entregables/susceptibilidad/biologica/v_costera_yuc/fv_v_costera_presencia_yuc_100m.tif

**Nombre de la capa:** |fv_v_costera_presencia_yuc.tif|

**issue**:  |Vegetación costera|






Física
=======


Dunas costeras
---------------
*susceptibilidad - Física*
    
    **Peso local**:0.56

    **Insumo:** |ifv_duna_yuc.tif|

    **Definición:** Esta capa representa la presencia de dunas costeras en la costa, El insumo ocupado
    para la generación de esta capa corresponde a información del POETY combinado con 
    el ancho de playa.

    **Tipo de función:** Binaria

    **Resultado:** C:/Dropbox (LANCIS)/SIG/desarrollo/sig_papiit/entregables/susceptibilidad/fisica/duna_yuc/fv_duna_yuc/fv_duna_yuc_100m.tif

    **Nombre de la capa:** |fv_duna_yuc.tif|

    **issue** |Duna costera|

Elevación 
---------------
*susceptibilidad - Física*
    
    **Peso local:**:0.04

    **Insumo:** |ifv_elev_yuc_v2.tif|

    **Definición:** El insumo para la generación de esta capa proviene del Continuo de Elevaciones Mexicano (CEM) de INEGI,
    a la cual se le aplico una funcion de valor *concava creciente* 

    **Tipo de función:** continua - Concava creciente

    arhivo json: 

    ``min:0
    max: 31
    gama: 0.01975
    saturacion: 13``


    .. image:: ../recursos/fv/fv_c_sens_elevacion.png

    **Resultado:** SIG/desarrollo/sig_papiit/entregables/susceptibilidad/fisica/elev_yuc/fv_elevacion_yuc_100m.tif

    **Nombre de la capa:** |fv_elevacion_yuc.tif|

    **issue** |Elevación|
    

Tipo de litoral
-----------------
*susceptibilidad - Física*
    
    **Peso local:** 0.07

    **Insumo**: ifv_tipo_litoral_yuc.tif

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
    Categoria Descripción  fv
    ========= =========== ====
    1         Arenoso     0.55
    2         Artificial  0.11
    3         Lodoso      1.00
    4         Vegetado    0.31
    ========= =========== ====
 
 

    **Resultado:** SIG/desarrollo/sig_papiit/entregables/susceptibilidad/fisica/t_litoral_yuc/fv_tipo_litoral_yuc_100m_corregida.tif

    **Nombre de la capa:** |fv_tipo_litoral_yuc.tif|

    **issue** |Tipo de litoral|




.. Ligas 
.. #Vegetación acuática

.. |ifv_v_acuatica_yuc.tif| raw:: html
    
    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/188ed4da-d849-4c40-b902-f0751cdcdc96" target="_blank">ifv_v_acuatica_yuc.tif</a>

.. |fv_v_acuatica_yuc.tif| raw:: html
    
    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/ead203a1-f80a-44e6-8828-c6361438fda7" target="_blank">fv_v_acuatica_yuc.tif</a>

.. |Vegetación acuática|  raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/64" target="_blank">Vegetación acuática</a>


.. #Vegetación costera

.. |fv_v_costera_presencia_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/8521cca4-497f-499a-8425-7c563fc59e02" target="_blank">fv_v_costera_presencia_yuc.tif</a>

.. |Vegetación costera|  raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/65" target="_blank">Vegetación costera</a>

.. #Ancho de playa

.. |ifv_ancho_playa_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/5e4501b7-a425-4f56-a3d0-1c9bd31319a0" target="_blank">ifv_ancho_playa_yuc.tif</a>

.. |fv_ancho_playa_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/8fd8fde8-4801-4752-b847-d1d032c92c43" target="_blank">fv_ancho_playa_yuc.tif</a>

.. |Ancho de playa| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/67" target="_blank">Ancho de playa</a>

.. #Dunas costeras

.. |ifv_duna_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/b0f9c6b1-bc93-4e4b-8bfc-1f606c65898d" target="_blank">ifv_duna_yuc.tif</a>
.. |fv_duna_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/bfbb9b86-75d3-40eb-bf50-afc06bad84fc" target="_blank">fv_duna_yuc.tif</a>

.. |Duna costera| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/62" target="_blank">Duna costera</a>

.. #Elevacion

.. |ifv_elev_yuc_v2.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/a065c6db-6faf-4840-a188-852808452ad0" target="_blank">ifv_elev_yuc_v2.tif</a>

.. |fv_elevacion_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/e386162b-58dd-49d8-a17a-62d43a5b5f5c" target="_blank">fv_elevacion_yuc.tif</a>

.. |Elevación| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/59" target="_blank">Elevación</a>


.. #Tipo de litoral

.. |ifv_tipo_litoral_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/ea4792db-93a8-4ea1-9ba3-75a1aefdb8b2" target="_blank">ifv_tipo_litoral_yuc.tif</a>
.. |fv_tipo_litoral_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/0d70eb64-f225-4e0c-af9a-e630934f84ec" target="_blank">fv_tipo_litoral_yuc.tif</a>
.. |Tipo de litoral| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/54" target="_blank">Tipo de litoral</a>