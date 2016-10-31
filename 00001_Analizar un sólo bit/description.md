### El desafío


Se necesita implementar una rutina ```divSiEsPar``` que divide por 2 el valor del registro R1 si este es par. Para esto se necesita analizar la estructura de la cadena, en particular el bit menos significativo. Si este es 0 entonces el número representado por esta cadena es par, y es impar en caso contrario.

¿Cómo miramos un sólo bit?

¡Usamos una máscara!

Para testear el valor de un determinado bit, debemos aplicar una **máscara**, que es una nueva cadena con partes fijas y partes variables (que vienen a ser como huecos en la máscara). 

Esa máscara se aplica sobre la cadena que queremos analizar **mediante una operación lógica** (en general AND, OR, XOR), consiguiendo una cadena resultante de caracterìsticas fàcilmente *medibles*, es decir: **que pueda compararse por igualdad con una constante**. 

### Nuevas instrucciones

Para esto es necesario incorporar a nuestra arquitectura, 3 operaciones lógicas que funcionan a nivel de bit:


<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;}
.tg .tg-7geq{background-color:#ffffc7;text-align:center;vertical-align:top}
.tg .tg-quxf{background-color:#ffffff;text-align:center;vertical-align:top}
</style>

<table class="tg">
  <tr>
    <th class="tg-7geq">Instrucción</th>
    <th class="tg-7geq">Tipo</th>
    <th class="tg-7geq">Codop </th>
    <th class="tg-7geq">Efecto </th>
  </tr>
  <tr>
    <td class="tg-baqh">OR</td>
    <td class="tg-baqh">2 operandos</td>
    <td class="tg-baqh">0101</td>
    <td class="tg-baqh">Dest=Dest or Origen </td>
  </tr>
  <tr>
    <td class="tg-baqh">NOT</td>
    <td class="tg-baqh">1 operando destino</td>
    <td class="tg-baqh">1001</td>
    <td class="tg-baqh">Dest = not Dest </td>
  </tr> <tr>
    <td class="tg-baqh">AND</td>
    <td class="tg-baqh">2 operandos </td>
    <td class="tg-baqh">0100 </td>
    <td class="tg-baqh">Dest=Dest and Origen </td>
  </tr>
</table>


### Cómo funcionan?

Las operaciones lógicas se aplican **bit a bit**, es decir, columna a columna.

```
11001100 AND 11110000 = 11000000
```

```
11001100 OR 11110000 = 11111100
```



# A trabajar

¿Cuál es la máscara que debe aplicarse para poner todos los bits de una cadena en 0, salvo el ultimo bit?

