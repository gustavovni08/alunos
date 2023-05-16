<template>
  <div class="main-container">
    <h2>Preencha o formulário:</h2>
    <form @submit.prevent="getAlunoInfo">
      <label for="nome">Nome completo:</label><br>
      <input type="text" id="nome" required><br><br>
      
      <label for="matricula">Número de matrícula:</label><br>
      <input type="text" id="matricula" required><br><br>
      
      <label for="telefone">Telefone:</label><br>
      <input type="text" id="telefone" required><br><br>
      
      <label for="email">Email:</label><br>
      <input type="email" id="email" required><br><br>
      
      <label for="cep">CEP:</label><br>
      <input type="text" id="cep" required><br><br>
      
      <input type="submit" value="Enviar" @click="adicionarAluno()">
    </form>

    <div v-for="(aluno, index) in alunos" :key="aluno.id">
         <p>{{aluno.nome}}</p>
         <p>{{aluno.matricula}}</p>
         <p>{{aluno.telefone}}</p>
         <p>{{aluno.email}}</p>
         <p>{{aluno.cep}}</p>

         <button value="deletar" @click="deletarAluno(index)">deletar</button>
         <br>
         <button value="deletar" @click="deletarAluno(index)">alterar</button>
         <br>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
        alunos: []
    }
  },
  methods: {
    adicionarAluno() {
     
      const nome = document.getElementById('nome').value;
      const matricula = document.getElementById('matricula').value;
      const telefone = document.getElementById('telefone').value;
      const email = document.getElementById('email').value;
      const cep = document.getElementById('cep').value;
    
     const newAluno = {
        nome:'',
        matricula:'',
        telefone:'',
        email:'',
        cep:'',
     }
     
     newAluno.nome = nome
     newAluno.matricula = matricula
     newAluno.telefone = telefone
     newAluno.email = email
     newAluno.cep = cep

     this.alunos.push(newAluno)

     console.log(this.alunos)

    },

    deletarAluno(index){
        this.alunos.splice(index, 1)
        console.log(this.alunos)
    },
  },

};
</script>
