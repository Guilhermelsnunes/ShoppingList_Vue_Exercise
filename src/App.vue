<template>
  <div id="app">
    <h1>{{ greeting }}</h1>
    <button v-on:click="updateGreeting">Change Greeting</button>
    <ul>
      <!-- <li v-for="(item, index) in items" :key="index">{{ item }}</li> -->
      <li v-for="(item, index) in items" :key="index">
        <span> {{ item.name}} </span>
        <span v-if="item.isPurchased">Purchased!</span>
      </li>
    </ul>
    <form v-on:submit.prevent="saveNewItem">
      <label for="nem-item">Add a new Item:</label>
      <input type="test" id="new-item" v-model="newItem"/>
      <input type="submit" value="Save New Item"/>
    </form>


  </div>
</template>





<script>

export default {
  name: 'App',
  data() {
    return{
      greeting: "Hello World",
      // items : ["Milk", "Cheese", "Beans"],

      items:[
        {name:"Milk", isPurchased: true },
        {name:"Cheese", isPurchased: false },
        {name:"Beans", isPurchased: true },
      ],
      newItem: "",
    };
  },
  methods : {
    updateGreeting : function(){
      this.greeting = "Changed!";
    },
    saveNewItem: function(){
      // this.items.push(this.newItem)
            this.items.push({name:this.newItem, isPurchased: false});
      this.newItem = "";
    }
  },
  components: {},
};

</script>






<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
