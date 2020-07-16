<template>
  <div id="formulario">
    <div class="row">
        <form v-on:submit="Datos">
            <div class="col s12 m8 l4 offset-m2 offset-l4">
                <div class="card">
                    <div class="card-action teal lighten-1 white-text">
                        <h5 id="titulo">Formulario</h5>
                    </div>
                    <div class="card-content">
                    <div class="input-field">
                        <label for="username">Nombre</label>
                        <input type="text" v-model="nombre" class="validate" required>
                    </div>
                    <div class="input-field">
                        <select v-model="localizacion" required>
                          <option value="" disabled selected>Seleccione Localización</option>
                          <option value="California">California</option>
                          <option value="Washintong">Washintong DC</option>
                          <option value="New York">New York</option>
                          <option value="Las Vegas">Las Vegas</option>
                        </select>
                    </div>
                    <div class="input-field">
                        <select v-model="lenguaje" required>
                            <option value="" disabled selected>Seleccione Lenguaje Favorito</option>
                            <option value="Java Script">Java Script</option>
                            <option value="Css">Css</option>
                            <option value="Phyton">Phyton</option>
                            <option value="NET">NET</option>
                        </select>
                    </div><br>
                    <p>Seleccione su/s framework favoritos:</p><br>
                    <label class="check">
                        <input type="checkbox"  value="Vue" v-model="frameworks"/>
                        <span>Vue</span>
                    </label>
                        <label class="check">
                        <input type="checkbox" value="React" v-model="frameworks"/>
                        <span>React</span>
                    </label>
                    <label class="check">
                        <input type="checkbox" value="Angular" v-model="frameworks" />
                        <span>Angular</span>
                    </label><br><br>
                    <div class="input-field">
                        <textarea v-model="comentarios" class="materialize-textarea" required></textarea>
                        <label for="textarea1">Comentarios</label>
                    </div>
                    <div class="form-field">
                        <button type="submit" class="btn-large waves-effect waves-dark" style="width:100%;">Enviar</button>
                    </div><br>
                </div>
              </div>
            </div>
        </form>
    </div>
    <!-- Modalcito-->
    <div id="modal1" class="modal">
        <div class="modal-content">
        <h4>Los campos seleccionados por usted son: </h4>
        <p>Nombre: {{this.nombre}}</p>
        <p>Localización: {{this.localizacion}}</p>
        <p>Lenguaje Favorito: {{this.lenguaje}}</p>
        <p>Frameworks Favoritos: {{this.frameworks}}</p>
        <p>Comentarios: {{this.comentarios}}</p>
        </div>
        <div class="modal-footer">
        <a href="#!" class="modal-close waves-effect waves-light btn">Cerrar</a>
        </div>
    </div>
    </div>
</template>
<script>
import M from 'materialize-css'
  export default {
      name: "Formulario",
      data: () => {
          return {
              nombre: '',
              localizacion:'',
              lenguaje:'',
              comentarios:'',
              frameworks:[]
          };
      },
      mounted: function(){
        M.AutoInit();
      },
      methods: {
        Datos: function(ev) {
           ev.preventDefault();
           const modal = document.querySelector('.modal')
           var instance = M.Modal.getInstance(modal);
           instance.open();
        }
      }
  }
</script>
<style scoped>
    #titulo{
    text-align:center;
    }
    .check{
        margin:10px;
    }
</style>
