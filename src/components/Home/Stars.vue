<template>
  <div>
       <div class="location-rating-box">
              <div class="rating-box">
                <span
                  v-for="star in rating"
                  :key="'checkedStar' + star"
                  class="fa fa-star checked"
                >
                </span>
                <span
                  class="fa fa-star"
                  v-for="star in 5 - rating"
                  :key="'start' + star"
                >
                </span>
              </div>
              <span class="vertical"></span>
              <div class="location-box">
                <i class="fas fa-map-marker-alt"></i>
                <span class="location">{{ location }}</span>
              </div>
            </div>
  </div>
</template>

<script>
export default {
    name:'Stars',
    props:{
        rating:Number,
        location:String
    }

}
</script>

<style>
.location-rating-box {
  display: flex;
  margin: 1rem 0;
  width: 500px;
  align-items: center;
  height: 40px;
}
.vertical {
  width: 5px;
  height: 20px;
  background-color: #bdbdbd;
  border-radius: 10px;
  margin: 0 1rem;
}
.location {
  font-family: "Poppins", sans-serif;
  margin-left: 0.5rem;
  color: #616161;
}
.fa-map-marker-alt {
  color: #616161;
  font-size: 17px;
}
.checked {
  color: orange;
}
</style>