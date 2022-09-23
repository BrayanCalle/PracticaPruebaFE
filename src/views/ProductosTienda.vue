<template>
    <section class="mt-5 container">
        <div class="row mt-5 mb-5">
            <h1>Soy el producto</h1>
            {{ productos }}
        </div>
    </section>
</template>

<script>
import axios from "axios";
// import TiendaPrincipal from "@/components/Tienda/TiendaPrincipal";
export default {
  name: "HomePrincipal",
  components: {
    // TiendaPrincipal,
  },
  data() {
    return {
        productos: [],
    };
  },
  created() {
    this.getProductos();
  },
  methods: {
    getProductos(categoria__tienda) {
      axios
        .get(`http://127.0.0.1:8000/api/v1/productos/?precio__gte=&precio__lte=&categoria__nombre=&categoria__tienda=${categoria__tienda}`)
        .then((response) => {
          this.productos = response.data.results;
          console.log(this.productos.tienda)
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