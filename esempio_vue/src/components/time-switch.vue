<template>
  <div id="app">
    <b-card-group>
      <b-card>
        <b-card-text v-for="stadio in stadi" :key="stadio">
        </b-card-text>
      </b-card>
    </b-card-group>  
    </div>
</template>
<script>
import json from './data.json'
export default { 
  data(){
    return{
        stadi:[
            {lasso:"Daily"},
            {lasso:"Weekly"},
            {lasso:"Monthly"}
        ],
      myJson: json,
      title:"titolo"
    }
  }
}
</script>

<style >    

</style>