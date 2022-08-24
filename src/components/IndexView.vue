<script>
export default {
  data() {
    return {
      qualidades: [
        { qualidade: 5, servico: "5% (Péssimo)" },
        { qualidade: 10, servico: "10% (Ruim)" },
        { qualidade: 15, servico: "15% (OK)" },
        { qualidade: 20, servico: "20% (Bom)" },
        { qualidade: 25, servico: "25% (Mais que bom)" },
        { qualidade: 30, servico: "30% (Excelente)" },
      ],
      valor: 0,
      pessoa: 1,
      qualidade_selecionada: "",
    };
  },
  computed: {
    valor_final() {
      return (
        (this.valor * (1 + this.qualidade_selecionada / 100)) /
        this.pessoa
      ).toFixed(2);
    },
  },
};
</script>

<template>
  <div class="app">
    <h1>Calcular Gorjetas</h1>
    <form action="" class="formGorjeta">
      <label for="valorConta">Valor da conta:</label>
      <input name="valorConta" v-model="valor" type="number" />
      <label for="porcentagemServico">Como foi o serviço?</label>
      <select v-model="qualidade_selecionada">
        <option
          v-for="qualidade of qualidades"
          :key="qualidade.qualidade"
          for="select-servico"
          :value="qualidade.qualidade"
        >
          {{ qualidade.servico }}
        </option></select
      ><label for="qtdPessoas">Nº de pessoas pagando a conta:</label
      ><input name="qtdPessoas" type="number" v-model="pessoa" />
    </form>

    <div class="resultado">
      <h3>Valor da conta:</h3> 
      <span>R$ {{ valor_final }} por pessoa</span>
    </div>
  </div>
</template>

<style>
.app {
  display: flex;
  justify-content: center;
  flex-direction: column;
}
h1 {
  text-align: center;
}

form {
  padding: 10%;
}

input, select {
  padding: 1%;
  border-radius: 10px;
}

.resultado {
  background-color: yellow;
}
</style>
