<template>
    <div>
        <img :src="randomCatUrl" alt="Random cat" />
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        data() {
            return {
                randomCatUrl: ''
            }
        },
        created() {
            this.generateRandomCatUrl()
        },
        methods: {
            generateRandomCatUrl() {
                // Generate a random number between 1 and 100
                const randomNumber = Math.floor(Math.random() * 100) + 1;
                // Use the random number to retrieve a random cat image from the cat API

                this.randomCatUrl = `https://api.thecatapi.com/v1/images/search?limit=1&page=${randomNumber}`;
                axios.get(this.randomCatUrl, {
                    headers: {
                        'x-api-key': 'live_kIr0fhQLq7LlB5hGFVZyoaNHwM77Op5E50KuzXiaLQdMP7FIqZZQFgGfykjKusLv'
                    }
                }).then(response => {
                    // Set the randomCatUrl variable to the URL of the cat image
                    this.randomCatUrl = response.data[0].url;
                });
            }
        }
    }
</script>

<style scoped>

</style>

