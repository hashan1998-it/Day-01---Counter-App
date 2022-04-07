<template>
  <div class="wrapper d-flex justify-content-center align-items-center">
    <div class="counter-container">
      <h1>Counter App</h1>
      <span class="count" :style="[{color:statusOfColor[flag]}]">{{ count }}</span>
      <hr>
      <div class="buttons d-flex-sm flex-column-sm">
        <AppButton @onClick="subtract" color="#fff" width=" 110px" backgroundColor="red" fontWeight="600">SUBTRACT</AppButton>
        <AppButton @onClick="reset" color="black"  width="110px" backgroundColor="#fff" fontWeight="600">RESET</AppButton>
        <AppButton @onClick="add"  width="110px" backgroundColor="green" fontWeight="600">ADD</AppButton>
      </div>
    </div>
  </div>
</template>

<script> 
import AppButton from '@/components/UI/AppButton.vue'
export default {
  name: 'IndexPage',
  components:{
    AppButton
  },
  data(){
    return{
      count: 0,
      flag:'',
      statusOfColor:['green','red','#fff']
    }
  },
  methods:{
    add(){
      this.count +=1
      this.flag = 0
  
    },
    subtract(){
      this.count -= 1
      this.flag = 1
    },
    reset(){
      this.count =0
      this.flag = 2
    }

  },
 
}
</script>

<style scoped>
html{
   background-color: #f9e7e8;
}
.wrapper{
  max-width: 900px;
  margin: 0 auto;
  padding: 0 20px;
  height: 100vh;
  color: #fff;
 
}

.counter-container{
  background-color: #20ad65;
  width: 40rem;
  text-align: center;
  padding: 1rem;
  border: 1px #eee solid;
  border-radius: 5px;
  
}
h1{
  color: rgb(221, 221, 28);
}

.counter-container > *{
  margin-bottom: 2rem;
}

.count{
  font-size: 4rem;
}

hr{
  background-color: #fff;
  height: 0.1rem;
}

@media only screen and (max-width: 450px){
  .buttons{
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  button{
    margin-bottom: 10px;
  }
}
</style>
