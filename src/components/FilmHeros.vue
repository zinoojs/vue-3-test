<template>
    <div class="bg-white rounded shadow p-6 m-4 w-full lg:w-3/4 lg:max-w-lg">
          <h3 class="text-center text-3xl">Heros count ( {{heroCount}} )</h3>
            <div class="mb-4">
                <h1 class="text-grey-darkest">Todo List</h1>
                <form action="" @submit.prevent="AddHero()">
                    <div class="flex mt-4">
                    <input class="shadow appearance-none border rounded w-full py-2 px-3 mr-4 text-grey-darker" v-model="newHero" placeholder="Add Todo">
                    <button class="flex-no-shrink p-2 border-2 rounded text-teal border-teal hover:text-grey hover:bg-teal" type="submit">Add</button>
                </div>
                </form>
                
            </div>
            <div>
                <div class="flex mb-4 items-center">
                    <p class="w-full text-grey-darkest">
                      <ul>
                          <li v-for="(h,i) in heros" :key="i">{{ h.name }}
                          <button class="flex-no-shrink p-2 ml-2 border-2 bg-gradient-to-r from-red-700 to-pink-400 rounded text-white border-red hover:text-red hover:bg-red" @click="removeHero(i)">Remove</button>
                          </li>
                      </ul>
                  </p>
                </div>
                
            </div>
      </div>
</template>

<script>
export default {
    data() {
        return {
            newHero : '',
            heros : [
            { name: "super man" },
            { name: "wonderwoman" },
            { name: "spiderman" },
            ]
        }
       
    },
    methods:{
      AddHero() {
        if( this.newHero !== '') {
          this.heros.push({ name : this.newHero});
          this.newHero = '';
        }
      },
      removeHero(index) {
        this.heros = this.heros.filter((hero,i) => i !== index)
      }
    },
    computed: {
      heroCount() {
        return this.heros.length;
      }
    },
}
</script>

<style>

</style>