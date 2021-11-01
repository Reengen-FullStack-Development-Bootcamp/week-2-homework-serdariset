<template>
  <div>
    <div class="comments" @click="sendID()">
      <div class="card-button">
       <span> {{ cardName.commentName }}<i :class="cardIcon.commentIcon"></i></span>
       <span> {{ cardName.serviceName }}<i :class="cardIcon.serviceIcon"></i></span>
       <span> {{ cardName.photosName }}<i :class="cardIcon.photosIcon"></i></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardButtons",
  props: {
    cardIcon: Object,
    cardName: Object,
    hotelId: Number
  },
  data(){
    return{
      showBottom:0
    }
  },
  methods:{
    sendID(){
      if(this.showBottom == 0){
        this.showBottom = 1
      }else{
        this.showBottom = 0
      }

      /* let buttonID = this.cardName+this.hotelId */
      this.$emit('button-id',[this.showBottom,this.hotelId])
    }
  }
};
</script>

<style>
.service-box {
  width: 500px;
  display: flex;
  height: 130px;
  align-items: flex-end;
  justify-content: flex-start;
}
.card-button {
  display: flex;
  align-items: center;
  width: 360px;
  height: 50px;
  background-color: #cfd8dc;
  padding: 0.3rem;
  justify-content: space-around;
  border-radius: 10px;
  font-family: "Poppins", sans-serif;
  font-size: 12px;
  color: #757575;
  margin-right: 1rem;
  cursor: pointer;
  transition: 0.4s ease;
  border: 2px solid transparent;
  text-transform: capitalize;
}
.card-button span{
  display: flex;
  flex-direction: column;
  align-items: center;
}
.card-button:hover {
  border: 2px solid #1e88e5;
  color: #03a9f4;
}
</style>