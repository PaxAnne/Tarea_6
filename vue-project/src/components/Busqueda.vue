<script>
export default {
  data() {
    return {
      seleccionado: "",
      filtro: "",
      options: [
        { value: "", text: "Seleccionar" },
        { value: "autor", text: "Autor" },
        { value: "genero", text: "Género" },
        { value: "titulo", text: "Título" },
      ],
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
      ],
    };
  },
  methods: {},
  computed: {
    filtrados: function () {
      if (this.seleccionado == "autor") {
        return this.libros.filter(
          (libros) => !libros.autor.toLowerCase().trim().indexOf(this.filtro)
        );
      }
      if (this.seleccionado == "genero") {
        return this.libros.filter(
          (libros) => !libros.genero.toLowerCase().trim().indexOf(this.filtro)
        );
      }
      if (this.seleccionado == "titulo") {
        return this.libros.filter(
          (libros) => !libros.titulo.toLowerCase().trim().indexOf(this.filtro)
        );
      }
      if (this.seleccionado == "") {
        return this.libros;
      }
    },
  },
};
</script>

<template>
  <main>
    <div class="Supremo">
      <div>
        <h1 id="titulo">Búsqueda</h1>
      </div>

      <div>
        <b-form-input v-model="filtro" placeholder="Buscar"></b-form-input>
      </div>

      <div>
        <b-form-select
          v-model="seleccionado"
          :options="options"
        ></b-form-select>
      </div>
    </div>

    <div class="Resultados">
      <div id="libro" v-for="libro in filtrados" :key="libro.id">
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

<style >
#titulo {
  font-family: fantasy;
  color: darkslateblue;

}
.Supremo {
  padding-top: 35px;
  padding-left: 30px;
  display: grid;
  grid-template-columns: 14% 30% 20% 10%;
  align-items: center;
  gap: 20px;
}
#ok {
  background-color: brown;
}
.Resultados {
  padding-top: 100px;
  display: grid;
  justify-content: space-evenly;
  grid-template-columns: auto auto auto;
  row-gap: 100px;
}
#libro {
  justify-content: center;
  display: grid;
  grid-template-columns: 75px 75px 80x 80px;
  grid-template-rows: 52px 26px 52px 42px 42px;
  gap: 10px;
  width: 20rem; 
}

#imagenLibro {
  display: flex;
  flex-grow: 1;
  grid-area: 1 / 2 / 5 / 3;
  justify-content: center;
  align-items: center;
}
#tituloLibro {
  display: flex;
  width: 160px;
  grid-area: 1 / 3 / 1 / 4;
  font-size: 20px;
}
#generoLibro {
  grid-area: 5 / 3 / 5 / 4;
  width: 160px;
}

#autorLibro {
  grid-area: 2 / 3 / 2 / 3;
  display: flex;
  width: 160px;
  align-items:center;
  
}

#descripcionLibro {
  display: flex;
  align-items: center;
  grid-area: 2 / 3 / 5 / 4;
  width: 160px;
}
</style>
