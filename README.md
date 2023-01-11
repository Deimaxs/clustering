<!-- PROJECT LOGO -->
<br />

<p align="center">


  <h3 align="center">Anomaly detection clustering</h3>

  <p align="center">
    control of anomalies in ITV tests
    <br />
    <br />
</p>



## Introducción

El proyecto consiste en realizar la limpieza, procesamiento y análisis de un conjunto de datos producto de controles medio ambientales aleatorios a vehículos de combustión interna en carreteras y autopistas, con el fin de corroborar los resultados obtenidos en la Inspección Técnica de Vehículos (ITV - En España) o Revisión técnico-mecánica (En Latinoamérica) y poder determinar conductas fraudulentas por parte de las empresas que certifican dichos procesos.


* Resultados:

![Image base](image1.JPG?raw=true)

Este script hace uso de librerías y frameworks tales como scikit-learn, pandas, seaborn, entre otras.


## Descipción

El dataset se compone de los registros de los vehículos aleatorios sometidos a un análisis de gases de escape, cuyos features son:

- Fecha_prueba: Fecha en la que se realizó la medición.
- Matricula: Número/Placa/Patente/Matrícula del vehículo.
- Temp_Amb: Temperatura ambiente del lugar donde se realizó la prueba.
- Humr_Amb: Humedad relativa ambiente del lugar donde se realizó la prueba.
- Marca: Nombre del fabricante del vehículo.
- Modelo: El año civil de la fabricación del vehículo o el año modelo del vehículo según lo defina el fabricante.
- Cilindraje: Cantidad de mezcla que puede admitir el motor, expresado en centímetros cúbicos (CC).
- Combustible: Matería usada para la generación de energía motriz (GNV-Gas Natural Vehicular, Gasolina e Híbridos-GNV_gasolina). 
- Kilometraje: Distancia recorrida por el vehículo en kilómetros (km).
- Fecha_ITV: Fecha en la que el vehículo certificó la prueba técnica.
- CDA: Centro de diagnóstico automotriz encargado de certificar la prueba técnica.
- Temp_motor: Temperatura del motor durante la prueba.
- RPM_motor: Revoluciones por minuto del motor durante la prueba.
- HC: Hidrocarburos presentes en los gases de escape en ralentí, expresado en partes por millón (ppm).
- CO: Monóxido de carbono presente en los gases de escape en ralentí, expresado en porcentaje volumétrico (%v)
- CO2: Dióxido de carbono presente en los gases de escape en ralentí, expresado en porcentaje volumétrico (%v)
- O2: Oxigeno presente en los gases de escape en ralentí, expresado en porcentaje volumétrico (%v)
- RPM_Cru: Revoluciones por minuto del motor durante la etapa de aceleración de la prueba.
- HC_Cru: Hidrocarburos presentes en los gases de escape con el vehículo acelerado aproximadamente a 2.500 RPM, expresado en partes por millón (ppm).
- CO_Cru: Monóxido de carbono presente en los gases de escape con el vehículo acelerado aproximadamente a 2.500 RPM, expresado en porcentaje volumetrico (%v).
- CO2_Cru: Dióxido de carbono presente en los gases de escape con el vehículo acelerado aproximadamente a 2.500 RPM, expresado en porcentaje volumetrico (%v).
- O2_Cru: Oxígeno presente en los gases de escape con el vehículo acelerado aproximadamente a 2.500 RPM, expresado en porcentaje volumetrico (%v).


## Observaciones

Los registros procedentes de datos sensibles como Matrícula, Marca, CDA, etc. fueron generados de manera aleatoria por un script de python y NO tienen ninguna relación con vehículos o empresas reales.
  
  * Scripts generadores de datos:
  ```python
  def gen_plate():
  plate=rand_num()
  plate=plate+rand_num()+rand_num()+rand_num()+' '+rand_let()+rand_let()+rand_let()
  return plate

  def rand_let():
      return random.choice(string.ascii_letters).upper()

  def rand_num():
      return str(random.randint(0,9))

  def choise(column):
      lista = []
      for _ in column.index:
          plate = gen_plate()
          if plate not in lista:
              column[_]=plate
              lista.append(plate)
          else:
              choise(column)
```

<!-- LICENSE -->
## License

  Distributed under the MIT License. See `LICENSE` for more information.

<!-- CONTACT -->
## Contact

Email: mateo.sanchezalzate@gmail.com

Portfolio: 
[Página Web](https://deimaxs.github.io/ "Página Web")

LinkedIn: 
[Mateo Sánchez](https://www.linkedin.com/in/mateo-sanchez-ds/ "Mateo Sánchez")