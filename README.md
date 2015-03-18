# teleprenda
Mostra dun sistema loxístico para o sector textil.
Consiste nun traballo para a asignatura de Sectores de Negocio impartida na Facultade de Informática, na UDC.

O proxecto esta dividido en tres partes, cada unha das partes ten asociado unha Base de Datos distinta:
* Materias primas
* Ropa
* Transporte.

## Grupo de Transporte
Esta Base de Datos encargase de almacenar os datos relativos aos transportes tanto de materias primas como de roupas da empresa.

A continuación mostranse as caracteristicas e restriccións implementadas no sistema:

#### Resumo

Un transporte representa un viaxe do punto Orixe ao Destino, neste <strong>Transporte</strong> hai un <strong>Conductor</strong> implicado, que leva unha <strong>Materia Prima</strong> ou un lote de <strong>Roupa</strong>, identificadas por un identificador de pedido (idPedido).

#### Tipos de percorridos

- Materia prima do proveedor ao almacén de materias primas
- Materia prima do almacén de materias primas á fábrica (para a fabricación de roupa)
- Roupa da fábrica ao almacén de roupa
- Roupa do almacén de roupa á fábrica de roupa (no caso de que sexa defectuosa)
- Roupa do almacén de roupa ao cliente que encargou o pedido

#### Base de Datos

Para modelar esta situación un tanto idealizada, creouse o segunte modelo de bd:
![ScreenShot](https://raw.githubusercontent.com/mcgalvan/teleprenda/master/Aplicacion/Transporte/BDTransporte.png)

* Conductor modela os datos dun conductor que traballa para a empresa.
* Vehiculo contén os datos dun vehículo empregado para transportar mercancía.
* Transporte amosa información asociada aos diferentes transportes realizados pola empresa. O tipo de transporte é un atributo multivaluado, que pode tomar calquera dos [5 valores enumerados anteriormente](https://github.com/mcgalvan/teleprenda#tipos-de-percorridos), e os valores idFabrica e idMateriaPrima, están pensados para que se asignen en base á información asociada nas outras bases de datos.
* Albarán modela a información tanto de saida como de chegada do transporte dende o punto de orixe ao seu destino, permitindo así que as partes implicadas neste transporte certifiquen que o número de bultos transportados é correcto. 

Esta base de datos permite plasmar unha visión moi simplificada da empresa, e xerar informes de esta. Tamén se implementa unha sinxela interfaz gráfica para facer o seu uso mais accesible.


## Grupo de Materias primas
O módulo de almacenamento de materias primas rexistra información dos pedidos realizados polos diversos clientes, os proveedores que suministran as distintas materias primas a a fábrica de envío dos pedidos.

A continuación mostranse as caracteristicas e restriccións implementadas no sistema:

#### Resumo

Un cliente solicita un pedido (idPedido) que poderá necesitar para a súa elaboración diversas materias primas, suministradas por distintos proveedores. Cada materia prima da que consta o pedido será rexistrada como unha entrada distinta na base de datos.
Unha vez obtidos todos os recursos do pedido enviaranse á fábrica para a sua manufacturación e quedará almecenada a data saída á fábrica do pedido.

#### Base de Datos

Modelo Entidade-relación para as materias primas.
![ScreenShot](https://github.com/mcgalvan/teleprenda/blob/master/_lab/materias_primas.PNG)


* Cliente modela a información dos consumidores dos nosos servizos.
* Pedido identifica unívocamente un pedido realizado por un cliente rexistrado entre outros a data de salida do pedido así como o número de transporte de saída (un pedido só ten unha saída á fábrica) .
* Proveedor contén os datos dos suministradores das diversas materias.
* Materia representa as distintas materias primas rexistradas no sistema. O mesmo tipo de materia prima ofrecida por diversos proveedores constan como materias distintas.
* Materias_pedido, é a entidade encargada de rexistrar para un pedido determinado (idPedido) as distintas entradas (par materia pedido) das que consta, así como a data de entrada no almacén.
* Fábrica representa á fábrica á cal será enviado un pedido.



