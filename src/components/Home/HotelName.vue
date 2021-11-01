<template>
  <div>
    <div>
      <h2 class="hotel-name">{{ hotelName }}</h2>
    </div>
  </div>
</template>

<script>
export default {
    name:'HotelName',
    props:{
        hotelName:String
    }
};
</script>

<style>

.hotel-name {
  font-family: "Poppins", sans-serif;
  color: #616161;
}
</style>