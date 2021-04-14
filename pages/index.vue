<template>
  <div class="container">
    <div class="content-wrap">
      <NewLogo id="logo"/>
      <h1 class="title">
        Useless Knowledge 
      </h1>
      <h2>Today we are the {{displayDate(today)}} and the sentence of the moment is : </h2>
      <div class="frame" @click="copyText()">
        <span v-if="seen">Copy !</span>
        <h3  >{{sentence}}</h3>
      </div>
      <button @click="update()">Reroll a new sentence</button>
    </div>
    <Footer/>
  </div>
</template>

<script>
import axios from"axios";
import "../styles/index.css"
import "@/styles/app.css"
export default {
  data(){
    return{ sentence:"Hello World ! Do not press too fast 🥴",
    today : new Date(),
    seen:false
    }
  }, mounted(){
    axios.get("https://uselessfacts.jsph.pl/random.json?language=en").then(response => this.sentence =response.data.text)
  },
  methods:{
   displayDate(date){
  const dayNumber = date.getDate();
  const day = date.getDay(); // number between 0 and 6
  const month = date.getMonth(); // number between 0 and 11
  const year = date.getFullYear();

  let dayName;
  let monthName;

  switch (day) {
    case 0:
      dayName = "Sunday";
      break;
    case 1:
      dayName = "Monday";
      break;
    case 2:
      dayName = "Tuesday";
      break;
    case 3:
      dayName = "Wednesday";
      break;
    case 4:
      dayName = "Thurdsday";
      break;
    case 5:
      dayName = "Friday";
      break;
    case 6:
      dayName = "Saturday";
      break;
  }

  switch (month) {
    case 0:
      monthName = "January";
      break;
    case 1:
      monthName = "February";
      break;
    case 2:
      monthName = "March";
      break;
    case 3:
      monthName = "April";
      break;
    case 4:
      monthName = "May";
      break;
    case 5:
      monthName = "June";
      break;
    case 6:
      monthName = "July";
      break;
    case 7:
      monthName = "August";
      break;
    case 8:
      monthName = "September";
      break;
    case 9:
      monthName = "October";
      break;
    case 10:
      monthName = "November";
      break;
    case 11:
      monthName = "December";
      break;
      }
const sentence = dayName +" "+ dayNumber +" of "+monthName + ", "+year
  return sentence;
    },
    update(){
          axios.get("https://uselessfacts.jsph.pl/random.json?language=en").then(response => this.sentence =response.data.text)

    },
    copyText () {
         navigator.clipboard.writeText(this.sentence);
         this.seen=true;
         setTimeout(() => this.seen = false, 2000)
        }
        
  }
}
</script>

