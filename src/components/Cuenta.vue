<template>
  <h1>Saldo: {{summary}}</h1>
  <h1>Tipo de cuenta: {{type}}</h1>
  <h1>cuenta: {{state ? 'Activa' : 'Descativada'}}</h1>
  <div v-for="(servicio, index) in servicios" :key="index">{{index + 1}} - {{servicio}}</div>
  <AccionSaldo txt="Aumentar Saldo" @action="increment" />
  <AccionSaldo :disabled="disabled" txt="Restar Saldo" @action="decrement" />
</template>

<script>
import AccionSaldo from "./AccionSaldo";
export default {
  data() {
    return {
      summary: 1000,
      type: "visa",
      state: true,
      servicios: ["giro", "transferencia", "abono"],
      disabled: false,
    };
  },
  components: {
    AccionSaldo,
  },
  methods: {
    increment() {
      this.summary = this.summary + 100;
      this.disabled = false;
    },
    decrement() {
      if (this.summary <= 0) {
        this.disabled = true;
        return alert("Saldo insuficiente");
      }
      this.summary = this.summary - 100;
    },
  },
};
</script>

<style>
</style>