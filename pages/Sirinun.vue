<template>
<section class="container">
<form>
  <div id="show-blogs">
    <div class="single-blog">
      <center><h1> SIRINUN </h1></center>
    </div>
      <div class="single-blog">
        <label>How're U </label>
        <input type="text" v-model="newmsg"/>
        <button @click="aaa" >SUB</button>
      </div>

      <div class="single-blog"v-for="a in msg">
        <h2 >{{a.text}}</h2>
      </div>
  </div>

</form>
</section>
</template>
<script>
export default {
  components: {
  },
  data () {
    return {
      msg: [
        {
          id: 1,
          text: 'EiEi'
        }
      ],
      nextid: 2,
      newmsg: ''
    }
  },
  methods: {
    aaa: function () {
      this.msg.push({
        id: this.nextid++,
        text: this.newmsg
      })
      this.newmsg = ''
    }
  }
}
</script>

<style>
#show-blogs{
    max-width: 800px;
    margin: 0px auto;
    background-color: #ddd;

}
.single-blog{
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
}
</style>
