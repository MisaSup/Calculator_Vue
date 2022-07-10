<script>
export default {
    props: {
        isLong: Boolean
    },
}
</script>

<template>
    <Transition >
        <div v-if="isLong" class="alarm-long">
            This expression too long.
            Please press equals or remove symbols to continue.
        </div>
    </Transition>
</template>

<style scoped>
.alarm-long {
    position: absolute;
    width: 10vw;
    top: 115px;
    right: 300px;
    border: solid 1px #41b883;
    padding: 15px;
}
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
</style>