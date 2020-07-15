<template>
  <div id="formulario">
    <div class="row">
        <form>
            <div class="col s12 m8 l4 offset-m2 offset-l4">
                <div class="card">
                    <div class="card-action teal lighten-1 white-text">
                        <h3 id="titulo">Formulario</h3>
                    </div>
                    <div class="card-content">
                    <div class="input-field">
                        <label for="username">Nombre</label>
                        <input type="text" v-model="nombre" class="validate">
                    </div><br>
                    <div class="input-field">
                        <select v-model="localizacion">
                          <option value="" disabled selected>Seleccione Localización</option>
                          <option value="California">California</option>
                          <option value="Washintong">Washintong DC</option>
                          <option value="New York">New York</option>
                          <option value="Las Vegas">Las Vegas</option>
                        </select>
                    </div><br>
                    <div class="input-field">
                        <select v-model="lenguaje">
                            <option value="" disabled selected>Seleccione Lenguaje Favorito</option>
                            <option value="Java Script">Java Script</option>
                            <option value="Css">Css</option>
                            <option value="Phyton">Phyton</option>
                            <option value="NET">NET</option>
                        </select>
                    </div><br>
                    <div class="input-field">
                        <textarea v-model="comentarios" class="materialize-textarea"></textarea>
                        <label for="textarea1">Comentarios</label>
                    </div>
                    <div class="form-field">
                        <button class="btn-large waves-effect waves-dark" style="width:100%;">Enviar</button>
                    </div><br>
                </div>
              </div>
            </div>
        </form>
    </div>
  </div>
</template>
<script>
  export default {
      name: "Formulario",
      data: () => {
          return {
              nombre: '',
              localizacion:'',
              lenguaje:'',
              comentarios:'' 
          };
      }
  }
</script>
<style scoped>
#titulo{
  text-align:center;
}
</style>
