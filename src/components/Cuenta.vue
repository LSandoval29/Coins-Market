<template>
  <h2>Tipo de cuenta: {{ cuenta }}</h2>
  <h2>Mi Saldo: {{ saldo }}</h2>
  <h2>Cuenta {{ estado ? "Activa" : "Desactivada" }}</h2>

  <div v-for="(item, index) in servicios" :key="index">
    {{ index + 1 }} - {{ item }}
  </div>

  <accion-saldo texto="Aumentar Saldo" @accion="aumentar" />
  <accion-saldo
    texto="Disminuir Saldo"
    @accion="disminuir"
    :disabled="btnDesactivar"
  />
</template>

<script>
import AccionSaldo from "./AccionSaldo.vue";
export default {
  components: { AccionSaldo },
  data() {
    return {
      cuenta: "Visa",
      saldo: 1000,
      estado: true,
      servicios: ["Giro", "Abono", "Transferencia"],
      btnDesactivar: false,
    };
  },
  methods: {
    aumentar() {
      this.btnDesactivar = false;
      this.estado = true;
      this.saldo = this.saldo + 100;
    },
    disminuir() {
      if (this.saldo === 0) {
        this.btnDesactivar = true;
        this.estado = false;
        alert("Saldo agotado!");
        return;
      }
      this.saldo = this.saldo - 100;
    },
  },
};
</script>

<style></style>
