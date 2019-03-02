new Vue({
  el: '#app',
  data: {
    titulo: "hola mundo!",
    users: [],
    numberPages: 1,
  },
  methods: {
    getUsers() {
      axios.get('https://reqres.in/api/users', {
        params: {
          'page': this.numberPages
        }
      }).then(res => {
        this.users = res.data.data
        console.log(this.users)
      }).catch(e => {
        console.log(e)
      })
    }
  },
  created() {
    this.getUsers()
  }
})
