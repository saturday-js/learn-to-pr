<template>
  <section class="container">
    <div align="center" id="app">
      <h1 class="rev">{{msg}}</h1>
      <button id="show" v-on:click="showmore()">Show More</button>
      <div id="main">
        <h2>#Students : 5806021630151</h2>
        <h2>Nick Name : Flame </h2>
        <h2>Sec : IT-3RC</h2>

        <input type="text" placeholder="My Hobbies" v-model="newhobbie" v-on:keyup.enter="addhob()"> 
        <div v-for='a in hobbie'>
          {{a.hobbie}}
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Sillawat Leelas',
      hobbie: [
        {
          id: '1',
          hobbie: 'play game'
        }
      ],
      nexthob: 1
    }
  },
  components: {
  },
  methods: {
    showmore: function () {
      var x = document.getElementById('main')
      if (x.style.display === 'none') {
        x.style.display = 'block'
      } else {
        x.style.display = 'none'
      }
    },
    addhob: function () {
      this.hobbie.push({
        id: this.nexthob++,
        hobbie: this.newhobbie
      })
      this.newhobbie = ''
    }
  }
}
</script>

<style>
  input {
    width: 30%;
    height: 30px;
    border :2px solid black;
    text-align: center;
  }
  h1 {
    margin-bottom: 40px;
    font-size :72px;
  } 
  div {
    margin-top: 70px;
    color : black;
  }
  button {
    border: 2px solid black;
    background-color: white;
    width: 200px;
    height: 70px;
    font-size: 32px;
  }
  button:hover {
    border: 2px solid black;
    background-color: grey;
    width: 200px;
    height: 70px;
    font-size: 32px;
  }
  #main {
    display: none;
  }
  #show {
    display: block;
  }
</style>
