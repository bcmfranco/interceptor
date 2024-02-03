<template>
  <div id="container">
    <label for="capital">Capital:</label>
    <input v-model="capital" placeholder="Ingrese el capital" />

    <label for="interest">Interés:</label>
    <input v-model="interest" placeholder="Ingrese el interés" />

    <label for="returnX">Retorno neto (X):</label>
    <input :value="calculateReturnX" disabled />

    <label for="returnY">Retorno bruto (Y):</label>
    <input :value="calculateReturnY" disabled />
  </div>
</template>

<script>
export default {
  data() {
    return {
      capital: null,
      interest: null
    };
  },
  computed: {
    calculateReturnX() {
      if (this.capital && this.interest) {
        return parseFloat(this.capital) * (parseFloat(this.interest) / 100);
      }
      return null;
    },
    calculateReturnY() {
      if (this.capital && this.interest) {
        return parseFloat(this.capital) + parseFloat(this.calculateReturnX);
      }
      return null;
    }
  }
};
</script>

<style scoped>
#container {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(4, 1fr);
}

.input-field {
  margin-bottom: 20px;
}

label {
  font-size: 16px;
  color: #26a69a;
}

input {
  font-size: 16px;
  padding: 10px;
  border: 1px solid #26a69a;
  border-radius: 4px;
  margin-top: 5px;
}

.result-field {
  margin-top: 20px;
}
</style>