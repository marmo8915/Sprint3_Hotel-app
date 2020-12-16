<template>
  <div id="home">
    <h2>{{ username }}</h2>
    <h2>
      Tu habitación es: <span> {{ username }} COP </span>
    </h2>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Home",

  created: function () {
    this.message=this.$route.params.message;
    let self = this;
    axios.get("http://127.0.0.1:8000/home/")
      .then((result) => {
        self.balance = result.data.balance;
      })
      .catch((error) => {
        alert("ERROR Servidor");
      });
  },
};
</script>

<style>
#home {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
#home h2 {
  font-size: 50px;
  color: #283747;
}
#home span {
  color: crimson;
  font-weight: bold;
}
</style>
