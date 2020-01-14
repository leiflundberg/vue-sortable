<template>
  <div class="row">
    <div class="col-3">
      <h3>Favoritter</h3>
      <draggable class="list-group" :list="list1" group="people">
        <div
          class="list-group-item"
          v-for="(element, index) in list1"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>
    <div class="col-3">
      <h3>Sensorer</h3>
      <draggable class="list-group" :list="list2" group="people">
        <div
          class="list-group-item"
          v-for="(element, index) in list2"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>
    <div class="col-3">
      <h3>Mindre viktige</h3>
      <draggable class="list-group" :list="list3" group="people">
        <div
          class="list-group-item"
          v-for="(element, index) in list3"
          :key="element.name"
        >
          {{ element.name }} {{ index }}
        </div>
      </draggable>
    </div>
  </div>
</template>
<script>
import draggable from "vuedraggable";

export default {
  name: "two-lists",
  display: "Two Lists",
  order: 1,
  components: {
    draggable
  },
  data() {
    return {
      list1: [
        { name: "Potet", id: 1 },
        { name: "Irigation", id: 2 },
        { name: "Slushmaskin", id: 3 },
      ],
      list2: [
        { name: "WiFi-sender", id: 5 },
        { name: "Overvannsensor", id: 6 },
        { name: "Trefukt", id: 7 }
      ],
      list3: [
        
      ]
    };
  }
};
</script>