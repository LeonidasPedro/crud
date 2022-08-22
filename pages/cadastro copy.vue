<template>
  <v-container>
    <v-row>
      <v-btn
      elevation="2"
      >Novo País
      </v-btn>
    </v-row>
    <v-row>
      <v-sheet 
        rounded="lg"
        color="white"
        elevation="7"
        >    
          <v-container
          >
          <v-row>
            <v-col>
              <template>
                <v-data-table
                  :headers="headers"
                  :items="paises"
                  :items-per-page="5"
                >
                  <template v-slot:item.actions="{ item }">
                    <v-icon
                      small
                      class="mr-2"
                      @click="editItem(item)"
                    >
                    mdi-pencil
                    </v-icon>
                    <v-icon
                      X
                      small
                      @click="deleteItem(item)"
                    >
                    mdi-delete
                    </v-icon>
                  </template>
                  <template v-slot:no-data>
                      <v-btn
                      color="primary"
                      @click="initialize"
                        >
                        Reset
                      </v-btn>
                  </template>
                </v-data-table>
              </template>
            </v-col>
          </v-row>
          </v-container>
      </v-sheet>
    </v-row>
    
  </v-container>
</template>

<script>
export default {
  name: 'CadastroPage',
   data () {
      return {
        headers: [
          { text: 'País', value: 'name' },
          { text: 'Língua', value: 'lingua' },
          { text: "", value: "actions"}
        ],
        paises: [
          {
            name: 'Portugal',
            lingua: 'portugues',
          },
           {
            name: 'Portugal',
            lingua: 'portugues',
          },
           {
            name: 'Portugal',
            lingua: 'portugues',
          },
           {
            name: 'Portugal',
            lingua: 'portugues',
          },
           {
            name: 'Portugal',
            lingua: 'portugues',
          },
           {
            name: 'Portugal',
            lingua: 'portugues',
          } 
        ],
      }
  }
}
</script>,
