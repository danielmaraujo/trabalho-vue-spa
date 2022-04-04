<template>
  <v-app>
    <v-card outlined max-width="50%" class="px-6 pb-6 mx-auto mt-12">
      <v-card-title>Controle de Usuários</v-card-title>
      <CadastrarUsuario @userSave="(usuario) => this.usuarios.push(usuario)"/>
      <br>
      <MostrarUsuarios :usuarios="this.usuarios"/>
    </v-card>
  </v-app>
</template>

<script>
import CadastrarUsuario from './components/CadastrarUsuarios';
import MostrarUsuarios from './components/MostrarUsuarios';

export default {
  name: 'App',

  components: {
    CadastrarUsuario,
    MostrarUsuarios
  },

  data: () => ({
    usuarios: []
  }),
};
</script>
