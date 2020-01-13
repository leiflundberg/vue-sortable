<template>
  <div class="hello">
    <h1>Sensorer</h1>

    <draggable v-model="myArray" ghost-class="ghost" @end="onEnd">
      <transition-group type="transition" name="flip-list">
        <div class="sortable" :id="element.id" v-for="element in myArray" :key="element.id">
          <h3>{{ element.name }}</h3>
          <span id="span">{{ element.id }}</span>
        </div>
      </transition-group>
    </draggable>

    <p><strong>Siste indexposisjon: </strong> {{ oldIndex }}</p>
    <p><strong>Ny indexposisjon: </strong> {{ newIndex }}</p><br>
    <h4>Sensor i indexposisjon 0: </h4>
    <p>{{ myArray[0].name }}</p>
  </div>
</template>

<script>
import draggable from 'vuedraggable'

export default {
  name: 'HelloWorld',
  components: {
    draggable
  },
  props: {
    msg: String
  },
  data() {
    return {
      myArray:[
        { name: "Potet", id:0 },
        { name: "Irrigation", id:1 },
        { name: "Slushmaskin", id:2 },
        { name: "Relativ luftfuktighet", id:3 },
        { name: "Bikube", id:4 },
        { name: "Bygg", id:5 },
      ],
      index: '',
      oldIndex: '',
      newIndex: ''
    }
  },
  methods: {
    showIndex() {
      console.log('works');
    },
    onEnd: function(evt) {
      console.log(evt)
      this.oldIndex = evt.oldIndex;
      this.newIndex = evt.newIndex;
    }
  },
  beforeMount(){
    this.showIndex();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  display: inline-block;
}

strong {
  display: inline-block;
}

.sortable {
  width: 100%; 
  background: white; 
  padding: 1em;
  cursor: move; 
  margin-bottom: 10px;
}

#span {
    float: right; 
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
