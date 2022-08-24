<script></script>

<template>
  <div id="app">
    <h1>Calcular Gorjetas</h1>
    <form action="" class="formGorjeta">
      <label for="valorConta">Valor da conta:</label>
      <input name="valorConta" type="number" />
      <label for="porcentagemServico">Como foi o serviço?</label>
      <select>
        <option value="30">30% (Excepcional)</option>
        <option value="25">25% (Mais do que bom)</option>
        <option value="20">20% (Bom)</option>
        <option value="15">15% (OK)</option>
        <option value="10">10% (Ruim)</option>
        <option value="5">5% (Péssimo)</option></select
      ><label for="qtdPessoas">Nº de pessoas pagando a conta:</label
      ><input name="qtdPessoas" type="number" />
    </form>

    <div class="resultado">
      Valor da conta:
      <span class="valorContaPorPessoa">R$ 0.00 por pessoa</span>
    </div>
  </div>
</template>

<style></style>
