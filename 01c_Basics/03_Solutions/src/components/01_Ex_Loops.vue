<template>
  <div>
    <h1>Looping through arrays (demo-07.vue)</h1>
    <!-- Backticks -->
    <div v-for="n in 5" :key="`${n}`">
      {{ n }}
    </div>

    <ul>
      <li v-for="n in 5" :key="n">
        {{ n }}
      </li>
    </ul>
    <ul>
      <li v-for="(item, n) in interests" :key="n">
        {{ item }}
      </li>
    </ul>
    <!-- Object -->
    <h3>Book:</h3>
    <ol>
      <li v-for="item in book" :key="item">
        {{ item }}
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  data() {
    return {
      interests: ['TV', 'Games', 'Sports', '07_Loops.vue'],
      book: [
          {
            title: 'Schachnovelle',
            author: 'Stefan Zweig',
            publishedAt: '19xy-04-10'
          },{
            title: 'Ready Player One',
            author: 'Ernest Clien',
            publishedAt: '20xx-04-10'
          },
      ]
    }
  },
}
</script>

<style lang="scss" scoped>
li {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 10px;
}

h1 {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
