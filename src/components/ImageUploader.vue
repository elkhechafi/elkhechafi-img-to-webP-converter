<template>
    <div class="image-uploader">
      <div
        class="upload-area"
        @dragover.prevent
        @drop.prevent="handleDrop"
        @click="triggerFileInput"
      >
        <p v-if="!image">Drag & Drop or Click to Browse</p>
        <img v-if="image" :src="image" alt="Uploaded Image" />
      </div>
      <input
        type="file"
        ref="fileInput"
        class="file-input"
        @change="handleFileSelect"
        accept="image/*"
        hidden
      />
      <button v-if="image" @click="downloadWebP">Download WebP</button>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import imageCompression from 'browser-image-compression';
  
  const image = ref(null);
  const webpImage = ref(null);
  
  const fileInput = ref(null);
  
  const handleDrop = async (event) => {
    const file = event.dataTransfer.files[0];
    if (file) {
      await processImage(file);
    }
  };
  
  const triggerFileInput = () => {
    fileInput.value.click();
  };
  
  const handleFileSelect = async (event) => {
    const file = event.target.files[0];
    if (file) {
      await processImage(file);
    }
  };
  
  const processImage = async (file) => {
    try {
      const options = {
        fileType: 'image/webp',
      };
      webpImage.value = await imageCompression(file, options);
      image.value = URL.createObjectURL(webpImage.value);
    } catch (error) {
      console.error('Image processing failed:', error);
    }
  };
  
  const downloadWebP = () => {
    const link = document.createElement('a');
    link.href = image.value;
    link.download = 'image.webp';
    link.click();
  };
  </script>
  
  <style scoped>
  .image-uploader {
    display: flex;
    flex-direction: column;
    align-items: center;
    border: 2px dashed #ccc;
    padding: 20px;
    cursor: pointer;
    position: relative;
  }
  
  .upload-area {
    width: 300px;
    height: 300px;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 2px dashed #ccc;
    background-color: var(--card-bg);
  }
  
  .upload-area p {
    margin: 0;
    color: var(--bg-color-reverse);
  }
  
  .upload-area img {
    max-width: 100%;
    max-height: 100%;
  }
  
  .file-input {
    display: none;
  }
  
  button {
    margin-top: 20px;
  }
  </style>
  