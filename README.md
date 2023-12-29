# DISEÑO ESTRATÉGICO PARA UN E-COMMERCE
## Identificación de dominios:
### Ventas
Se encarga de gestionar los pedidos de los clientes, incluyendo la creación de pedidos, el procesamiento de pagos, el seguimiento de envíos y la gestión de devoluciones.
Tipo de dominio: El subdominio ventas es un Core Domain porque representa el proceso de adquisición de los productos por parte de los clientes. Este proceso es esencial para el negocio del E-Commerce, ya que es el que genera los ingresos a la organización.
### Pagos
Se encarga de gestionar las transacciones financieras asociadas a las compras realizadas por los clientes. Esto incluye la autorización de pagos, el procesamiento de transacciones, la facturación y la coordinación con servicios de terceros como intermediario de transacciones financieras y entidades financieras.
Tipo de dominio: El subdominio de pagos es un Core Domain, porque representa una parte fundamental del proceso de adquisición de productos. La correcta gestión de pagos asegura que la organización reciba los ingresos de manera efectiva y eficiente. Desempeña un papel crucial en el éxito y la rentabilidad del negocio de E-Commerce.
### Inventario
Se encarga de gestionar la información de los productos ofertados a los clientes, incluyendo descripciones de las características principales, imágenes, precios y disponibilidad para ser separado para la venta.
Tipo de dominio: El subdominio de Inventario es un Core Domain ya que permite garantizar que los productos estén disponibles para los clientes. Sin embargo, no es esencial para el funcionamiento del negocio; es decir, un negocio de comercio electrónico podría seguir funcionando incluso si el inventario no está actualizado de forma precisa.
### Promociones
Representa las promociones y descuentos ofrecidos a los clientes, esto incluye las reglas del negocio para las promociones y las reglas para aplicar los descuentos, así como realizar el seguimiento de la efectividad de las promociones.
Tipo de dominio: El subdominio Promociones es un Support Domain, ya que su función principal consiste en complementar el proceso de adquisición de productos, mejorando la experiencia del cliente y generando interés adicional. Aunque no es el núcleo central, desempeña un papel estratégico en el fortalecimiento de la relación entre el cliente y el negocio.

### Gestión de Usuarios
Se encarga de manejar la información de los clientes de la organización, incluyendo sus perfiles, direcciones de envío, información de la forma de pago y facturación, historial de pedidos y preferencias.
Tipo de Dominio:  El subdominio usuarios es un Generic Domain porque representa los conceptos y reglas de negocio relacionados con los usuarios de un sistema y podrían ser reutilizados en otros proyectos y adaptarse a las necesidades específicas de cada negocio.
## Patrones Utilizados
### Inventario y promociones
Patrón conformista
La relación entre los contextos inventario y promociones se basa en el patrón de diseño conformista porque el equipo upstream, Inventario, no tiene ninguna motivación para apoyar las necesidades específicas del equipo downstream, Promociones. El equipo downstream, promociones, necesita adaptarse al modelo de datos del equipo Inventario.
### Promociones y Usuario
Patrón cliente-proveedor:
Los contextos promociones y usuario usan el patrón de diseño cliente-proveedor porque el contexto promociones necesita utilizar la información proporcionada por el contexto usuario para aplicar las promociones de forma adecuada. El contexto usuario domina esta relación porque debe proporcionar la información que el contexto promociones necesita.
### Usuario y pagos
Patrón capa anticorrupción
El contexto de usuario y el de pagos trabajan juntos para garantizar transacciones seguras y eficientes en un sistema de comercio electrónico. El contexto de usuario proporciona la información de pago, mientras que el contexto de pagos procesa la información y completa la transacción. La capa anticorrupción protege la información de pago de la corrupción.
### Pago y ventas
Patrón capa anticorrupción
El contexto de ventas proporciona la información necesaria para completar la transacción, como los productos seleccionados, los precios, etc. El contexto de pagos recibe la información de la transacción del contexto de ventas y la procesa para completar la transacción. La capa anticorrupción protege la información de la transacción proporcionada por el contexto de ventas de la corrupción. La capa anticorrupción válida, encripta y procesa la información de la transacción de manera segura.
### Promociones y Pagos
Patrón capa anticorrupción
El contexto de ventas proporciona la información necesaria para completar la transacción, como los productos seleccionados, los precios, etc. El contexto de pagos recibe la información de la transacción del contexto de ventas y la procesa para completar la transacción. La capa anticorrupción protege la información de la transacción proporcionada por el contexto de ventas de la corrupción. La capa anticorrupción válida, encripta y procesa la información de la transacción de manera segura.
### Ventas e Inventarios
Patrón cliente-proveedor:
Los contextos de promociones y pagos en comercio electrónico siguen el patrón cliente-proveedor. El contexto de promociones, actuando como cliente, requiere datos del usuario para aplicar ofertas en pagos. Aquí, el contexto usuario domina, proporcionando la información clave. Esta dinámica asegura la aplicación precisa de promociones durante pagos, mejorando la experiencia del cliente y garantizando transacciones precisas en el sistema.
### Usuario y Ventas
Patrón capa anticorrupción
El contexto de usuario proporciona información sobre el usuario, como sus preferencias, historial e información de perfil. Esta información se utiliza para personalizar la experiencia de compra, mostrando productos relevantes, haciendo recomendaciones y ofreciendo ofertas personalizadas. La capa anticorrupción protege la información del usuario de la corrupción, asegurando su integridad y seguridad.