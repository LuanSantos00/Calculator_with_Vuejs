<template>
  <div id="app">

    <h3>Calculadora utilizando Vue.js</h3>

  <input class="input" v-model="exp" type="text"><br>

<div style="padding:10px">
<div style="display:block;">
<button class="btnStyle"  @click="adicionar(7)">7</button>
<button class="btnStyle" @click="adicionar(8)">8</button>
<button class="btnStyle" @click="adicionar(9)">9</button>
<button class="btnStyle" @click="adicionar('/')">/</button>
</div><br>
<div style="display:block">
<button class="btnStyle" @click="adicionar(4)">4</button>
<button class="btnStyle" @click="adicionar(5)">5</button>
<button class="btnStyle" @click="adicionar(6)">6</button>
<button class="btnStyle" @click="adicionar('*')">*</button>
</div><br>
<div style="display:block">
<button class="btnStyle" @click="adicionar(1)">1</button>
<button class="btnStyle" @click="adicionar(2)">2</button>
<button class="btnStyle" @click="adicionar(3)">3</button>
<button class="btnStyle" @click="adicionar('-')">-</button>
</div><br>
<div style="display:block">
<button class="btnStyle" style="margin-left: 50px;" @click="adicionar(0)">0</button>
<button class="btnStyle" @click="adicionar('.')">.</button>
<button class="btnStyle" @click="adicionar('+')">+</button>
<button class="btnStyle" @click="resolver">=</button>
<button class="btnStyle" @click="limpar">CE</button>
</div><br>
</div>
</div>
</template>

<script>
export default {
  name: 'Calculadora',
  data(){
      return {
          exp: ''
      }
  },
  methods: {
    adicionar: function(value){
      this.exp += value
    },
    resolver: function(){
      let op = this.exp;
      let res = eval(op);
      
      this.exp = res;
    },
    limpar: function (){
      this.exp = '';
    }
  }
}
</script>

<style>
.btnStyle{
    padding: 10px;
    border: 0.4px;
    cursor: pointer;
    margin-left: 5px;
    box-shadow: 2px 2px #888888;
}

.input {
    padding: 5px;
    box-shadow: 2px 2px #888888;
}
</style>