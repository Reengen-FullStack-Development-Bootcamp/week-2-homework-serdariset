<template>
  <div>
    <div
      :class="[
        'bottom-boxes',
        'comment-container',
      ]"
    >
      <div
        class="comment"
        v-for="(comment, index) in comments"
        :key="'comment' + index"
      >
        <span class="client"><i class="fas fa-user"></i></span>
        <span class="description">
          <h3 class="client-name">{{ comment.name }}</h3>
          <p class="comment-text">
            {{ comment.description }}
          </p>
          <span
            class="client-rating"
            :class="
              comment.rate > 9
                ? 'green'
                : comment.rate < 9 && comment.rate > 8
                ? 'yellow'
                : 'red'
            "
            >{{ comment.rate }}</span
          >
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:'CardComment',
  props:{
    hotelId:Number,
    comments:Array
  }
};
</script>

<style>
.comment-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  width: 100%;
  padding: 1rem;
}
.comment {
  display: flex;
  width: 48%;
  height: 85px;
  background-color: white;
  border-radius: 10px;
}
.client {
  width: 85px;
  height: 85px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  color: #455a64;
  background-color: #90a4ae;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
}
.description {
  display: flex;
  flex-direction: column;
  width: calc(100% - 85px);
  padding: 0.3rem;
  position: relative;
  overflow: hidden;
}

.client-rating {
  position: absolute;
  width: 80px;
  height: 20px;
  background-color: green;
  top: 5px;
  right: -26px;
  display: flex;
  justify-content: center;
  transform: rotate(45deg);
  align-items: center;
  color: white;
  font-family: "Poppins", sans-serif;
}
.comment-text {
  font-family: "Poppins", sans-serif;
  font-size: 12px;
  margin-left: 0.5rem;
}

</style>