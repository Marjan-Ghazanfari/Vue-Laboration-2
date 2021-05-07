<template>
  <div class="bg-light">
    <Navbar :users="users"/>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Footer from './components/Footer'

export default {
  name: 'App',
  components: {
    Navbar,
    Footer
  },
  data() {
    return {
      users: [
                {id:'1', name:'Ida', pass:'1234'},
                {id:'2', name:'Mina', pass:'1234'},
                {id:'3', name:'Tina', pass:'1234'},
                {id:'4', name:'Sara', pass:'1234'}
            ]
    }
  }
}
</script>

<style>
.btn-success {
  background-color: #41b883;
  border-color: #41b883;
}
.btn-success:hover {
  background-color: #1a3a2c;
  border-color: #1a3a2c;
}
</style>
