<template>
  <div>
      <div
              :class="[
                'bottom-boxes',
                `bottom-boxes${hotelID}`,
              ]"
            >
              <span
                class="mini-images"
                v-for="(image, index) in photos"
                :key="index"
              >
                <img
                  :src="require(`@/assets/images/${image}`)"
                  :alt="'image' + index"
                  class="mini-image"
                />
              </span>
            </div>
  </div>
</template>

<script>
export default {
    name:'CardPhotos',
    props:{
        hotelID:Number,
        photos:Array
    }
}   
</script>

<style>
.photos-container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 220px;
  padding: 1rem;
  width: 100%;
}
.mini-images {
  width: 185px;
  height: 150px;
  background-color: green;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
.mini-image {
  max-height: 100%;
  transform: scale(1);
  transition: 0.3s ease;
}
.mini-image:hover {
  transform: scale(1.25);
}
</style>