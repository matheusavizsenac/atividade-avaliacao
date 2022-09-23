<template>
    <div>
      <input type="button" value="Calcular" @click="calculaNota"/><br/><br/>
      <br>
      <table>
        <tr>
            <th>Nome do Aluno</th>
            <th>Situacao</th>
        </tr>
        <tr v-for='item in listaAlunos' :key="item.NomeAluno">
            <td v-if="item.situacao == 'Aprovado'" style="background-color: blue;">
                {{item.nome}}
            </td>
            <td v-if="item.situacao == 'Aprovado'" style="background-color: blue;">
              {{item.situacao}}
            </td>
            <td v-if="item.situacao == 'Reprovado'" style="background-color: Red;">
                {{item.nome}}
            </td>
            <td v-if="item.situacao == 'Reprovado'" style="background-color: Red;">
              {{item.situacao}}
            </td>
        </tr>

    </table>
    </div>
</template>
  
  <script>
  export default {
    name: "Nota-Aluno",
    props: {
      nomeAluno: String, 
      nota1: Number,
      nota2: Number,
      nota3: Number,
      media: Number,
    },
  
    data(){
      return {
        listaAlunos: []
      }
      },

    methods: {
      calculaNota(){
        var situacao = ""
        var notaFinal = (this.nota1 + this.nota2 * 2 + this.nota3 * 3 + this.media ) / 7
        if (notaFinal >= 7){
          situacao = "Aprovado"
        } else{situacao = "Reprovado"}
        
        this.adicionaLista(this.nomeAluno, situacao)
      },
      adicionaLista(nome, situacao){
        this.listaAlunos.push({nome: nome, situacao: situacao})
      }
    }

    }
  
  
  </script>
  

  <style scoped>
  table, th, td {
    border: 1px solid;
  }
  
  </style>
  