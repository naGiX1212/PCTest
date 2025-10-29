![logo](./img/logo.jpeg)

# PC

Joel Murillo
Año 2025

## Tabla de indices
- [Ejercicio 1](#ejercicio-1)
- [Ejercicio 2](#ejercicio-2)
- [Ejercicio 3](#ejercicio-3)
- [Ejercicio 4](#ejercicio-4)
- [Ejercicio 5](#ejercicio-5)
- [Ejercicio 6](#ejercicio-6)

---

## EJERCICIO 1

### VSCODE
![vscode](./img/vscode.png)

### GIT BASH

![git](./gif/gitbash.gif)
---

## EJERCICIO 2


### RESPUESTAS
1. Es un servidor que utiliza el protocolo HTTP para el manejo de solicitudes.
2. Son comandos o tipos de solicitudes que un cliente o usuario le puede hacer a un servidor HTTP.
   GET : Obtener informacion
   POST : Insertar informacion
   DELETE : Eliminar informacion
   PUT : Modificar o Remplazar informacion
4. Un request es una solicitud que un cliente le realiza al servidor , un response es la respuesta que devuelve el servidor a la request que le mando el cliente.
5. Los headers son informacion adicional que se envia al ocurrir un response o request , por ejemplo una fecha y hora de la solicitud , o el formato de texto utilizado.
6. ¿Qué es un queryString? (En el contexto de una url)
7. Es un codigo que me dice si ocurrio un fallo o la solicitud fue manejada de forma correcta por el servidor , tenemos por ejemplo :
   200 OK
   300 REDIRECCION
   400 ERROR SERVIDOR
   500 ERROR CLIENTE
8. La data para un GET se envia desde la URL , como por ejemplo localhost/Cliente?id=123. Mientras que los datos para realizar un POST se envian a traves de body , por ejemplo un JSON.
9. El verbo que utiliza el navegador cuando accedemos a una pagina es GET
10.XML un lenguaje de marcado que usa etiquetas para estructurar y describir datos.
  ```xml
   <usuario>
     <nombre>Joel</nombre>
     <estado>online</estado>
   </usuario>
  ```
   JSON es un formato de texto ligero para representar datos estructurados, fácil de leer y procesar por humanos y máquinas.
  ```json
   {
     "nombre": "Joel",
     "estado": "online"
   }
  ```
12. es un protocolo de comunicación que utiliza mensajes en formato XML para intercambiar información entre aplicaciones a través de la red. Define una estructura estricta y suele usarse en entornos empresariales donde se requiere seguridad y confiabilidad.
13. es un estilo de arquitectura que usa los métodos estándar de HTTP (GET, POST, PUT, DELETE) para acceder y manipular recursos a través de URLs. Es más liviano que SOAP y generalmente utiliza el formato JSON para enviar y recibir datos.
14. Los headers son parte de una solicitud HTTP y contienen información adicional o metadatos sobre la petición, como la autenticación, el tipo de contenido o la longitud de los datos enviados.
El header Content-Type se utiliza para indicar el formato del contenido que se envía en el cuerpo del request, por ejemplo application/json si los datos están en formato JSON o application/xml si están en XML.
---

## EJERCICIO 3

1. Realizar un request GET a la URL:
![getBefore](./img/getPostmanBefore.png)

2. Realizar un request POST a la URL anterior, y con body:

![post](./img/postPostman.png)

3. Realizar nuevamente un request GET a la URL:

![getAfter](./img/getPostmanAfter.png)

¿Qué diferencias se observan entre las llamadas el punto 1 y 3?
En el paso 3 aparece un nombre que no estaba presente en el paso 1 , esto es debido al POST que realice con mis datos en el paso 2.

---
## EJERCICIO 4
[![salesForce](https://img.shields.io/badge/Salesforce-00A1E0.svg?style=for-the-badge&logo=Salesforce&logoColor=white)](https://www.salesforce.com/trailblazer/ytp32goxlbrkzkzx8h)

---
## EJERCICIO 5

### 1. Lead
**Concepto:** Representa un prospecto o posible cliente.  
**Datos estándar:** Nombre, empresa, email, teléfono, fuente de origen, estado.  
**Relaciones:**  
-No se relaciona con ninguno de los Objects presentados.

---

### 2. Account
**Concepto:** Empresa o cliente con el que la organización mantiene una relación.  
**Datos estándar:** Nombre, tipo (cliente, partner, proveedor), industria, dirección.  
**Relaciones:**  
- 1 `Account` → N️ `Contact`
- 1 `Account` → N️ `Opportunity`
- 1 `Account` → N️ `Case`
- 1 `Account` → N️ `Asset`
- 1 `Account` → N️ `Account`
  
---

### 3. Contact
**Concepto:** Persona asociada a una cuenta (cliente o socio).  
**Datos estándar:** Nombre, cargo, email, teléfono, dirección.  
**Relaciones:**  
- N `Contact` → 1 `Account`
- 1 `Contact` → N `Case`
- 1 `Contact` → N `Asset`
- 1 `Contact` → N `Contact`


---

### 4. Opportunity
**Concepto:** Representa una oportunidad de venta.  
**Datos estándar:** Nombre, etapa, monto, fecha de cierre, probabilidad.  
**Relaciones:**  
- 1 `Opportunity` → N `Quote`
- N `Opportunity` → 1 `Price Book`
- 1 `Opportunity` → N `Asset`

---

### 5. Product
**Concepto:** Producto o servicio ofrecido por la empresa.  
**Datos estándar:** Nombre, código, familia, descripción, precio base.  
**Relaciones:**  
- 1 `Product` → N `Case`
- N️ `Product` → 1 `Product`
- 1 `Product` → N `Asset`


---

### 6. Price Book
**Concepto:** Lista de precios de los productos.  
**Datos estándar:** Nombre, estado (activo/inactivo).  
**Relaciones:**  
- 1 `Price Book` → N️ `Opportunity`
---

### 7. Quote
**Concepto:** Cotización o presupuesto ofrecido al cliente.  
**Datos estándar:** Nombre, fecha, monto total, estado, descripción.  
**Relaciones:**  
- N️ `Quote` → 1 `Opportunity`

---

### 8. Asset
**Concepto:** Producto físico o servicio vendido/instalado para un cliente.  
**Datos estándar:** Nombre, número de serie, producto, estado, fecha de compra.  
**Relaciones:**  
- N️ `Asset` → 1 `Account`
- N️ `Asset` → 1 `Contact`
- N️ `Asset` → 1 `Product`
- N️ `Asset` → 1 `Asset`
- 1 `Asset` → N `Case`

---

### 9. Case
**Concepto:** Representa una incidencia o solicitud de soporte.  
**Datos estándar:** Número de caso, asunto, descripción, estado, prioridad.  
**Relaciones:**  
- N️ `Case` → 1 `Account`
- N️ `Case` → 1 `Contact`
- N️ `Case` → 1 `Product`
- N️ `Case` → 1 `Case`
- N️ `Case` → 1 `Asset`
---

### 10. Article (Knowledge)
**Concepto:** Documento de conocimiento o solución a un problema.  
**Datos estándar:** Título, contenido, categoría, estado.  
**Relaciones:**  
-No se relaciona de forma directa con ninguna del las 9 restantes.

---
![relaciones](./img/relaciones.png)

---


## EJERCICIO 6
Responder las siguientes preguntas brevemente sobre: Soluciones de Salesforce
A. Salesforce es un CRM que corre en la nube.
B. ¿Qué es Sales Cloud?
C. ¿Qué es Service Cloud?
D. ¿Qué es Health Cloud?
E. ¿Qué es Marketing Cloud?

Funcionalidades de Salesforce
A. ¿Qué es un RecordType?
B. ¿Qué es un ReportType?
C. ¿Qué es un Page Layout?
D. ¿Qué es un Compact Layout?
E. ¿Qué es un Perfil?
F. ¿Qué es un Rol?
G. ¿Qué es un Validation Rule?
H. ¿Qué diferencia hay entre una relación Master Detail y Lookup?
I. ¿Qué es un Sandbox?
J. ¿Qué es un ChangeSet?
K. ¿Para qué sirve el import Wizard de Salesforce?
L. ¿Para qué sirve la funcionalidad Web to Lead?
M. ¿Para qué sirve la funcionalidad Web to Case?
N. ¿Para qué sirve la funcionalidad Omnichannel?
O. ¿Para qué sirve la funcionalidad Chatter?



Conceptos generales
A. Software as a Plataform
B. Si Salesforce es SaaS
C. Que corre en la nube , por ende el cliente no debera gastar en hardware.
D. ¿Qué significa que una solución sea On-Premise?
E. ¿Qué es un pipeline de ventas?
F. ¿Qué es un funnel de ventas?
G. ¿Qué significa Customer Experience?
H. ¿Qué significa omnicanalidad?
I. ¿Qué significa que un negocio sea B2B?¿Qué significa que un negocio sea
B2C?¿Qué es un KPI?
J. ¿Qué es una API y en qué se diferencia de una Rest API?
K. ¿Qué es un Proceso Batch?
L. ¿Qué es Kanban?
M. ¿Qué es un ERP?
N. ¿Salesforce es un ERP?

