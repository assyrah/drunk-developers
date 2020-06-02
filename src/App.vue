<template>
  <div id="app">
    <app-header></app-header>
    <app-hero></app-hero>
    <app-articles :articles="articles"></app-articles>
    <app-contact></app-contact>
    <app-signup></app-signup>
    <app-footer></app-footer>
  </div>
</template>

<script>
  import axios from 'axios';
  import appHeader from './components/header.vue'
  import appFooter from './components/footer.vue'
  import appArticles from './components/articles.vue'
  import appHero from './components/hero.vue'
  import appContact from './components/contact.vue'
  import appSignup from './components/signup.vue'
  export default {
    name: 'App',
    components: {
      'app-header': appHeader,
      'app-footer': appFooter,
      'app-articles': appArticles,
      'app-hero': appHero,
      'app-contact': appContact,
      'app-signup': appSignup
    },
      data() {
          return {  
              articles: []
          };
      },
      created: function () {
          // axios.get('https://randomuser.me/api/?results=100&inc=id,name,location,email,dob,picture&seed=012b173efcc779f9')
          //   .then(response => {
          //       const result = response.data.results;
          //       for (let i = 0; i < result.length; i++) {
          //         this.employees.push({
          //           id: result[i].id.value,
          //           name: result[i].name.first + " " + result[i].name.last,
          //           location: result[i].location.street.number + " " + result[i].location.city + " " + result[i].location.state,
          //           email: result[i].email,
          //           dob: this.formatDate(result[i].dob.date),
          //           status: this.assignStatus(result[i].id.value),
          //           picture: result[i].picture.large
          //         })
          //       }
          //   })
            axios.get('https://jsonplaceholder.typicode.com/posts')
            .then(response => (console.log(response.data), this.articles = response.data))
            .catch(error => console.log(error))
            console.log(this.articles)
      },
      methods: {
        formatDate (givenDate) {
          return new Date(givenDate).toLocaleDateString();
        },
        assignStatus (employeeId) {
          let status = "Discarded";
          if (employeeId) {
            status = "Employed";
          }
          return status;
        }
      }
  }
</script>

<style lang="scss">
  @import "./styles/main.scss"
</style>
