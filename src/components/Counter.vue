<template>
  <h2>{{ customTitle }}</h2>
  <p>{{ counter }} <sup>2</sup> = {{ squareCounter }}</p>
  <div>
      <button @click=" incrementCounter ">+1</button>
      <button @click=" decrementCounter ">-1</button>
  </div>
</template>

<script>
export default {
    props: {
        title: {
            required: false,
        },
        start: {
            type: Number,
            required: false,
            default: 14,
        },
    },
    data() { 
        return {
            counter: this.start
        }
    },
    computed: {
        squareCounter() { 
            return this.counter * this.counter;
        },
        customTitle() { 
            return this.title ? this.title : 'No title provided';
        }
    },
    methods: {
        incrementCounter() { 
            this.counter += 1;
        },
        decrementCounter() { 
            this.counter -= 1;
        }
    }
}
</script>

<style>
button {
    margin: 10px;
    padding: 5px 15px;
    background: #41B883;
    border: none;
    color: white;
    border-radius:10px
}
</style>
