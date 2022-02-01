<template>
  <div id="app">
    <b-container>
      <b-row>
        <b-col cols = 3>
          <b-card class="cartaNuova blue white muoviZ" :img-src="require('@/assets/image-jeremy.png')" img-alt="Card image" img-top> 
            <h4>Report for</h4>
            <h2>Jeremy</h2>
            <h2>Robson</h2>
          </b-card>
          <b-card class="card text-white ruota" id="cartaScelta">
            <ul>
              <li class="daily"><button v-on:click="mostraDaily">Daily</button></li>             
              <li class="weekly"><button v-on:click="mostraWeekly">Weekly</button></li>
              <li class="monthly"><button v-on:click="mostraMonthly">Monthly</button></li>
            </ul>
          </b-card>
        </b-col>
        <b-col cols = 9>
          <b-row>
            <b-col class="colonna " cols="4" v-for="(elem,index) in myJson" :key="elem.title">
              <div class="card noBorder" id="cartaGenerale"> 
                <b-card class="d-flex bd-highlight centrato" :style="'background-color: ' + listaColori[index]">
                  <div class="p-2 bd-highlight d-flex flex-row-reverse classeDiv">
                  <img :src="require('@/assets/'+elem.imgPath)">
                  </div>
                </b-card>
                <b-card class="carteTempo white muoviZ">
                  {{elem.title}}<br>
                  <h1>{{outputCurrent[index]}}hrs </h1><br>
                  Last Week - {{outputPrevious[index]}} hrs 
                </b-card>
              </div>
            </b-col>
          </b-row>
        </b-col>
      </b-row>
    </b-container>   
  </div>

</template>
<script>
import json from '@/data.json'
export default { 
  data(){
    return{
      myJson: json,
      outputCurrent: [],
      outputPrevious: [],
      listaColori : ['red','lightblue','magenta','green','purple','yellow']
    }
  },
  methods:{
    mostraDaily (){
      this.outputCurrent=[]
      this.outputPrevious=[]
      this.myJson.forEach(elem=>{
        this.outputCurrent.push(elem.timeframes.daily.current)
        this.outputPrevious.push(elem.timeframes.daily.previous)
        })
    },
    mostraWeekly (){
      this.outputCurrent=[]
      this.outputPrevious=[]
      this.myJson.forEach(elem=>{
        this.outputCurrent.push(elem.timeframes.weekly.current)
        this.outputPrevious.push(elem.timeframes.daily.previous)
        })
    },
    mostraMonthly (){
      this.outputCurrent=[]
      this.outputPrevious=[]
      this.myJson.forEach(elem=>{
        this.outputCurrent.push(elem.timeframes.monthly.current)
        this.outputPrevious.push(elem.timeframes.daily.previous)
        })
    }
  }
}
</script>

<style scoped>  
.cartaNuova .card-img-top {
    width: 40%;
    object-fit: contain;
}
.cartaNuova{
  padding-left:20px;
  padding-top:10px;
  border-radius: 20px !important;
}

.card-body{
  padding-top: 1rem !important;
  border-radius: 20px !important;
}

img{
  object-fit: cover;
}
#cartaGenerale .card.d-flex.bd-highlight{
  height:60px;
  justify-content: center;
  border-radius: 15px !important;

}
.carteTempo{
  background-color:blueviolet;
  transform: translateY(-20px);
  border-radius: 15px !important;
}
.white{
  color:white
}
.blue{
  background-color:blue
}
h4{
  font-size: 15px;
  color:lightgrey
}
button{
border: 0;
 background: none;
 box-shadow: none;
 color:white;
}
.colonna{
  overflow:hidden 
}
.muoviZ{
  z-index:100;
}
#cartaScelta{
  background-color:blueviolet;
  transform: translateY(-20px);
  border-radius: 15px !important;
}
.noBorder{
  border: 0 !important; 
}
</style>