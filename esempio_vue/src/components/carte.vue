<template>
  <div id="app">
    <b-container>
              <!-- <b-card           
                :img-src="require('@/assets/icon-work.svg')"
                title="title"
                img-top
                img-width="200"
                img-height="200"
              >
              </b-card> -->
      <b-row>
        <b-col cols = 4>
          <b-card class="card text-white bg-info" :img-src="require('@/assets/image-jeremy.png')" img-alt="Card image" img-top> 
            <h3>Report for</h3>
            <h1>Jeremy</h1>
            <h1>Robson</h1>
          </b-card>
        </b-col>
        <b-col cols = 8>
          <b-row>
            <b-col cols="4" v-for="elem in myJson" :key="elem.title">
              <!-- <b-card           
                :img-src="require('@/assets/'+elem.imgPath)"
                img-top
                img-width="200"
                img-height="200"
              >
              <b-card-text>
                {{elem.timeframes["weekly"]}}
              </b-card-text>
              </b-card> -->
              <div class="card h-40"> 
                <b-card :img-src="require('@/assets/'+elem.imgPath)">
                </b-card>
              </div>
              <div class="card h-60"><p>fomfpomf</p></div>
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
    }
  }
}
</script>

<style>  
h3{
  font-size:20px;
}  

</style>