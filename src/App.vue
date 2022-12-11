<template>
  <div id="app">

      <FilterComponent :store="store" />

    <CatGenerator />
  </div>
</template>

<script>
    import CatGenerator from './components/CatGenerator';
    import FilterComponent from './components/FilterComponent';

    export default {
        name: 'App',
        data() {
            return {
                store: {
                    items: [
                        { id: 1, name: 'Apple' },
                        { id: 2, name: 'Banana' },
                        { id: 3, name: 'Orange' }
                    ]
                }
            }
        },
        components: {
            FilterComponent,CatGenerator
        }


    }
</script>
