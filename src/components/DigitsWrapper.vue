<template>
    <ul class="keys-wrapper">
        <KeysItem 
        v-for="(key, id) in keys" 
        :content="key" 
        :key="id"
        @click="$emit('get-symbol', key)"
        />
        <li class="content equals" @click="$emit('equals')">
            <i class="fa-solid fa-equals"></i>
        </li>
    </ul>
</template>

<script>
import KeysItem from "./KeysItem.vue"

export default {
  name: 'DigitsWrapper',
  data() {
      return {
            keys: "1234567890".split('')
      }
  },
  components: {
      KeysItem,
  }
}
</script>

<style>
    .keys-wrapper {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-template-rows: repeat(4, 1fr);
        grid-column-gap: 5px;
        grid-row-gap: 5px;
        grid-area: 2 / 1 / 6 / 4;
    }
    .equals {
        grid-area: 4 / 3 / 5 / 4; 
    }
</style>