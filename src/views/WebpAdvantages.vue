<template>
  <div class="webp-advantages">
    <h1>Advantages of Using WebP Images</h1>
    <ul>
      <li v-for="advantage in advantages" :key="advantage.id">
        <h2>{{ advantage.title }}</h2>
        <p>{{ advantage.description }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'WebPAdvantages',
  data() {
    return {
      advantages: [
        {
          id: 1,
          title: 'Smaller File Size',
          description: 'WebP images are typically 25-34% smaller than comparable JPEG images, leading to faster page loads and reduced bandwidth usage.'
        },
        {
          id: 2,
          title: 'Better Compression',
          description: 'WebP uses both lossy and lossless compression techniques, offering better compression than PNG and JPEG for images on the web.'
        },
        {
          id: 3,
          title: 'Alpha Channel Support',
          description: 'WebP supports transparency (alpha channel) with both lossy and lossless compression, making it versatile for various design needs.'
        },
        {
          id: 4,
          title: 'Animated Image Support',
          description: 'WebP can replace animated GIFs with much smaller file sizes, while maintaining image quality.'
        },
        {
          id: 5,
          title: 'Wide Browser Support',
          description: 'Most modern browsers now support WebP, including Chrome, Firefox, Edge, and Opera, with fallback options available for others.'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.webp-advantages {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 15vh auto 0;
  padding: 20px;
  background-color: var(--card-bg);
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

  h1 {
    color: var(--bg-color-reverse);
    text-align: center;
    margin-bottom: 30px;
  }

  ul {
    list-style-type: none;
    padding: 0;

    li {
      background-color: #fff;
      margin-bottom: 20px;
      padding: 20px;
      border-radius: 5px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
      transition: transform 0.3s ease;

      &:hover {
        transform: translateY(-5px);
      }

      h2 {
        color: #2c3e50;
        margin-top: 0;
      }

      p {
        color: #34495e;
        line-height: 1.6;
      }
    }
  }
}

@media only screen and (max-width: 600px) {
  .webp-advantages {
    margin-bottom: 15vh;
  }
}
</style>
