<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Directives Exercise</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->
                <button class="btn btn-primary" v-my-on:click="alertMe">Click me!</button>
                

                <div style="width: 100px; height: 100px; background-color: lightgrey"
                     v-my-on:mouseleave="mouseLeave"
                     v-my-on:mouseenter="mouseEnter"></div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            alertMe() {
                alert('Someone clicked me!');
            },

            mouseEnter() {
                console.log('mouse entered');
            },

            mouseLeave() {
                console.log('mouse left');
            }
        },

        directives: {
            'my-on': {
                bind(el, binding, vnode) {
                    const type = binding.arg;
                    const myFunction = binding.value;

                    el.addEventListener(type, myFunction)
                }
            }
        }
    }
</script>

<style>
</style>
