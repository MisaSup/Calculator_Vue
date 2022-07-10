<template>
    <div :class="isZero">
        {{ content }}
    </div>
</template>


<script>
export default {
    name: 'KeysItem',
  props: {
      content: String
  },
  computed: {
      isZero(){
        return {
            zero: this.$props.content === '0',
            content: true
        }
      }
  }
}
</script>

<style>
.content {
    font-size: 5vh;
    display: flex;
    align-items: center;
    justify-content: space-around;
    cursor: pointer;
}
.content:hover
{
    transition-duration: 0.3s;
    font-size: 6vh;
}
.zero {
     grid-area: 4 / 2 / 5 / 3;
}
</style>