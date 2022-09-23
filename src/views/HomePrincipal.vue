<template>
    <section class="mt-5 container">
        <div class="row mt-5 mb-5">
            <tienda-principal 
                v-for="tienda in tiendas" 
                v-bind:key="tienda.id"
                v-bind:tienda="tienda"
            >
                
            </tienda-principal>
        </div>
    </section>
</template>

<script>
import axios from "axios";
import TiendaPrincipal from "@/components/Tienda/TiendaPrincipal";
export default {
  name: "HomePrincipal",
  components: {
    TiendaPrincipal,
  },
  data() {
    return {
        tiendas: [],
    };
  },
  created() {
    this.getTiendas();
  },
  methods: {
    getTiendas() {
      axios
        .get("http://127.0.0.1:8000/api/v1/tiendas/")
        .then((response) => {
          this.tiendas = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  }
}

</script>

<style scoped>

</style>