<template>
  <div id="app">
    <span>
      <button class="vermelho" @click="componente = 'ComponenteVermelho'">
        Carregar Componente Vermelho
      </button>
      <button class="verde" @click="componente = 'ComponenteVerde'">
        Carregar Componente Verde
      </button>
      <button class="azul" @click="componente = 'ComponenteAzul'">
        Carregar Componente Azul
      </button>
    </span>

    <!-- Componentes dinamicos, e passar elementos via Slot! 
		Que o conteudo que está dentro do componente, seja passado via slot marcar o nome da cor em destaque
    apenas um compoente seja exibido de uma vez, quando o usuário selecionar o
    botão -->
    <component :is="componente">
      <span slot="conteudo"
        >Conteúdo do Componente <strong> {{ componente }}</strong></span
      >
    </component>
  </div>
</template>

<script>
import ComponenteVermelho from "./components/CompoenenteVermelho.vue";
import ComponenteAzul from "./components/ComponenteAzul.vue";
import ComponenteVerde from "./components/ComponenteVerde.vue";

export default {
  name: "app",
  components: { ComponenteVermelho, ComponenteVerde, ComponenteAzul },
  data() {
    return {
      componente: "ComponenteVermelho",
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

button {
  padding: 10px;
  color: #fff;
  font-size: 1.3rem;
}

.caixa {
  color: #fff;
  font-size: 1.8rem;
  padding: 25px;
  margin: 10px 0px;
}

.vermelho {
  border: 2px solid red;
  background-color: #f54235;
}

.verde {
  border: 2px solid green;
  background-color: #49b057;
}

.azul {
  border: 2px solid blue;
  background-color: #2594f0;
}
</style>
