<template>
    <div class="display">
        <div class="operation">{{toDisplay.expression}}</div>
        <div class="answer">{{toDisplay.answer}}</div>
    </div>
</template>

<script>

export default {
  name: 'DisplayOperations',
  props: {
      toDisplay: Object
  }
}
</script>

<style>
    .display {
        position: relative;
        height: 20vh;
        text-align: right;
        font-size: 7vh;
        word-break: break-all;
        padding: 10px 15px 0 0;
    }
    .display::after {
        content: "";
        background: #41b883;
        position: absolute;
        bottom: 0;
        left: 7%;
        height: 1px;
        width: 85%;
    }
</style>