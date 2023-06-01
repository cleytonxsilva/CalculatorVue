<template>
  <div class="calculator">
    <h1>{{ msg }}</h1>
    <div class="col-md4-4 m-3">
    <table class="table table-bordered">
      <tbody>
        <tr>
          <td colspan="4">{{output || 0}}</td>
        </tr>
        <tr>
          <td v-on:click="clearField">C</td>
          <td>+/-</td>
          <td v-on:click="calculatePercentage">%</td>
          <td class="right-column">/</td>
        </tr>
        <tr>
          <td>7</td>
          <td>8</td>
          <td>9</td>
          <td class="right-column">x</td>
        </tr>
        <tr>
          <td>4</td>
          <td>5</td>
          <td>6</td>
          <td class="right-column">-</td>
        </tr>
        <tr>
          <td>1</td>
          <td>2</td>
          <td>3</td>
          <td class="right-column">+</td>
        </tr>
        <tr>
          <td colspan="2">0</td>
          <td>.</td>
          <td class="right-column">=</td>
        </tr>
      </tbody>
    </table>
  </div>
  </div>
</template>

<script>
export default {
  name: 'CalculadoraComponent',
  props: {
    msg: String 
  },
  data(){
    return{
      output:'0',
      previousValue: null,
      operationFired: false
    }
  },
  methods:{
    clearField(){
      this.output = '0'
    },
    calculatePercentage(){
       this.output = parseFloat(this.output)/100;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.right-column{
  background-color: blueviolet;
  color: blue;
}
td:active{
  background-color: #42b983;
}

</style>
