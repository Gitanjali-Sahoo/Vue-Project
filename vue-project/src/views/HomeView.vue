<script setup>
    import HeroImage from '../components/HeroImage.vue'
    import Cards from '../components/Cards.vue'
    // import ImageSlider from '../components/ImageSlider.vue'
</script>

<template>
    <HeroImage />

    <Cards />
    <!-- <div id="slider-app">
        <ImageSlider />
    </div> -->

    <div id="fetch-books">
        <input type="button" @click="fetchBooks" value="collections" />
        <table class="table">
            <thead class="table-dark"></thead>
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
                books: null
            }
        },
        methods: {
            async fetchBooks() {
                const res = await fetch('books.json')
                const val = await res.json()
                this.books = val
            },
            mounted() {
                this.fetchBooks()
            }
        }
    }
</script>

<style scoped></style>
