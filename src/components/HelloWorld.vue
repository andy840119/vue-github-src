<template>
  <div>
    <ul>
      <li v-for="(item, index) in todos" :key="index">
        {{ item.id }} : {{ item.title }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

const url = 'https://jsonplaceholder.typicode.com/todos';

const data = () => ({
  todos: [],
});

const mounted = function() {
  axios.get(url)
    .then(res => this.todos = res.data.slice(0, 3));
};

export default {
  name: 'HelloWorld',
  data,
  mounted,
};
</script>
