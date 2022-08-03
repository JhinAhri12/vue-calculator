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
          <button class="btn btn-secondary btn-lg m-1">C</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">+/-</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">%</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-success btn-lg m-1">+</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-1 offset-4 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">7</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">8</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">9</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-success btn-lg m-1">*</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-1 offset-4 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">4</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">5</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">6</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-success btn-lg m-1">-</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-1 offset-4 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">1</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">2</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">3</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-success btn-lg m-1">+</button>
        </div>
      </div>
      <div class="d-flex ">
        <div class="col-2 offset-4 d-grid gap-2">
          <button class="btn btn-secondary btn-lg m-1">0</button>
        </div>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-secondary btn-lg m-1">.</button>
        </div><br>
        <div class="col-1 d-grid gap-1">
          <button class="btn btn-success btn-lg m-1">=</button>
        </div>
      </div>
      <br>
      
      <input type="text" v-model="query">
      <input type="submit" value="=">
      
 
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