<script setup>
import { VueElement } from "@vue/runtime-dom";
import { RouterLink } from "vue-router";
</script>

<template>
  <div>
    <div class="barra">
      <div class="titulo">
        <h1>Library</h1>
      </div>

      <div class="botones">
        
        <b-button href="/" variant="warning">Home</b-button>
        <b-button href="/search" variant="info" >Search</b-button>
        <div id="avatar">
            <b-avatar src="https://placekitten.com/300/300" size="4rem"></b-avatar>
        </div>
      </div>
    </div>

    <div class="contenido">
      <RouterView></RouterView>
    </div>
  </div>
</template>


<style>
.barra {
  background-color: rgb(133, 102, 163);
  display: flex;
  justify-content: space-between;
  flex-flow: row wrap;
  padding-left: 3%; 
  padding-right: 3%;
  border-radius: 8px;
  border: 1px solid gray;
  padding-bottom: 8px;
}
.titulo {
  color: rgb(70, 204, 204);
}
.botones {
  display: flex;
  align-items: center;
  gap: 10px;
}
#b {
  background-color: rgb(231, 157, 67);
}
#avatar{
  padding-left: 20px;
}
</style>