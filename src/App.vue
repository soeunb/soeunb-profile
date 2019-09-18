<template>
  <div id="app">
    <ProfileHeader></ProfileHeader>
    <ProfileContent v-bind:items="projectItems"/>
    <ProfileDetail v-bind:items="projectItems"/>
  </div>
</template>

<script>
import ProfileHeader from './components/ProfileHeader.vue'
import ProfileContent from './components/ProfileContent.vue'

export default {
  components: {
    'ProfileHeader': ProfileHeader,
    'ProfileContent': ProfileContent
  },
  data () {
    return {
      projectItems: [
        {
          thumbnail: require('./assets/imgs/samsung.jpg'),
          description: 'samsung'
        },
        {
          thumbnail: require('./assets/imgs/lg.jpg'),
          description: 'lg'
        },
        {
          thumbnail: require('./assets/imgs/aia.jpg'),
          description: 'aia'
        },
        {
          thumbnail: require('./assets/imgs/amore.jpg'),
          description: 'amore'
        },
        {
          thumbnail: require('./assets/imgs/hallym.jpg'),
          description: 'hallym'
        },
        {
          thumbnail: require('./assets/imgs/more.jpg'),
          description: 'more'
        }
      ],
      visible: false,
      index: 0 // default
    }
  }
}
</script>

<style>
:root {
    font-size: 10px;
}

*,
*::before,
*::after {
    box-sizing: border-box;
}

body {
    font-family: "Open Sans", Arial, sans-serif;
    min-height: 100vh;
    background-color: #fafafa;
    color: #262626;
    padding-bottom: 3rem;
}

img {
    display: block;
}

.container {
    max-width: 93.5rem;
    margin: 0 auto;
    padding: 0 2rem;
}

.btn {
    display: inline-block;
    font: inherit;
    background: none;
    border: none;
    color: inherit;
    padding: 0;
    cursor: pointer;
}

.btn:focus {
    outline: 0.5rem auto #4d90fe;
}

.visually-hidden {
    position: absolute !important;
    height: 1px;
    width: 1px;
    overflow: hidden;
    clip: rect(1px, 1px, 1px, 1px);
}
</style>
