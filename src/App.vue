<script>
import StartBox from './components/StartBox.vue'
import ClickBox from './components/ClickBox.vue'

export default{
    components: { StartBox ,ClickBox},
    
    data() {
        return {
            counter: 0,
            show: true,
            inputTime: "",
            sec: "секунд"
        };
    },
    methods: {
        times() {
            return this.inputTime * 1000;
        },
        clicker() {
            this.show = false;
            setTimeout(() => {
                this.show = true;
            }, this.times());
            this.counter = 0;
        }
    },
   
}
</script>

<template>
  <h1>игра быстрые пальцы кликер</h1>
  <input v-model="inputTime" @click="inputTime = ''" type="text" placeholder="выберите секунды"/>
  <button @click="times">установить время</button>
  <StartBox :clicker="clicker" v-if="show"/>
  <ClickBox @counterEmmet="counter++" :counter="counter" v-else />
  <h2>результат :{{ counter }} кликов за {{ inputTime }} {{ sec }}</h2>
</template>


<style>
.box{
  margin-top: 20px;
  width: 150px;
  height: 30px;
  background-color: red;
}
.box1{
  margin-top: 20px;
  margin-left: 160px;
  width: 100px;
  height: 30px;
  background-color: green;
}
</style>
