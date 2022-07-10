<template>
    <div class="wrapper-keys">
        <DigitsWrapper @get-symbol="getSymbol" @equals="equals"/>
        <SignsWrapper @get-symbol="getSymbol" @remove-symbol="removeSymbol"/>
    </div>
</template>

<script>
import SignsWrapper from "./SignsWrapper.vue"
import DigitsWrapper from "./DigitsWrapper.vue"

export default {
  name: 'CalculatorKeys',
  data() {
      return {
        toDisplay: {
            expression: "",
            answer:""
        }
      }
  },
  methods: {
      getSymbol(item) {
          if (!(/^(\/|\*|\+|-|\))/.test(item)) || this.toDisplay.expression)
          {
            this.toDisplay.expression += item; 
            this.calculateAnswer();
            this.$emit('get-expression', this.toDisplay)
          }
      },
      removeSymbol() {
          console.log(typeof this.toDisplay.expression, this.toDisplay.expression.length);
          if (this.toDisplay.expression.length) {
            this.toDisplay.expression = this.toDisplay.expression.slice(0, -1); 
            this.calculateAnswer();
            this.$emit('get-expression', this.toDisplay);
          }
      },
      equals()
      {
          const answer = this.toDisplay.answer;
          this.toDisplay.expression = `${answer}`;
          this.$emit('get-expression', this.toDisplay);
      },
      calculateAnswer()
      {
        if (!(/(\/|\*|\+|-)$/.test(this.toDisplay.expression)))
            this.toDisplay.answer = eval(this.toDisplay.expression);
      }
  },
  components: {
      SignsWrapper,
      DigitsWrapper
  }
}
</script>

<style>
    .wrapper-keys {
        display: grid;
        height: 55vh;
        grid-template-columns: repeat(4, 1fr);
        grid-template-rows: repeat(5, 1fr);
        grid-column-gap: 5px;
        grid-row-gap: 5px; 
    }
</style>