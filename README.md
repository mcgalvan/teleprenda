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