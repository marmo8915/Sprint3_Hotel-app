<template>
<<<<<<< HEAD
  <div id="UserRegistro">
    <h2>{{ username }}</h2>
    <h2>
      <span> {{ estado }}  </span>
    </h2>
    </div>
</template>

<script>
import axios from "axios";
=======
<div>
  <div id="UserRegistro">

    <div class="titulo">
      <h2>
        Hola <span> {{ estado }}, </span> ¡Te damos la bienvenida!
      </h2>
    </div>

  </div>
<div class="imagen">
  <v-img
  contain
  lazy-src="https://i3.visitchile.com/img/GalleryContent/112184/Galerias_6.jpg"
  max-height="600"
  max-width="1000"
  margin-right= center;
  margin-left= center;
  src="https://i3.visitchile.com/img/GalleryContent/112184/Galerias_6.jpg"
></v-img>
</div>
</div>

</template>

<script>
>>>>>>> 445a3fc985b7fe7245231e9e0668ce0878cacb01
export default {
  name: "UserRegistro",
  data: function () {
    return {
<<<<<<< HEAD
      username: "",
=======
>>>>>>> 445a3fc985b7fe7245231e9e0668ce0878cacb01
      estado: "none",
    };
  },
  created: function () {
<<<<<<< HEAD
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
=======
    this.estado = this.$route.params.estado;
  },
};
</script>

<style>
#UserRegistro {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: right;
}

.imagen {
  display: flex;
  height: 65vh;
  align-content: center;
  margin: 0%;
  padding: 0%;
  justify-content: center;
  align-items: center;
  margin-right: center;
  margin-left: center;
}

>>>>>>> 445a3fc985b7fe7245231e9e0668ce0878cacb01
#UserRegistro h2 {
  font-size: 50px;
  color: #283747;
}
#UserRegistro span {
  color: crimson;
  font-weight: bold;
}
<<<<<<< HEAD
</style>
=======
</style>
>>>>>>> 445a3fc985b7fe7245231e9e0668ce0878cacb01
