<template>
    <div class="hello">


        <h1>{{ msg }}</h1>


        <div>
            Count: {{count}}
        </div>


        <div>
            Store count: {{storeCount}}
        </div>

        <div>
            <button @click="incNum">Add</button>
        </div>
    </div>
</template>

<script>
    import store from '../store';

    export default {
        name: 'HelloWorld',
        props: {
            msg: String,
        },
        data(){
            return {
                count: 0
            }
        },
        methods: {
            incNum(){
                // this.count += 1;
                store.commit('increment')
            }
        },
        computed: {
          storeCount(){
              return store.state.count;
          }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }

    li {
        display: inline-block;
        margin: 0 10px;
    }

    a {
        color: #42b983;
    }
</style>
