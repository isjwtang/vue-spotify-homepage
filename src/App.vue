<template>
  <div class="bg-dark h-screen">
    <div class="flex" style="height: 88vh;">
      <!-- side nav -->
      <div class="w-56 bg-black h-full flex-none" bg-black h-full>
        <div class="p-6">
          <img
            src="./assets/Spotify_Logo_RGB_Black.png"
            class="h-10"
            style="filter: brightness(0) invert(1)"
          />
        </div>
        <div class="mx-2">
          <button
            v-for="page in pages"
            :key="page.index"
            @click="setID = page.id"
            :class="
              `w-full text-sm font-semibold font-xs rounded px-3 py-2 flex items-center justify-start ${
                setID === page.id ? 'bg-light text-white' : 'text-lightest'
              }`
            "
          >
            <i class="material-icons mr-3">{{ page.icon }}</i>
            <p>{{ page.name }}</p>
          </button>
        </div>
      </div>
      <!-- main content -->
      <div class="w-full h-full relative">
        <!-- header -->
        <div class="w-full sticky top-0 p-2"></div>
      </div>
    </div>
    <!-- play bar -->
    <div class="w-full bg-light" style="height: 12vh"></div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data: function() {
    return {
      pages: [
        { index: 1, id: 'home', name: 'Home', icon: 'home' },
        { index: 2, id: 'search', name: 'search', icon: 'search' },
        { index: 3, id: 'library', name: 'Your Library', icon: 'bar_chart' },
      ],
      setID: 'home',
    }
  },
  components: {},
  methods: {},
}
</script>

<style>
@import url('https://fonts.googleapis.com/icon?family=Material+Icons');
#app {
  font-family: 'Material Icons', Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: 400;
}
</style>
