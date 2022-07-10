<template>
    <main class="wrapper">
      <CalculatorDisplay :toDisplay="toDisplay"/>
      <CalculatorKeys @get-expression="getExpression"/>
      <LongExpAlarm :isLong="toDisplay.isLong"/>
    </main>
</template>

<script>
import CalculatorDisplay from "./CalculatorDisplay.vue"
import CalculatorKeys from "./CalculatorKeys.vue"
import LongExpAlarm from "./LongExpAlarm.vue"

export default {
  name: 'CalcWrapper',
  data() {
    return {
      toDisplay: {
        expression: "",
        answer: "",
        isLong: false
      }
    }
  },
  methods: {
    getExpression(item) {
      this.toDisplay.isLong = item.expression.length > 15;
      this.toDisplay = !this.toDisplay.isLong ? item : this.toDisplay;
    }
  },
  components: {
    CalculatorDisplay,
    CalculatorKeys,
    LongExpAlarm
  }
}
</script>


<style>
    .wrapper {
        margin: 0 auto;
        margin-top: 20px;
        min-height: 75vh;
        width: 35vw;
        box-shadow: 1px 1px 11px 1px #41b883;
    }
</style>