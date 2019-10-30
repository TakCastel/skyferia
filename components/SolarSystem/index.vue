<template>
  <v-layout align-center justify-center>
    <div id="solar-system" class="mt-5">
      <!-- Circles closest to the central point -->
      <div id="earth-orbit" class="orbite">
        <div class="astre earth" @click.prevent="handleClick('earth')" />
      </div>

      <!-- Circles second closest to the central point -->
      <div id="mars-orbit" class="orbite">
        <div class="astre mars" @click.prevent="handleClick('mars')" />
      </div>

      <!-- Circles furthest away to the central point -->
      <div id="kuiper-orbit" class="orbite">
        <div class="astre kuiper" @click.prevent="handleClick('kuiper')" />
      </div>
    </div>
  </v-layout>
</template>

<script>
export default {
  methods: {
    handleClick (location) {
      switch (location) {
        case 'earth':
          alert('Il est impossible de vous rendre sur Terre pour le moment')
          break
        case 'mars':
          alert('Vous êtes déjà sur cette planète')
          break
        case 'kuiper':
          alert('Vous allez être redirigé sur Kuiper')
          break
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.orbite {
  pointer-events: none;
}
.astre {
  pointer-events:all;
  cursor: pointer
}
/* ---------- Container for the orbiting circles animation ---------- */
#solar-system {
  position: relative;
  overflow: hidden;
  height: 500px;
  width: 500px;
}

/* ---------- Inner orbit - This is the circles closest to the central point ---------- */
#earth-orbit {
  position: absolute;
  top: 175px;
  left: 175px;
  width: 150px;
  height: 150px;
  border: 2px #424242 dashed;
  border-radius: 100%;
  animation: spin-right 200s linear infinite;
}

/* ---------- Repeating styles for the inner orbiting circles ---------- */
.earth {
  position: absolute;
  top: 62px;
  left: -6px;
  height: 10px;
  width: 10px;
  border-radius: 100%;
  background-color: #9F98E6;
}

/* ---------- Middle orbit - This is the circles second closest to the central point ---------- */
#mars-orbit {
  position: absolute;
  top: 125px;
  left: 125px;
  width: 250px;
  height: 250px;
  border: 2px #424242 dashed;
  border-radius: 100%;
  animation: spin-right 250s linear infinite;
}

/* ---------- Repeating styles for the inner orbiting circles ---------- */
.mars {
  position: absolute;
  top: 25px;
  left: 25px;
  height: 20px;
  width: 20px;
  border-radius: 100%;
  background-color: #8c4945;
}

/* ---------- Outer orbit - This is the circles furthest away from the central point ---------- */
#kuiper-orbit {
  position: absolute;
  width: 485px;
  height: 485px;
  border: 2px #424242 dashed;
  border-radius: 100%;
  animation: spin-right 500s linear infinite;
}

/* ---------- Repeating styles for the outer orbiting circles ---------- */
.kuiper {
  position: absolute;
  top: 54px;
  left: 54px;
  height: 30px;
  width: 30px;
  border-radius: 100%;
  background-color: #00FFCA;
}

/* ---------- Animation ---------- */
@keyframes spin-right {
  100% {
    transform: rotate(360deg);
  }
}
</style>
