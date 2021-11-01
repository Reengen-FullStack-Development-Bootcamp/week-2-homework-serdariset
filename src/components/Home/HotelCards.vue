<template>
  <div style="main-container">
    <div v-for="(item, index) in data" :key="'data' + index">
      <div class="card-container" :id="`cardContainer${item.hotelID}`">
        <div class="top-side">
          <ImageBox :images="item.photos[0]" />
          <div class="property-box">
            <HotelName :hotelName="item.hotelName" />
            <Stars :rating="item.rating" :location="item.location" />

            
          </div>
          <div class="price-box">
            <button class="go-hotel-page">
              <router-link :to="`/hotel/${item.hotelID}`"
                ><i class="fas fa-angle-right"></i
              ></router-link>
            </button>
          </div>
        </div>
    
      </div>
    </div>
  </div>
</template>

<script>
import json from "@/assets/data/Hotels.json";
import Stars from "@/components/Home/Stars.vue";
import ImageBox from "@/components/Home/ImageBox.vue";
import HotelName from "@/components/Home/HotelName.vue";

export default {
  name: "HotelCards",
  components: {
    Stars,
    ImageBox,
    HotelName,
 
  },
  data() {
    return {
      data: json,
     
    };
  },

  
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500&display=swap");

.card-container {
  width: 1180px;
  height: 300px;
  border-radius: 10px;
  background-color: #e0e0e0be;
  box-shadow: 1px 2px 14px -1px rgba(0, 0, 0, 0.59);
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-bottom: 2rem;
}

.top-side {
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}






.property-box {
  width: 500px;
  height: calc(300px - 2rem);
  padding: 1rem 0;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}


.price-box {
  width: 300px;
  height: calc(300px - 2rem);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding-right: 1rem;
}
.go-hotel-page {
  width: 70px;
  height: 70px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Poppins", sans-serif;
  text-decoration: none;
  background-color: #03a9f4;
  outline: none;
  border: none;
  border-radius: 10px;
  color: white;
  font-size: 1.2rem;
}
.client-name {
  font-family: "Poppins", sans-serif;
  font-size: 16px;
  margin-left: 0.5rem;
  color: #616161;
}
.green {
  background-color: green;
}
.red {
  background-color: red;
}
.yellow {
  background-color: orange;
}



</style>