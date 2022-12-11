<template>
    <div>
        <input type="text" v-model="searchTerm" placeholder="Filter items" />
        <ul>
            <li v-for="item in filteredItems" :key="item.id">
                {{ item.name }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        props: {
            store: {
                type: Object,
                required: true
            }
        },
        data() {
            return {
                searchTerm: ''
            }
        },
        computed: {
            filteredItems() {
                // Filter the store items by the search term
                return this.store.items.filter(item =>
                    item.name.toLowerCase().includes(this.searchTerm.toLowerCase())
                );
            }
        }
    }
</script>