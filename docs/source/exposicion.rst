Criterio de exposición
##########################



Insumos
*********

Biológica
===========

Vegetación acuatíca
-------------------------
    *Exposición - biológica*

    Criterio: vegetacion acuatica 

    **peso**:0.16

    
    Esta capa representa la distancia a la que se encuentran los pastos marinos dentro de la costa, la distancia 
    va de 0 a 3000 metros. esta capa es procesada con una función de valor logística, quedando sus valores
    de 0 a 1.

    nombre del archivo: fv_v_acuatica_yuc.tif

    ``mínimo: 0.0
    máximo:1.00``

    función continua - Logística invertida

    insumo: ifv_v_acuatica.tif

    .. note::
        Esta capa fue procesada en grass 7
    
    
    archivo json: fv_exp_bio_v_acuatica.jsonn

    ``centro:1500,
    min:0,
    max:3000,
    saturacion: 3,
    k:0.0834999999999999``

    .. imagen:: ../recursos/fi_fv_exp_bio_v_acuatica.JPG



    **Metadatos**: |e_fv_v_acuatica_yuc|

    **Ruta**: SIG/desarrollo/sig_papiit/entregables/exposicion/biologica/v_acuatica_yuc/fv_v_acuatica_yuc.tif

    **issue**: |vegetacion_acuatica|

    
Vegetación costera
---------------------
    *Exposición - Biológica*

    Criterio : Vegetación costera

    **peso**: 0.84
    
    Esta capa representa la integración de las capas de distancia de dunas costeras con la capa de distancias de manglar
    la construcción es 
    
    ``vegetacion costera = fv_distancia_dunas.tif*0.25 + fv_ditancia_manglar.tif*0.75``

    nombre del archivo = fv_v_costera.tif

    ``mínimo: 0.02
    máximo:1.00``
    
    **Nombre de la capa**: fv_v_costera_yuc


    **Metadatos**: |e_fv_v_costera_yuc|
    
    **Ruta**: SIG/desarrollo/sig_papiit/entregables/exposicion/biologica/v_costera_yuc/fv_v_costera.tif

    **issue**: |vegetacion_costera|

Dunas costeras
^^^^^^^^^^^^^^
*Exposición - biológica*

    Criterio: Vegetación costera
    
    **peso**: 0.25 
    
    nombre del archivo: fv_distancia_dunas.tif
    
    Esta capa representa la lejanía a una duna costera, el rango  va de 0 ,lo  que representa especialmente estar situado en la duna,
    hasta 1.0, que representa estar lo más lejano a una duna. la cercanía a la duna esta representada por una función de valor logística
    
    ``mínimo: 0.00
    máximo:1.00``

    Función continua - logística 
    
    insumo: ifv_distancia_dunas.tif
    
    archivo json: fv_exp_bio_veg_dunas.json
   
    ``centro:100
    min:0
    max:3000
    saturación:10
    k:0.255``

    .. imagen:: ../recursos/fi_fv_exp_bio_duna.JPG

    issue:

    metadatos:

Manglar 
^^^^^^^^
*Exposición - Biológica*

    Criterio: Vegetacion costera
    
    **peso**: (0.75)
    nombre del archivo: fv_ditancia_manglar.tif
    
    Esta capa representa la lejanía a una zona delimitada como manglar, el rango  va de 0 ,lo  que representa especialmente estar situado en el manglar, 
    hasta 1.0, que representa estar lo más lejano a una zona de manglar. la lejanía al manglar esta representada por una función de valor logística

    ``mínimo: 0.00
    máximo:1.00``

    Función continua - logística 
    
    insumo: ifv_distancia_manglar.tif
    
    archivo json: fv_exp_bio_veg_manglar.json
   
    ``centro:250
    min:0
    max:3000
    saturación:4
    k:0.108``

    .. imagen:: ../recursos/fi_fv_exp_bio_manglar.JPG

    issue:

    metadatos:


Física
========

Ancho de playa
----------------
*Exposición - Física*

    Criterio: Ancho de playa

    **peso** : **actualizar**

    Nombre del archivo: fv_distancia_playa.tif

    Esta capa representa la lejania a la playa, el rango va de 0, lo que representa espacialmente estar situado en la playa, 
    hasta 1, que representa espacialmente estar lo más alejado de la playa.

    ``mínimo: 0.00
    máximo:1.00``

    Función continua - logística 
    
    insumo: ifv_distancia_playa.tif
    
    archivo json: fv_exp_fis_playa.json

    ``centro:60,
    min:0,
    max:3000,
    saturación:7,
    k:0.1815``

    .. imagen:: ../recursos/fi_fv_exp_fis_distancia_playa.JPG

    **metadatos**: |e_fv_ancho_playa_yuc|

    **Ruta**: SIG/desarrollo/sig_papiit/entregables/exposicion/fisica/ancho_playa_yuc/fv_ancho_playa_yuc.tif

    **issue**: |ancho_de_playa|


Elevación
----------
*Exposición - Física*

    Criterio: elevacion

    **peso**: **verificar**

    nombre del archivo: fv_elev_yuc.tif

    El insumo para la generación de esta capa proviene del Continuo de Elevaciones Mexicano (CEM) de INEGI,
    a la cual se le aplico una funcion de valor *concava decreciente* 

    Funcion continua - Concava decreciente

    arhivo json: fv_exp_fis_elevacion.json

    ``min: 0
    max: 31
    gama: 0.049249999999999995
    saturacion: 3``


    .. imagen:: ../recursos/fi_fv_exp_fis_elevacion.JPG


    **Nombre de la capa**: fv_elev_yuc.tif

    **metadatos**: |fv_e_elev_yuc|

    **Ruta**: SIG/desarrollo/sig_papiit/entregables/exposicion/fisica/elev_yuc/fv_elev_yuc.tif

    **issue**: |elevacion|


.. liga de los metadatos
.. parte Biológica 

.. |e_fv_v_costera_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/3970a9d9-e5fc-4522-ab83-fabefed5633b" target="_blank">e_fv_v_costera_yuc</a>

.. |e_fv_v_acuatica_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/4a300c5b-af8e-47d5-ad48-3b15a3e541bf" target="_blank">e_fv_v_acuatica_yuc</a>





.. parte física

.. |e_fv_ancho_playa_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/ac5e34c8-1c3c-4bfb-a4ab-9be7885f9db6" target="_blank">e_fv_ancho_playa_yuc</a>

.. |e_fv_duna_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/e4801fba-766d-48ea-bbc5-dd78203d7ffa" target="_blank"e_fv_duna_yuc</a>

.. |e_fv_tipo_litoral_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/93fb03d9-dda9-4cb1-b6c6-fb97db32429b" target="_blank">e_fv_tipo_litoral_yuc</a>

.. |fv_e_elev_yuc| raw:: html

    <a href= "http://magrat.mine.nu:8088/geonetwork/srv/spa/catalog.search#/metadata/b794113f-dc2a-4ce0-b700-6d65263c9df4" target="_blank">fv_e_elev_yuc</a>


.. liga de los issues
.. biologica

.. |vegetacion_costera| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/66" target="_blank">Vegetación costera</a>
.. |vegetacion_acuatica| raw:: html

    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/47" target="_blank">Vegetación acuatica</a>

.. fisica

.. |elevacion| raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/58" target="_blank">elevacion</a>

.. |tipo_litoral| raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/54" target="_blank">tipo de litoral</a>

.. |duna_costera| raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/60" target="_blank">duna costera</a>
    
.. |ancho_de_playa| raw:: html
    
    <a href= "https://github.com/lancis-apc/espejos-lancis/issues/69" target="_blank">ancho de playa</a>