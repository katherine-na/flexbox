<style>
  .conteiner {
    display: flex;
    justify-content: space-around;
  }

  </style>

<h1 align="center"> Flexbox</h1>

<p align="center">
Se creó para mejorar la forma en la que se hace el diseño responsivo, evitando así el uso de float, escribiendo menos código y facilitando el posicionamiento de elementos
</p>

## Estructura de Flex Container

![](https://camo.githubusercontent.com/12ac134bb129d3a276a9c1ed9fd066cf23c9b193f528fd29b2ad1c4cc9d6a172/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31312f30302d62617369632d7465726d696e6f6c6f67792e737667)

**eje principal (main axis)**  
El eje principal de un flex container es el eje primario y a lo largo de él son insertados los flex ítems

**main-start | main-end**  
Los flex ítems se insertan en el contenedor empezando por el lado start, dirigiéndose hacia el lado end

**tamaño principal (main size)**  
Es el ancho o alto de un flex ítem

**eje transversal (cross axis)**  
Su dirección depende de la dirección del eje principal

**cross-start | cross-end**  
Se llenan con ítems y se agregan al contenedor, comienza desde el lado cross-star hacia el lado cross-end

**cross-size**  
Es el ancho o el alto del ítem, dependiendo de lo que se encuentre en la tranversal

El Contenedor-Flex **(flex container)** es nuestro contenedor padre y es él quién va a contener a todos los elementos hijos a los que queremos posicionar.  
El Elemento-Flex **(flex item)** es nuestro elemento hijo el cual utilizará todo el espacio disponible para ubicarse de acuerdo a las propiedades

```html
<div class="flex-container">
  <div>1</div>

  <div>2</div>

  <div>3</div>
</div>
```

```css
.flex-container {
  display: flex;
}
```

<div class="conteiner">

<div class="first">
## Propiedades para el padre (flex container)

### display

Define un flex container; en línea o bloque

```css
.container {
  display: flex; /* or inline-flex */
}
```

<img src="https://camo.githubusercontent.com/a21eff89a381a6f8470c4b0952874cbdf45b3486b3afe084b6f75095acd9c8d9/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f30312d636f6e7461696e65722e737667" width="300" heigh="300">

### flex-direction

Define la dirección en que se colocan los flex items en el flex container

```css
.container {
  flex-direction: row; /* or row-reverse | column | column-reverse */
}
```

<img src="https://camo.githubusercontent.com/9ece155a18899ad915ccef5da80f618006b82c49277beea200e22c1f70d966da/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f666c65782d646972656374696f6e2e737667" width="300" heigh="300">

### flex-wrap

Los flex items se ajusten según sea necesario con esta propiedad

```css
.container {
  flex-wrap: wrap; /* or wrap-reverse | nowrap */
}
```

<img src="https://camo.githubusercontent.com/fd3727f675a455a68ce92ed75cf57ff202447fd18f730f7978b80a3bb0e79638/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f666c65782d777261702e737667" width="300" heigh="300">

### justify-content

Define la alineación a lo largo del eje principal (main axis | cross axis)

```css
.container {
  justify-content: flex-start;
  /* or flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe */
}
```

<img src="https://camo.githubusercontent.com/99c142d1b528f7c33757152139ff8131358dc3ddb77eb3b2a6fc9a044d2bb53e/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f6a7573746966792d636f6e74656e742e737667" width="300" heigh="300">

### align-items

Define cómo se distribuyen los flex items

```css
.container {
  align-items: stretch;
  /* flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe */
}
```

<img src="https://camo.githubusercontent.com/6a31df6631678ba5686f4ec6203cd74c094924517b8b8a1f21981f26fb21eccf/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f616c69676e2d6974656d732e737667" width="300" heigh="300">

### align-content

Alinea las líneas de un flex container dentro cuando hay espacio adicional en el cross axis.

```css
.container {
  align-content: flex-start;
  /* flex-end | center | space-between | space-around | space-evenly | stretch | start | end | baseline | first baseline | last baseline + ... safe | unsafe; */
}
```

<img src="https://camo.githubusercontent.com/b3b9b868dc5b3bbb69ecd7ea7a950f7b33ca346d4c761d555717ec8b340bb966/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f616c69676e2d636f6e74656e742e737667" width="300" heigh="300">

### gap, row-gap, column-gap

Controla el espacio entre flex items.

```css
.container {
  display: flex;
  ...
  gap: 10px;
  gap: 10px 20px; /* row-gap column gap */
  row-gap: 10px;
  column-gap: 20px;
}
```

<img src="https://css-tricks.com/wp-content/uploads/2021/09/gap-1.svg" width="300" heigh="300">
</div>

<div class="second">
## Propiedades para el hijo (flex items)

### order

La propiedad order controla el orden en que aparecen en el container flex.

```css
.item {
  order: 5; /* default is 0 */
}
```

<img src="https://camo.githubusercontent.com/0a50368a4fd1553a70dfebf0937b7caf8354a83cae32097c2229822a277e3f08/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f6f726465722e737667" width="300" heigh="300">

### flex-grow

Define la capacidad de crecimiento de un flex item si es necesario.

```css
.item {
  flex-grow: 4; /* default 0 */
}
```

<img src="https://camo.githubusercontent.com/79e51e3724731b3f5f1597aaad21f9820bebcd30dcbe4c6ae546499694381b1e/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f666c65782d67726f772e737667" width="300" heigh="300">

### flex-shrink

Define la capacidad de que un flex item se encoja si es necesario.

```css
.item {
  flex-shrink: 3; /* default 1 */
}
```

### flex-basis

Es la abreviatura de flex-grow, flex-shrink y flex-basis combinados.

```css
.item {
  flex: none | [ < "flex-grow" > < "flex-shrink" >? || < "flex-basis" > ];
}
```

### align-self

Permite anular la alineación predeterminada para flex items individuales.

```css
.item {
  align-self: auto;
  /* flex-start | flex-end | center | baseline | stretch */
}
```

<img src="https://camo.githubusercontent.com/634a0654d355ea5af43d1bd868604176e01f726de196c4868dc0e0b80f3eee1f/68747470733a2f2f6373732d747269636b732e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031382f31302f616c69676e2d73656c662e737667" width="300" heigh="300">
</div>

</div>
