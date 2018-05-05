<template>
  <v-container>
      <v-layout row>

         <v-flex xs6 offset-xs3>
              <v-form>
                <v-text-field
                    label="Nome"
                    required
                    v-model="client.name"
                ></v-text-field>

                <v-text-field
                    label="Email"
                    required
                    v-model="client.email"
                ></v-text-field>

                <v-text-field
                    label="CPF"
                    required
                    v-model="client.cpf"
                ></v-text-field>

                <v-flex xs12 class="text-xs-center">
                    <v-btn
                        color="info"
                        @click="save()"
                        >
                        Salvar
                    </v-btn>
                </v-flex>

            </v-form>

            <h1>Clientes cadastrados</h1>

            <v-data-table
                :headers="headers"
                :items="clients"
                hide-actions
                class="elevation-1"
            >
                <template slot="items" slot-scope="client">
                <td>{{ client.item.name }}</td>
                <td>{{ client.item.email }}</td>
                <td>{{ client.item.cpf }}</td>
                </template>
            </v-data-table>

         </v-flex>

      </v-layout>
  </v-container>
</template>
<script>
    export default{
        data(){
            return {
                client: {},
                clients: [
                    {
                        name: "Jão da Silva",
                        email: "jao@gmail.com",
                        cpf: "123"
                    },
                    {
                        name: "Maria da Silva",
                        email: "mar@gmail.com",
                        cpf: "3321"
                    },
                    {
                        name: "Zé da Silva",
                        email: "ze@gmail.com",
                        cpf: "573"
                    }
                ]
            }
        },
        methods: {
            save(){
                window.alert(
                    "Nome: " + this.client.name + 
                    "\nEmail: " + this.client.email + 
                    "\nCPF: " + this.client.cpf 
                );
            }
        }
    };
</script>