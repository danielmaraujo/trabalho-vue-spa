<template>
  <div class="text-center">
    <v-dialog
      v-model="dialog"
      width="500"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          v-bind="attrs"
          v-on="on"
        >
          Listar usuários
        </v-btn>
      </template>

      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          Usuários cadastrados
        </v-card-title>

        <v-data-table
          :headers="headers"
          :items="usuarios"
          disable-pagination
          hide-default-footer
        ></v-data-table>


        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="dialog = false"
          >
            Fechar
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
  export default {
    props:{
      usuarios: Array
    },

    data () {
      return {
        dialog: false,
        headers: [
          { text: "Nome", align: "start", sortable: true, value: "nome" },
          { text: "Email", value: "email", sortable: false },
          { text: "Idade", value: "idade", sortable: true },
        ],
      }
    },
  }
</script>