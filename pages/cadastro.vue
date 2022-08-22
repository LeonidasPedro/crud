<template>
  <v-data-table
    :headers="headers"
    :items="paises"
    :search="paises"
    rounded
    sort-by="calories"
    class="elevation-1"
  >
    <template v-slot:top>
      <v-toolbar
        flat
      >
        <v-toolbar-title>
          <v-icon
            color="#bf2934">
            mdi-flag
          </v-icon>
          Países
        </v-toolbar-title>
        <v-divider
          class="mx-4"
          inset
          vertical
        ></v-divider>
        <v-spacer></v-spacer>
        <v-dialog
          v-model="dialog"
          max-width="500px"
        >
          <template v-slot:activator="{ on, attrs }">
            <v-btn
              color="#a1226c"
              rounded
              class="mb-2"
              v-bind="attrs"
              v-on="on"
            >
            <v-icon
            color="white">
              mdi-plus
            </v-icon>
            Novo
            </v-btn>
          </template>
          <v-card>
            <v-card-title>
              <span class="text-h5">Países</span>
            </v-card-title>
            <v-card-text>
              <v-container>
                <v-row>
                  <v-col
                    cols="12"
                    sm="6"
                  >
                    <v-text-field
                      label="Nome"
                    ></v-text-field>
                  </v-col>
                  <v-col
                    cols="12"
                    sm="6"   
                  >
                    <v-text-field
                      label="Lingua"
                    ></v-text-field>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>

            <v-card-actions>
              <v-spacer>
              </v-spacer>
              <v-btn
                color="blue darken-1"
                text              
              >
                Cancel
              </v-btn>
              <v-btn
                color="blue darken-1"
                text
              >
                Save
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>
      </v-toolbar>
    </template>
    <template v-slot:item.actions="{ item }">
      <v-icon
        small
        class="mr-2"
        color="#669a43"
      >
        mdi-pencil
      </v-icon>
      <v-icon
        small
        color="#bf2934"
      >
        mdi-delete
      </v-icon>
    </template>
  </v-data-table>
</template>

<script>
export default {
  name: 'CadastroPage',
   data () {
      return {
        headers: [
          { text: 'País', value: 'name' },
          { text: 'Língua', value: 'lingua' },
          { text: "", value: "actions" }
        ],
        paises: [
          {
            name: 'Portugal',
            lingua: 'portugues',
          },
          {
            name: 'Chile',
            lingua: 'Espanhol',
          },
          {
            name: 'Ilhas Falkland',
            lingua: 'Inglês',
          },
          {
            name: 'Croácia',
            lingua: 'Croata',
          },
          {
            name: 'Liechtenstein',
            lingua: 'Alemão',
          },
          {
            name: 'Moldávia',
            lingua: 'Romeno',
          },
          {
            name: 'San Marino   ',
            lingua: 'Italiano',
          },
          {
            name: 'Ilhas Faroé',
            lingua: 'dinamarquês',
          },
        ],
      }
  }
}
</script>,
