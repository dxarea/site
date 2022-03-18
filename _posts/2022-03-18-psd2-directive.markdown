---
layout: post
title:  Payment Services Directive
date:   2022-03-18 18:05:55 +0300
image:  '/images/20220318_psd2.jpg'
tags:   open_banking security payment_methods fintech
---
# Regimen PSD2

PSD2 es un marco regulatorio que trata de dinamizar los cambios que se están produciendo en los servicios de pago. Aunque las iniciativas en este tipo de servicios son constantes, es el negocio de los pagos minoristas en el que más se nota esta corriente gracias a las FinTech.

El acrónimo PSD2 corresponde a Payment Service Directive 2, directiva que define la normativa europea sobre pagos online. Aunque entró en vigor en 2018, y su aplicación estaba prevista para el 14 de septiembre de 2019, la ABE (Autoridad Bancaria Europea) aprobó una moratoria de 12 a 14 meses.

Así pues la moratoria finalizó el 31 de diciembre de 2020 y el 1 de enero de 2021 se empezaron a aplicar los cambios legislativos derivados de ésta.

La nueva directiva presenta dos grandes áreas:

* Seguridad. Mayor atención a los riesgos asociados a los procesos nacidos de la transformación digital
* Regulación de Servicios Adicionales
    * servicios de iniciación de pagos (Payment Initiation Service - PIS)
    * Servicios de agregación (Account Information Service - AIS)

En lo relativo a la seguridad se centra especialmente en las transacciones de carácter remoto, ya sea a través de internet o por medio de dispositivos móviles.

Su objetivo es proteger a consumidores, comercios online y entidades financieras del fraude mediante la aplicación de "autenticación reforzada de cliente" o SCA (Strong Customer Authentication). Un mecanismo que trata de asegurar la identidad del usuario durante las transacciones online.

![PSD2 environment]({{site.baseurl}}/images/psd2-schema.png)

[comment]: <> (*PSD2 environment*)

## Seguridad

### Autenticación Reforzada de Cliente

Según la Directiva de Servicios de Pago Revisada la autenticación reforzada se lleva a cabo cuando se utilizan al menos dos de los siguientes elementos para la autenticación del consumidor:

* Conocimiento. Algo que solo el consumidor sabe: contraseña, código PIN, datos de acceso
* Posesión. Algo que solo el consumidor tiene: móvil al que se envía un SMS para verificar la operación, dirección de correo electrónico, etc.
* Inherencia. Algo que el consumidor es: identificación biométrica, dactilar, facial, etc.

Aunque no es infalible, se basa en la idea de que estos elementos son independiente entre sí, de forma que la vulneración de uno no compromete la fiabilidad de los demás, lo que en último término hace mucho máa difícil suplantar la identidad. Basándose en esta idea, PSD2 requiere la presencia obligatoria de dos de los factores en servicios de pago online.

### Aplicación

Aunque la autenticación reforzada es obligatoria para las tiendas online, no todos los métodos de pago están afectados de la misma forma por la directiva:

* Domiciliación bancaria. No necesita autenticación reforzada
    * Transferencia inmediata. Al estar basados en un sistema bancario online que emite un Número de Autenticación de Transacción (TAN) a un segundo dispositivo, como un smartphone, dispone de facto de autenticación reforzada
* Paypal. Con paypal pueden hacerse pagos de crédito o de débito. Solo los primeros necesitan autenticación reforzada.
* Tarjeta de crédito. Debe aplicarse autenticación reforzada

Los proveedores de servicios de pago (PSP), serán los responsables de garantizar el cumplimiento de la normativa. De forma que si alguien se hace pasar por un cliente para realizar una compra en una tienda online, el pago es aceptado y no hay una autenticación reforzada establecida para este método de pago, el banco le reembolsará a la persona a la que le han robado los datos, los importes indebidamente debitados, y le exigirá al comercio o a su proveedor de servicios de pago el reembolso de estos importes.

## Servicios adicionales

PSD2 ha incluido la regulación de determinados servicios que habían quedado fuera en la anterior normativa. En concreto, los servicios prestados por entidades especializadas (Third Party Providers - TPP) sobre las cuentas de los clientes en otras entidades, iniciación de pagos en cuentas de otras entidades así como el ofrecimiento de información sobre saldos y operaciones de cuentas en otras entidades.

La característica de este tipo de servicios es que la entidad prestadora no requiere administrar las cuentas accedidas, sino que es suficiente el consentimiento del cliente para operar u obtener información de ellas.

Hasta la entrada en vigor de esta regulación existía un problema en el modo en que los TPP accedían a las cuentas de pago de sus clientes, ya que utilizaban las credenciales de seguridad personalizadas de éstos. De forma que accedían a las cuentas del mismo modo y con los mismos permisos que el propio titular, y se utilizaban técnicas de Screen Scraping.

Esta operativa tenía implicaciones en términos de seguridad y eficiencia, ya que los TPP, que no tenían ningún tipo de vinculación con la entidad gestora, podían acceder a la información de sus clientes por medio de un canal pensado para estos últimos. Potencialmente tenían acceso a más información de la necesaria para prestar servicio a sus clientes, ya que las entidades gestoras ofrecían un único canal con acceso a todas las cuentas, productos y posiciones.

PSD2 mediante la regulación de los servicios de agregación e iniciación de pagos, trata de ofrecer soluciones de utilidad a comerciantes y consumidores, como canales de pago alternativos no vinculados a las tarjetas de pago.

## Excepciones a la norma

* Los usuarios pueden crear "listas blancas" en el online banking con destinatarios de pago de confianza y de esta manera no se les requerirá a estos usuarios la autenticación reforzada.

* Los usuarios que hayan realizado una compra a través del móvil y, los datos de la tarjeta se hayan guardado en él, estarán exentos de la SCA.

* Para los pagos o transacciones inferiores a 30 euros no se necesitará la autenticación reforzada, siempre que no sean más de 5 veces al día o llegue a los 100 euros en 24 horas

## Glosario

* PSD2: Payment Service Directive 2
* PIS: Payment Initiation Service
* AIS: Account Information Service
* TPP: Third Party Providers
* RTS: Regulatory Technical Standards
* SCA: Strong Customer Authentication
* PSP: Payment Service Provider
* ASPSP: Account Servicing Payment Service Provider
* AISP: Account Information Service Provider
* PISP: Payment Initiation Service Providers
* ABE: Autoridad Bancaria Europea

## Fuentes

* [Trusted Shops](https://business.trustedshops.es/blog/psd2-nueva-normativa-pagos-online/)
* [Un nuevo regimen de acceso a las cuentas de pago la PSD2](https://www.bde.es/f/webbde/GAP/Secciones/Publicaciones/InformesBoletinesRevistas/RevistaEstabilidadFinanciera/18/NOVIEMBRE/Un_nuevo_regimen_de_acceso_a_las_cuentas_de_pago_la_PSD2.pdf)
  