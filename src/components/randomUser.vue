<template>
<div>
    <h1 class="header">Random User Generator</h1>

    <img :class="gender" :src="picture" :alt="`${firstName} ${lastName}`" />
    <h2>{{firstName}} {{lastName}}</h2>
    <h3>Email: {{email}}</h3>
    <button @click="getUser()" :class="gender">Get Random User</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      firstName: 'John',
      lastName: 'Doe',
      email: 'johndoe@gmail.com',
      gender: 'male',
      picture: 'https://randomuser.me/api/portraits/men/10.jpg',
    }
  },

  methods: {
    async getUser() {
      const res = await fetch('https://randomuser.me/api')
      const { results } = await res.json()

      this.firstName = results[0].name.first
      this.lastName = results[0].name.last
      this.email = results[0].email
      this.gender = results[0].gender
      this.picture = results[0].picture.large
      }
  },
}
</script>
<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html,
body {
    font-family: Arial, Helvetica, sans-serif;
}

#app {
    width: 400px;
    height: 100vh;
    margin: auto;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
h1 {
    margin: auto;
    /* margin-top: 1rem; */
    padding: 2rem 0;
    color: steelblue;
    font-weight: bold;
}

h2,
h3 {
    margin-bottom: 1rem;
    font-weight: normal;
}

img {
    border-radius: 50%;
    border: 5px #333 solid;
    margin-bottom: 1rem;
}

.male {
    border-color: steelblue;
    background-color: steelblue;
}

.female {
    border-color: pink;
    background-color: pink;
    color: #333;
}

button {
    cursor: pointer;
    display: inline-block;
    background: #333;
    color: white;
    font-size: 18px;
    border: 0;
    padding: 1rem 1.5rem;
}

button:focus {
    outline: none;
}

button:hover {
    transform: scale(0.98);
}
</style>