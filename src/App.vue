<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Directives Exercise</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->
                <button v-my-on:click="alertMe" class="btn btn-primary">Click me!</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            alertMe() {
                alert('Someone clicked me!');
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
