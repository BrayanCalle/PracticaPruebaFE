<template>
  <!-- Primer Cuadro -->
  <div class="d-inline-block mb-5 col-6 col-lg-4 tiendas-diseno mb-5">
      <div class="card h-100 contenedor-tiendas">
          <img v-bind:src="tienda.imagen_tienda" class="card-img-top" :alt="tienda.nombre" width="258px" height="182px">
          <div class="card-body">
              <p class="card-title nombre-tienda">{{ tienda.nombre }}</p>
              <p class="card-text">
                  {{ tienda.direccion }}
              </p>
          </div>
          <div class="card-footer row" v-if="tienda.estado == true">
                <small class="text-muted d-inline-block col-7">Abierto</small>
                <a class="d-flex justify-content-start col-4" href="">
                    <button type="button" class="btn-consultar colorfondo-principal">
                        Consultar
                    </button>
                </a>
          </div>
          <div class="card-footer" v-else>
              <small class="text-muted">Cerrado</small>
          </div>
      </div>
  </div>
  <!-- Fin Primer Cuadro -->
</template>
  
<script>
  export default {
    name: "TiendaPrincipal",
  
    data() {
      return {
        hover: false,
        // iconom: 'store',
      };
    },
  
    props: ["tienda"],
  
    //   {
    // marcas: {
    //   type: Array,
    //   default: () => [],
    // },
    //   },
  };
  </script>
  
<style scoped>
.tiendas-diseno{
    padding: 0em 3.75em;
}

.contenedor-tiendas{
  border-radius: 1.5em;
  -webkit-border-radius: 1.5em;
  -moz-border-radius: 1.5em;
  -ms-border-radius: 1.5em;
  -o-border-radius: 1.5em;
  box-shadow: 0.125em 1.5em 1.25em 0em #00000063;
}

.contenedor-marcas div .card-img-top {
  border-top-left-radius: 1.5em;
  border-top-right-radius: 1.5em;
}

.nombre-tienda{
    color: #FFCC2E;
    font-weight: 700;
    font-size: 1.2em ;
}
</style>