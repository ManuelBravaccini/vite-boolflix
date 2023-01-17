<script>
import { store } from '../store';

export default {
    name: 'AppMain',
    data() {
        return {
            store
        }
    },
}

</script>

<template>
    <main>
        <h1>Main</h1>
    </main>
</template>

<style lang="scss" scoped>
main {
    display: flex;
    justify-content: center;
}
</style>