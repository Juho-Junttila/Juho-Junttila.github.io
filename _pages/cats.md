---
layout: archive
title: ""
permalink: /cats/
author_profile: false
redirect_from:
  - /cats
---

<style>
.cat-page-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 40px 20px;
}

.cat-page-container h1 {
  text-align: center;
  font-size: 2.5em;
  margin-bottom: 40px;
  color: #494e52;
}

.cat-gallery {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  margin-top: 20px;
}

.cat-gallery img {
  width: 100%;
  height: 400px;
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: transform 0.3s ease;
}

.cat-gallery img:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
}
</style>

<div class="cat-page-container">
  <div class="cat-gallery">
  <img src='/images/kissat1.jpeg' alt='Cat photo 1'>
  <img src='/images/kissat2.jpeg' alt='Cat photo 2'>
  <img src='/images/kissat4.jpeg' alt='Cat photo 4'>
  <img src='/images/kissat5.JPG' alt='Cat photo 5'>
  <img src='/images/kissat6.jpeg' alt='Cat photo 6'>
  <img src='/images/kissat7.jpeg' alt='Cat photo 7'>
  </div>
</div>

<!--
To add new cat photos:
1. Add your image to the /images/ folder
2. Copy one of the lines above and update the filename:
   <img src='/images/your-new-photo.jpg' alt='Description'>
-->
