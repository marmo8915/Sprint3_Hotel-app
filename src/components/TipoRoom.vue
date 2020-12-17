<template>
  <div id="TipoRoom">
    <h2>{{ username }}</h2>
    <div>
        <table>
          <tbody>
            <tr>
              <td>id_room: {{rooms.id_room}}</td>
            </tr>
            <tr>
              <td>Tipo de Habitación{{rooms.tipo_room}}</td>
            </tr>
            <tr>
              <td>Camas: {{rooms.camas}}</td>
            </tr>
            <tr>
              <td>Ocupación: {{rooms.ocupacion}}</td>
            </tr>
            <tr>
              <td>Superficie: {{rooms.superficie}}</td>
            </tr>
            <tr>
              <td>Vistas: {{rooms.vistas}}</td>
            </tr>
            <tr>
              <td>A partir de $: {{rooms.tarifa_basica}}</td>
            </tr>
          </tbody>
        </table>
    </div>
    <div> 
      <b-table striped hover :items="rooms"> </b-table> 
    </div> 
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "TipoRoom",
  data: function () {
    return {
      rooms: null
    };
  },
  created: function () {
    this.username = this.$route.params.username; //Obtiene el nombre de usuario de localstorage
    let self = this; // captura el this en axios para usarlo
    axios
      .get("http://127.0.0.1:8000/room/Superior")
      .then((response) => {     // se ejecuta cuando todo sale bien
        self.rooms = response.data;
      })
      .catch((error) => {
        alert("ERROR Servidor");
      });
  },
};
</script>
<style>
td{
  text-align: center;
  }
</style>