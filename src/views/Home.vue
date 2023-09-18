<template>
    <main>
        <h1 class="text-center" v-html="text" v-for="(text, tkey) in texts" :class="tkey === index ? 'show' : null"></h1>
    </main>
</template>
<script>
    export default {
        data() {
            return {
                texts: ['Welcome', 'to my', 'portfolio'],
                index: 0
            }
        },
        methods: {
            init() {
                setTimeout(() => {
                    if(this.index < this.texts.length - 1) this.index++
                    else this.index = 0
                    this.init()
                }, 3000)
            }
        },
        mounted() {
            this.init()
        }
    }
</script>
