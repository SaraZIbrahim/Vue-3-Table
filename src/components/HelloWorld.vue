<template>
  <div id="table-demo" class="container">
    <h3 class="p-3 text-center">Vue 3 - Display a list of items with v-for</h3>
    <table>
      <tr v-for="(row, x) in users" :key="x" :class="{ bold: x === 0 }">
        <td
          v-for="(col, y) in row"
          :key="y"
          :data-th="users[0][y].value"
          @click="rowClicked(users, x, y)"
        >
          {{ users[x][y].value }}
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "App",
  setup() {
    // make users variable reactive with the ref() function
    const users = ref([
      [
        { value: "Fruit" },
        { value: "Vegetable" },
        { value: "Snacks" },
        { value: "Drinks" },
      ],
      [
        { value: "Apple" },
        { value: "Celery" },
        { value: "Chips" },
        { value: "Beer" },
      ],
      [
        { value: "Banana" },
        { value: "Eggplant" },
        { value: "Candy" },
        { value: "Coke" },
      ],
      [
        { value: "Oranges" },
        { value: "Squash" },
        { value: "Nuts" },
        { value: "Tea" },
      ],
    ]);

    return {
      users,
    };
  },
  methods: {
    rowClicked(user, x, y) {
      console.log(user[x][y].value + " is " + user[0][y].value);
    },
  },
};
</script>
