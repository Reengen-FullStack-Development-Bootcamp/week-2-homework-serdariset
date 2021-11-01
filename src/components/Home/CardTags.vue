<template>

      <div class="bottom-tag" :id="cardName+hotelId" @click="showContent()"> {{cardName}} </div>

</template>

<script>
export default {
    name:'CardTags',
    props:{
        cardName: String,
        hotelId:Number
    },
    methods:{
      showContent(){
        this.$emit('show-content',this.cardName+this.hotelId)
      }
    }
}
</script>

<style>
.bottom-tag {
  width: 33%;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Poppins", sans-serif;
  cursor: pointer;
  transition: all 0.4s ease;
  color: #616161;
  border-bottom: 3px solid transparent;
}
.bottom-tag:hover {
  color: #03a9f4;
}
</style>