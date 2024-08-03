<script setup>
const { locale, locales, setLocale } = useI18n()
const switchLocalePath = useSwitchLocalePath()

const target = ref(locale)

function handleLocale() {
  setLocale(target.value)
}
</script>

<template>
  <NuxtLink to="/">
    Home
  </NuxtLink>
  <select v-model="target" @change="handleLocale()">
    <option v-for="item in locales" :key="item.code" :value="item.code">
      {{ item.name }}
    </option>
  </select>
  <h1 class="text-red border">
    {{ $t('hello') }}
  </h1>
</template>
