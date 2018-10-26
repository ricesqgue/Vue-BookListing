<template>
  <div>
    <h1>{{ title }}</h1>
    <ul>
      <book-item v-for="book in books" :key="book.title" :book="book">
      </book-item>
    </ul>
    <book-form @addBook="appendBook"></book-form>
  </div>
</template>

<script>

import BookItem from './BookItem';
import BookForm from './BookForm';

export default {
  name: 'BookList',
  components: {
    BookItem,
    BookForm
  },
  data: () => ({
    title: 'All Books',
    books: [
      { title: 'Self-Reliance', author: 'Ralph Waldo Emerson' },
      { title: 'American Gods', author: 'Neil Gaiman' },
      { title: 'Amusing Ourselves to Death', author: 'Neil Postman' }
    ]
  }),
  methods: {
    appendBook (bootTitle, bookAuthor) {
      this.books.push({ title: bootTitle, author: bookAuthor })
    }
  }
}
</script>

<style>
  h1, h2 {
    font-weight: normal;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
</style>
