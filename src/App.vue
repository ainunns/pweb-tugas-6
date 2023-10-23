<template>
  <main>
    <header>
      <h1>Create a simple calculator using Vue JS</h1>
      <form @submit.prevent="calculate">
        <label for="firstNumber">First Number: </label>
        <input v-model="firstNumber" type="number" />
        <br />
        <label for="operator">Operator: </label>
        <select v-model="operator">
          <option value="+">tambah (+)</option>
          <option value="-">kurang (-)</option>
          <option value="*">kali (*)</option>
          <option value="/">bagi (/)</option>
        </select>
        <br />
        <label for="secondNumber">Second Number: </label>
        <input v-model="secondNumber" type="number" />
        <br />
        <button type="submit">hitung</button>
      </form>
      <p>Hasil perhitungan = {{ result }}</p>
    </header>
  </main>
</template>

<script>
export default {
  data() {
    return {
      firstNumber: 0,
      operator: '+',
      secondNumber: 0,
      result: 0
    }
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case '+':
          this.result = this.firstNumber + this.secondNumber
          break
        case '-':
          this.result = this.firstNumber - this.secondNumber
          break
        case '*':
          this.result = this.firstNumber * this.secondNumber
          break
        case '/':
          this.result = this.firstNumber / this.secondNumber
          break
        default:
          this.result = 'Invalid operator'
      }
    }
  }
}
</script>
