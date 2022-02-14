<template>
  <div class="api-test">
    <div>This Is Api Test Component</div>
    {{userData}}
  </div>
</template>

<script>
export default {
    name:"ApiTest",
    data(){
        return{
            userData : {}
        }
    },
    methods:{
        async fetchUser(){
            let response = await fetch('https://jsonplaceholder.typicode.com/todos/1')
            let data = await response.json()
            this.userData = data
        }
    },
    beforeMount(){
        this.fetchUser()
    }
}
</script>

<style>

</style>