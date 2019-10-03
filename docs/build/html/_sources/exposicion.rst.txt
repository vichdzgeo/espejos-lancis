Criterio de exposición
##########################



.. imagen:: ../recursos/vulnerabilidad_exposicion_fv.png


Insumos
*********

Biológica
===========

Vegetación acuatíca
-------------------------
    *Exposición - biológica*
 
    Criterio: vegetacion acuatica 

    **Peso local**:0.16

    **insumo:** |ifv_v_acuatica_yuc.tif|
    
    **Definición:** Distancia entre los pastos y la línea de costa 

    ``mínimo: 0.0
    máximo:3000``

    **tipo de función:**  Continua - Logística

    
    .. note::
        Esta capa fue procesada en grass 7 ya que no se pudo procesar en la 
        plataforma  
    
    
    archivo json: fv_exp_bio_v_acuatica.json

    ``centro:1500,
    min:0,
    max:3000,
    saturacion: 3,
    k:0.0834999999999999``

    .. image:: ../recursos/fv/fv_c_exp_veg_acuatica.png


    **Resultado:** SIG/desarrollo/sig_papiit/entregables/exposicion/biologica/v_acuatica_yuc/fv_v_acuatica_yuc.tif

    **Nombre de la capa:** |fv_v_acuatica_yuc|

    **issue:** |vegetacion_acuatica|


    
Vegetación costera
---------------------
    *Exposición - Biológica*

    Criterio : Vegetación costera

    **Definición**: Tipo de vegetación que se encuentra en la franja de 3 kilometros (manglar, dunas) 

    **peso local:** 0.84

    **insumo:** |fv_v_costera_yuc.tif|
    
    Esta capa representa la integración de las capas de distancia de dunas costeras con la capa de distancias de manglar
    la construcción es 
    
    ``fv_v_costera_yuc = fv_distancia_dunas.tif*0.25 + fv_ditancia_manglar.tif*0.75``
 
    
Insumos
^^^^^^^^
    **Dunas costeras**
    
    *Exposición - biológica - Vegetación costera*

        **peso**: 0.25 
        
        **insumo:** fv_distancia_dunas.tif

        **Definición:** Lejanía a una duna costera dentro de la franja de 3 kms

        ``mínimo: 0.0  máximo:3000``

        Función continua - logística 
        
        insumo: ifv_distancia_dunas.tif
        
        archivo json: fv_exp_bio_veg_dunas.json
    
        ``centro:100
        min:0
        max:3000
        saturación:10
        k:0.255``

        .. image:: ../recursos/fv/fv_c_exp_dunas_costeras.png



    **Manglar** 
    
    *Exposición - Biológica - Vegetación costera*
        
        **peso local:** 0.75

        insumo: fv_ditancia_manglar.tif
        
        **Definición:** Lejanía a una zona de manglar dentro de la franja de 3kms

        ``mínimo: 0.00 máximo:1.00``

        **Tipo de función:** Continua - logística 
        
        archivo json: fv_exp_bio_veg_manglar.json
    
        ``centro:250
        min:0
        max:3000
        saturación:4
        k:0.108``

        .. imagen:: ../recursos/fv/fv_c_exp_manglar.png




**Resultado**: SIG/desarrollo/sig_papiit/entregables/exposicion/biologica/v_costera_yuc/fv_v_costera_distancia_yuc.tif


**Nombre de la capa:** fv_v_costera_distancia_yuc

**issue**: |vegetacion_costera|



Física
========

Ancho de playa
----------------
*Exposición - Física*

    **peso local:** 0.13

    **insumo:** ifv_distancia_playa.tif

    **Definición:** Distancia entre la línea de mar y el final de la playa
    
    .. Note::
        verificar esta Definición
    
   
    ``mínimo: 0.00
    máximo:3000.00``

    **Tipo de función: ** Continua - logística
        
    archivo json: fv_exp_fis_playa.json

    ``centro:60,
    min:0, 
    max:3000,
    saturación:7,
    k:0.1815``

    .. image:: ../recursos/fv/fv_c_exp_aplaya.png

**Resultado**: SIG/desarrollo/sig_papiit/entregables/exposicion/biologica/v_costera_yuc/fv__distancia_playa.tif


**Nombre de la capa:** |fv_distancia_playa|

**issue**: |Ancho_de_playa|


Elevación
----------
*Exposición - Física*

    **peso local:** 0.87

    **insumo:** ifv_elev_yuc.tif

    **Definición:** Localización sobre el nivel medio del mar

    **Tipo de función:** Continua - Concava decreciente


    arhivo json: fv_exp_fis_elevacion.json


    ``min: 0
    max: 31
    gama: 0.049249999999999995
    saturacion: 3``


    .. image:: ../recursos/fv/fv_c_exp_elevacion.png

**Resultado**: SIG/desarrollo/sig_papiit/entregables/exposicion/fisica/elev_yuc/fv_elevacion.tif


**Nombre de la capa:** |fv_elevacion|

**issue**: |Elevación|


.. ####liga de los metadatos#####
.. parte Biológica 

.. |ifv_v_costera_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/3970a9d9-e5fc-4522-ab83-fabefed5633b" target="_blank">ifv_v_costera_yuc.tif</a>

.. |ifv_v_acuatica_yuc.tif| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/4a300c5b-af8e-47d5-ad48-3b15a3e541bf" target="_blank">ifv_v_acuatica_yuc.tif</a>





.. parte física

.. |e_fv_ancho_playa_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/ac5e34c8-1c3c-4bfb-a4ab-9be7885f9db6" target="_blank">e_fv_ancho_playa_yuc</a>

.. |fv_e_elev_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/b794113f-dc2a-4ce0-b700-6d65263c9df4" target="_blank">fv_e_elev_yuc</a>


.. ####liga de los issues#####
.. biologica

.. |vegetacion_costera| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/66" target="_blank">Vegetación costera</a>
.. |vegetacion_acuatica| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/47" target="_blank">Vegetación acuatica</a>

.. fisica

.. |elevacion| raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/58" target="_blank">elevacion</a>

.. |duna_costera| raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/60" target="_blank">duna costera</a>
    
.. |ancho_de_playa| raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/69" target="_blank">ancho de playa</a>