<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      msg: 'y',
    };
  },
  mounted() {
    this.hello();
  },
  methods: {
    hello() {
      axios.get('/')
        .then(response => {
          this.msg = response.data.greeting;
        })
        .catch(error => {
          console.log(error);
        });
    },
  },
};
</script>
