<template>
    <ul class="signs-wrapper">
        <li class="content" @click="$emit('remove-symbol')">
            <i class="fa-solid fa-delete-left"></i>
        </li>
        <li class="content" @click="$emit('get-symbol', '/' )">
            <i class="fa-solid fa-divide"></i>
        </li>
        <li class="content" @click="$emit('get-symbol', '*')">
            <i class="fa-solid fa-xmark"></i>
        </li>
        <li class="content" @click="$emit('get-symbol', '-')">
            <i class="fa-solid fa-minus"></i>
        </li>
        <li class="content" @click="$emit('get-symbol', '+')">
            <i class="fa-solid fa-plus"></i>
        </li>
    </ul>
</template>

<style>
    .signs-wrapper {
        list-style-type: none;
        display: grid;
        grid-template-columns: 1fr;
        grid-template-rows: repeat(5, 1fr);
        grid-column-gap: 5px;
        grid-row-gap: 5px;
        grid-area: 1 / 4 / 6 / 5; 
        padding: 0;
    }
</style>