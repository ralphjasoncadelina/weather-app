<template>
  <div
    class="flex py-6 px-3 bg-weather-secondary rounded-md shadow-md cursor-pointer"
  >
    <div class="flex flex-col flex-1">
      <h2 class="text-3xl">{{ city.city }}</h2>
      <h3>{{ textWithSpaces }}</h3>
    </div>

    <div class="flex flex-col gap-2">
      <p class="text-3xl self-end">
        {{ Math.round(city.weather.main.temp) }}&deg;
      </p>
      <div class="flex gap-2">
        <span class="text-xs">
          H:
          {{ Math.round(city.weather.main.temp_max) }}&deg;
        </span>
        <span class="text-xs">
          L:
          {{ Math.round(city.weather.main.temp_min) }}&deg;
        </span>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  city: {
    type: Object,
    default: () => {},
  },
});

let textSpace = props.city.state
const addSpaces = (text) => {
  return text.replace(/([a-z])([A-Z])/, '$1 $2')
} 
let textWithSpaces = addSpaces(textSpace)
</script>