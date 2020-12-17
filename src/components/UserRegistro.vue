<template>
  <div id="UserRegistro">
    <h2>{{ username }}</h2>
    <h2>
      <span> {{ estado }}  </span>
    </h2>
    </div>
</template>

<script>
import axios from "axios";
export default {
  name: "UserRegistro",
  data: function () {
    return {
      username: "",
      estado: "none",
    };
  },
  created: function () {
    this.username = this.$route.params.username;
    let self = this;
    axios
      .get("http://127.0.0.1:8000/user/room/" + this.username)
      .then((result) => {
        self.estado = result.data.estado;
      })
      .catch((error) => {
        alert("ERROR Servidor");
      });
  },
};

</script>
<style>
#UserRegistro h2 {
  font-size: 50px;
  color: #283747;
}
#UserRegistro span {
  color: crimson;
  font-weight: bold;
}
</style>
