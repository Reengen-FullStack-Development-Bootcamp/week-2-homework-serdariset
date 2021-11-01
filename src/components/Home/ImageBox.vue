<template>
  <div>
      <div class="image-box">
            <img
              :src="require(`@/assets/images/${images}`)"
              alt=""
              class="hotel-mini-image"
            />
          </div>
  </div>
</template>

<script>
export default {
    name:"ImageBox",
    props:{
        images:String
    }
}
</script>

<style>
.image-box {
  width: calc(300px - 2rem);
  height: calc(300px - 2rem);
  border-radius: 10px;
  overflow: hidden;
  position: relative;
}
.hotel-mini-image {
  max-height: 100%;
  transform: scale(1);
  transition: 0.7s ease;
}
.hotel-mini-image:hover {
  transform: scale(1.15);
}
</style>