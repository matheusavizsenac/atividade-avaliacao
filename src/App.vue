<template>
  <label for="nomeAluno">Insira o nome do Aluno: </label>
  <input id="nomeAluno" v-model="nomeAluno" type="text"><br>
  <label for="nota1">Insira a primeira nota: </label>
  <input id="nota1" v-model="nota1" type="number"><br>
  <label for="nota2">Insira a segunda nota: </label>
  <input id="nota2" v-model="nota2" type="number"><br>
  <label for="nota3">Insira a terceira nota: </label>
  <input id="nota3" v-model="nota3" type="number"><br>
  <label for="nota3">Insira a media: </label>
  <input id="media" v-model="media" type="number"><br>
  <Nota-Aluno :nomeAluno="nomeAluno" :nota1="nota1" :nota2="nota2" :nota3="nota3" :media="media"/>
</template>

<script>
import NotaAluno from './components/NotaAluno.vue'

export default {
  name: 'App',
  components: {
    NotaAluno
  },

  data(){
    return{
      nomeAluno: "",
      nota1: 0,
      nota2: 0,
      nota3: 0,
      media: 0
    }
  }
}
</script>

<style>

</style>
