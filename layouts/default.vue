<template>
    <n-config-provider :theme="theme">
      <n-card>
        <n-page-header title="Weather App" >
          <template #avatar>
            <n-icon size="40" :component="WeatherHailNight48Regular"/>
          </template>
         <template #title>
            <a href="#">Weather App</a>
          </template>
         <template #extra>
            <n-card>
              <n-space>
                <n-icon size="40" :component="WeatherMoon48Regular" @click="changeTheme"/>
             </n-space>
            </n-card>
          </template>
        </n-page-header>
        <slot />
      </n-card>
    </n-config-provider>
</template>

<script setup lang="ts">
import WeatherHailNight48Regular from '@vicons/fluent/WeatherHailNight48Regular'
import WeatherMoon48Filled from '@vicons/fluent/WeatherMoon48Filled'
import WeatherMoon48Regular from '@vicons/fluent/WeatherMoon48Regular'
import { NIcon, NPageHeader, NSpace, darkTheme, NConfigProvider,NCard } from 'naive-ui'
import type {BuiltInGlobalTheme} from "naive-ui/es/themes/interface";

const theme: Ref<null | BuiltInGlobalTheme> = ref(null)

const changeTheme = () => {
  if (theme.value === null) {
    theme.value = darkTheme
  } else theme.value = null
}
</script>

<style scoped>

</style>