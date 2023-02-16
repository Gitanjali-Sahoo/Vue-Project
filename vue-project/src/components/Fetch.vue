<template>
  <div id="fetch-books" @click="showTable = true">
    <h2>Subjects</h2>
    <p>Here you can see all the types of books list</p>
    <input
      class="fetch-btn"
      type="button"
      @click="fetchBooks"
      value="collections"
    />
    <table class="table">
      <thead v-show="showTable" class="table-dark">
        <tr>
          <th scope="col">List</th>
          <th scope="col">Subjects</th>
          <th scope="col">Collections</th>
        </tr>
      </thead>
      <tbody v-if="books !== null">
        <tr v-for="book in books">
          <th scope="row">{{ book.id }}</th>
          <td class="table-light">{{ book.name }}</td>
          <td>{{ book.Collections }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      books: null,
      isShow: false,
    };
  },
  methods: {
    async fetchBooks() {
      const res = await fetch("books.json");
      const val = await res.json();
      this.books = val;
    },
    mounted() {
      this.fetchBooks();
    },
  },
};
</script>
<style scoped>
#fetch-books {
  margin-bottom: 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
#fetch-books h2 {
  text-decoration: underline;
}
.fetch-btn {
  margin-bottom: 10px;
}
</style>
