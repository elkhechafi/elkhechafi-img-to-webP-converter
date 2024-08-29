<script setup>
import ImageUploader from '../components/ImageUploader.vue';
</script>

<template>
  <main>
    <h4 class="main-title">Upload an Image by browsing from your device or draging and droping here</h4>
    <p class="description">Please only use images extensions, like PNG, JPEG. SVG and PDF don't work for now</p>
    <ImageUploader class="dropZone"/>
  </main>
</template>


<style scoped lang="scss">
  .main-title{
    width: 100%;
    text-align: center;
    color: var(--text-color);
    font-size: 2rem;
  }
  .description{
    width: 100%;
    text-align: center;
    color: var(--text-color);
    font-size: 1.3rem;
  }
  .dropZone{
    margin: 0% auto;
    width: 60%;
    height: auto;
  }

  @media only screen and (max-width: 600px) {
    main{
      display: block;
      .main-title{
        margin: 10vh auto 3vh;
        width: 100%;
        text-align: center;
        color: var(--text-color);
        font-size: 1.8rem;
      }
      .description{
        width: 100%;
        text-align: center;
        color: var(--text-color);
        font-size: 1rem;
        margin-bottom: 3vh;
      }
      .dropZone{
        margin: 0% 15%;
        width: 70%;
        height: auto;
      }
    }
  }
</style>
