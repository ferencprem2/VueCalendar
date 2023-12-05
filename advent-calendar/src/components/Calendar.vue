<script >
import messages from '../assets/messages.json'

export default {
  data() {
    return {
      days: []
    };
  },
  methods: {
    fillDays() {
      for (let i = 1; i < 24; i++) {
        var currentId = `id${i}`
        this.days.push({text: messages[currentId].text, opened: false })
      }
    },
    openBox(){
      
    }
  },
  mounted: function() {
    this.fillDays()
  },
}
var parent = document.getElementsByClassName("calendarBox")[0]

</script>

<template>
  <div class="calendarBox">
    <div id="day" v-for="day in days" @click="day.opened = !day.opened">
      <h1 v-if="opened">{{ day.text }}</h1>
    </div>
  </div>
</template>

<style>
  #app{
  margin: 0;
  padding: 0;
  }

  .calendarBox{
    height: 100vh;
    width: 100vw;
    background-color: green;
    display: grid;
    gap: 25px;
    padding: 10px;
    grid-template-columns: repeat(7, 1fr);
    box-sizing: border-box;
  }

  #day{
    width: 100%;
    height: 200px;
    background-color: red;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid rgb(15, 66, 18);
    border-radius: 5px;
  }


  @media only screen and (max-width: 992px){
    .calendarBox{
      grid-template-columns: repeat(3, 1fr);
    }
  }

</style>
