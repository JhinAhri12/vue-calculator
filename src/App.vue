<script setup>
//import HelloWorld from './components/HelloWorld.vue'
//import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
<div class="container">
  <div class="row text-center">
    <form @submit.prevent="myResult">

      <div class="col-4 offset-4 alert alert-secondary mt-2">
        <p>{{query}} = {{result}}</p>
      </div>

      <div class="d-flex ">
        <div class="col-1 offset-4 d-grid gap-1">
          <button @click.prevent="reset" class="btn btn-secondary btn-lg m-1">C</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="number" class="btn btn-secondary btn-lg m-1">+/-</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="modulo" class="btn btn-secondary btn-lg m-1">%</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="divide" class="btn btn-success btn-lg m-1">/</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-1 offset-4 d-grid gap-1">
          <button @click.prevent="seven" class="btn btn-secondary btn-lg m-1">7</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="eigth" class="btn btn-secondary btn-lg m-1">8</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="nine" class="btn btn-secondary btn-lg m-1">9</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="multiply" class="btn btn-success btn-lg m-1">*</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-1 offset-4 d-grid gap-1">
          <button @click.prevent="four" class="btn btn-secondary btn-lg m-1">4</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="five" class="btn btn-secondary btn-lg m-1">5</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="six" class="btn btn-secondary btn-lg m-1">6</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="minus" class="btn btn-success btn-lg m-1">-</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-1 offset-4 d-grid gap-1">
          <button @click.prevent="one" class="btn btn-secondary btn-lg m-1">1</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="two" class="btn btn-secondary btn-lg m-1">2</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="three" class="btn btn-secondary btn-lg m-1">3</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="add" class="btn btn-success btn-lg m-1">+</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-2 offset-4 d-grid gap-2">
          <button @click.prevent="zero" class="btn btn-secondary btn-lg m-1">0</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button @click.prevent="dot" class="btn btn-secondary btn-lg m-1">.</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <input type="submit" class="btn btn-success btn-lg m-1" value="=">
        </div>
      </div>
      <br> 
    </form>
  </div>
</div>

  <hr>

  <ul>
    <li v-for="item in calculations">{{item.query}} = {{item.result}} at {{item.time}}</li>
  </ul>
</template>

<style scoped>
</style>

<script>
export default {
  name: "App",
  data(){
    return {
      query : '',
      result : '',
      calculations : []
    }
  },
  methods : {
    add(){
      this.query += "+"
    },
    zero(){
      this.query += "0"
    },
    one(){
      this.query += "1"
    },
    two(){
      this.query += "2"
    },
    three(){
      this.query += "3"
    },
    four(){
      this.query += "4"
    },
    five(){
      this.query += "5"
    },
    six()
    {
      this.query += "6"
    },
    seven(){ 
      this.query += "7"
    },
    eight(){
      this.query += "8"
    },
    nine(){
      this.query += "9"
    },
    reset() {
      this.query = '',
      this.calculations = [],
      this.result = ''
    },
    divide() {
      this.query += '/'
    },
    multiply(){
      this.query += '*'
    },
    modulo(){
      this.query += '%'
    },
    dot(){
      this.query += '.'
    },
    number(){
      this.query += '-'
    },
    myResult() {
      this.result = eval(this.query)
      this.calculations.push({
        "query" : this.query,
        "result" : this.result,
        "time" : Date().toString()
      })
    }
  }
};
</script>