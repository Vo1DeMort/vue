<script setup lang="ts">
import { onMounted, ref } from "vue";
import type { Ref } from "vue";


type Geolocation = {
  latitude: number;
  longitude: number;
}

// reactive property
const coords: Ref<Geolocation | undefined> = ref(); // coordinates
const geolocationBlockedByUser: Ref<boolean> = ref(false);

const getGeolocation = async (): Promise<void> => {
  navigator.geolocation.getCurrentPosition(
    async (position: { coords: Geolocation }) => {
      coords.value = position.coords;
    },
    (error: { message: string }) => {
      geolocationBlockedByUser.value = true;
      console.error(error.message);
    }
  );
};

//NOTE: execute only when the component is "mounted"
onMounted(async () => {
  await getGeolocation();
})
</script>

<template>
  <div v-if="coords && !geolocationBlockedByUser">
    lalitude:{{ coords.latitude }} ,longitude :{{ coords.longitude }}
  </div>
  <div v-if="geolocationBlockedByUser">User denined location access </div>
</template>
