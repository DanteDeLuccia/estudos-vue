<template>
    <div class="container container-vue">
        <h3>Criar nova empresa</h3>
        <form action="post">
            <input type="text" v-model="nome" name="nome" id="" placeholder="Nome" required>
            <input type="email" v-model="email" name="email" id="" placeholder="Email" required>
            <input type="text" v-model="site" name="site" id="" placeholder="Site">
            <hr>
            <input type="submit" value="Cadastrar" v-on:click="cadastra">
        </form>
    </div>
</template>
<script>

    import axios from 'axios'

    export default {
      name: 'NovaEmpresa',

      data() {
        return {
          nome: '',
          email: '',
          site: '',
        }
      },
      methods: {
        cadastra: function (e) {
            e.preventDefault();
            axios.post('http://localhost:8000/api/companies/', {
                nome: this.nome,
                email: this.email,
                site: this.site,

            })
        }
      }
    }
</script>
