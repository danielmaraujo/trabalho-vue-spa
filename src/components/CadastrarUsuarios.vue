<template>
  <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          v-bind="attrs"
          v-on="on"
        >
          Cadastrar
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          Cadastro
        </v-card-title>

        <v-form class="pa-6">
          <v-text-field v-model="nome" label="Nome" max-width="75%"/>
          <v-text-field v-model="email" label="Email"/>
          <v-text-field type="number" :min=0 v-model="idade" label="Idade"/>
          <v-text-field type="password" v-model="senha" label="Senha"/>
        </v-form>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="save()"
          >
            Inserir
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
  export default {
    data: () => ({
      dialog: false,
      nome: null,
      email: null,
      idade: 0,
      senha: null
    }),

    methods:{
      save(){
        this.$emit('userSave', {nome: this.nome, email: this.email, idade: this.idade, senha: this.senha})
        this.nome = null
        this.email = null
        this.idade = null
        this.senha = null
        this.dialog = false
      }
    }
  }
</script>