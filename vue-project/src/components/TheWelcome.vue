<script>
export default {
  data() {
    return {
      libros: [
        {
          id: 1,
          titulo: "El fuego no siempre quema",
          nuevo: false,
          autor: "Soniammad",
          genero: "Misterio",
          descripcion: "Ada Irons quiere llegar a ser fiscal para ayudar a los buenos.",
          img: "https://img.wattpad.com/cover/257050615-352-k537201.jpg",
        },
        {
          id: 2,
          titulo: "Parcialmente Nublado",
          nuevo: true,
          autor: "TamineRasse",
          genero: "NovelaJuvenil",
          descripcion:"La vida le sonríe a Sunny, un chico risueño..." ,
          img: "https://img.wattpad.com/cover/232100442-352-k259416.jpg",
        },
        {
          id: 3,
          titulo: "Tienes que ser tú",
          nuevo: false,
          autor: "Zara_Black",
          genero: "Romance",
          descripcion: ": ―Bueno, es una larga historia...",
          img: "https://img.wattpad.com/cover/3194677-200-k718080.jpg",
        },
        {
          id: 4,
          titulo: "Rojo bajo fuego",
          nuevo: true,
          autor: " Love Story ",
          genero: "Suspenso ",
          descripcion: "La nación corre peligro, dinero, todo empieza a ser saboteado.",
          img: "https://img.wattpad.com/cover/288372856-416-k485559.jpg",
        },
        {
          id: 5,
          titulo: "Besos sabor magenta",
          nuevo: false,
          autor: "Zara_Black",
          genero: "Humor",
          descripcion:" Diego lleva años sobornando profesores...",
          img: "https://img.wattpad.com/cover/36500633-200-k356618.jpg",
        },
        {
          id: 6,
          titulo: "El Sacrificio del Fuego",
          nuevo: true,
          autor: "InfiniteAll",
          genero: "Ciencia ficción",
          descripcion:"Tras la Guerra cada mujer embarazada da a luz a dos hijos: uno es Normal.",
          img: "https://img.wattpad.com/cover/185036099-200-k535978.jpg",
         
        },
      ],
    };
  },
};
</script>

<template>
  <main>
    <h1 id=tituloP>Busca-inador de Noveas 3.000</h1>
    <div class="Resultados">
      <div id="libro" v-for="libro in libros" :key="libro.id">
       <div id="imagenLibro">
          <b-card>
            <b-img 
              :src="libro.img" 
              alt="Portada" 
              fluid
            ></b-img>
          </b-card>
        </div>
        <h4 id="tituloLibro">{{ libro.titulo }} <b-badge v-if="libro.nuevo" variant="warning"> New</b-badge></h4>
        <span id="generoLibro">Género: {{ libro.genero }}</span>
        <span id="autorLibro">Autor/a: {{ libro.autor }}</span>
        <span id="descripcionLibro"> {{ libro.descripcion }}</span>
      </div>
    </div>
  </main>
</template>


 <style>

#tituloP{
  color:rgb(63, 63, 150);
  margin-left: 30%;
}
.Resultados {
  justify-content: space-evenly;
  padding-top: 50px;
  display: grid;
  grid-template-columns: auto auto auto auto;
}
</style>