<template>
    <main class="d-flex flex-column">
        <header :class="showHeader ? 'show' : null">
            <div class="row align-items-center">
                <div class="col">
                    <h3 class="m-0 text-white">Jesper Pettersson</h3>
                </div>
                <div class="col-auto ml-auto">
                    <a  href="#"
                        @click.prevent=""
                        class="menu">
                        <span></span>
                        <span></span>
                        <span></span>
                    </a>
                </div>
            </div>
        </header>
        <section    id="home"
                    class="text-center">
            <div class="pt-5 pb-3">
                <h1 class="animated"
                    :class="tkey === index ? 'show' : null"
                    v-html="text"
                    v-for="(text, tkey) in texts"
                    :key="tkey"></h1>
            </div>
        </section>
    </main>
</template>
<script>
    export default {
        data() {
            return {
                texts: ['', 'Hello!', 'My name is Jesper', 'This is my resumé page', 'Want to see more?', 'Scroll down to explore!'],
                index: 0,
                showHeader: false
            }
        },
        methods: {
            init() {
                setTimeout(() => {
                    if(this.index < this.texts.length - 1) {
                        this.index++
                        this.init()
                    } else {
                        setTimeout(() => {
                            this.showHeader = true
                        }, 2000)
                    }
                }, 2500)
            }
        },
        mounted() {
            this.init()
        }
    }
</script>
