<script>
import { store } from '../store';
import axios from 'axios';

export default {
    name: 'AppHeader',

    data() {
        return {
            store,
            apiKey: 'b2e2c5a561ab474b668dc5ad4dda43cf',
            apiUrl: 'https://api.themoviedb.org/3/search/movie',
        }
    },

    methods: {
        getMovies(searchedQuery) {
            axios.get(this.apiUrl, {
                params: {
                    api_key: this.apiKey,
                    query: searchedQuery
                }
            })
                .then((response) => {
                    //console.log(response.data.results);
                    this.store.moviesList = response.data.results;
                })
                .catch(function (error) {
                    console.warn(error);
                });
        }
    },

    created() {
        //this.getMovies();
    },
}

</script>

<template>
    <header>
        <label for="user-search">
            Search movies:
        </label>
        <input type="text" id="user-search" v-model="store.searchText">
        <button @click="getMovies(store.searchText)">Search</button>

        <ul>
            <li v-for="(movieEl, index) in store.moviesList" :key="index">
                <h3>
                    {{ movieEl.title }}
                </h3>
                <h3>
                    {{ movieEl.original_title }}
                </h3>
                <p>
                    {{ movieEl.original_language }}
                </p>
                <p>
                    {{ movieEl.original_title }}
                </p>
            </li>
        </ul>
    </header>
</template>

<style lang="scss" scoped>

</style>
