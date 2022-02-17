<template>
  <div class="wrapper">
    <div class="event-list">
      <h3>Draggable events</h3>
      <draggable
        class="list-group list1"
        :list="list1"
        :group="{ name: 'events', pull: 'clone', put: false }"
        :clone="cloneEvent"
        @change="log"
        :disabled="!enabled"
      >
        <div
          class="list1-group-item"
          v-for="element in list1"
          :key="element.name"
        >
          <p>{{ element.name }}</p>
        </div>
      </draggable>
    </div>

    <div class="calendar">
      <h1>January 2022</h1>
      
      <div class="squares">
        <li>Monday</li>
        <li>Tuesday</li>
        <li>Wednesday</li>
        <li>Thursday</li>
        <li>Friday</li>
        <li>Saturday</li>
        <li>Sunday</li>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
          <div class="square"></div>
      </div>
        <draggable class="list2" :list="list2" group="events" @change="log">
            <div
            class="list2-group-item"
            v-for="element in list2"
            :key="element.name"
            :move="checkMove"
            >
            {{ element.name }}
            </div>
        </draggable>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";
export default {
  name: "calendar",
  display: "Calendar",
  order: 2,
  components: {
    draggable,
  },

  data() {
    return {
      enabled: true,
      list1: [
        { name: "Event 1", id: 1 },
        { name: "Event 2", id: 2 },
        { name: "Event 3", id: 3 },
        { name: "Event 4", id: 4 },
        { name: "Event 5", id: 5 },
      ],
      list2: [
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        // { name: ""},
        
       
      ],
    };
  },
  methods: {
    log: function (e) {
      window.console.log(e);
    },
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  overflow: hidden;
}
.wrapper {
  width: 100vw;
  height: 100vh;
  display: grid;
  grid-template-columns: 1fr 3fr;
}

.event-list {
  border: solid 1px gray;
  padding: 1rem;
}

.calendar {
  border: solid 1px gray;
  padding: 1rem;
}

li {
  list-style: none;
  margin-bottom: 0.5rem;
}

.list1 {
    display: flex;
    flex-direction: column;
}

p {
    width: 5rem;
    background-color: rgb(108, 108, 194);
    padding: 0.2rem;
    border-radius: 10px;
}

.squares {
    display: grid;
    grid-template-rows: repeat(4, 1fr);
    grid-template-columns: repeat(7, 1fr);
    position: absolute;
    width: 70vw;
    height: 80vh;
    justify-items: center;
}

.list2 {
    display: grid;
    grid-template-rows: repeat(4, 1fr);
    grid-template-columns: repeat(7, 1fr);
    position: absolute;
    min-width: 70vw;
    min-height: 80vh;
    justify-items: center;
    padding-top: 1.8rem;
}

.square {
    border: 1px solid gray;
    width: 6rem;
    height: 6rem;
}

.list2-group-item {
    border: 1px solid gray;
    width: 6rem;
    height: 6rem;
}
</style>
