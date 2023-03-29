# Calculadora-de-IMC
Este projeto consiste em uma calculadora de índice de massa corporal (IMC) que solicita ao usuário o seu peso e altura e, em seguida, calcula o seu IMC. O IMC é uma medida que relaciona o peso e altura de uma pessoa e é usada para avaliar se uma pessoa está com o peso ideal, acima do peso ou abaixo do peso.

// Seleciona os elementos HTML
const pesoInput = document.getElementById("peso");
const alturaInput = document.getElementById("altura");
const resultadoDiv = document.getElementById("resultado");

// Adiciona um event listener ao botão de calcular
const calcularButton = document.getElementById("calcular");
calcularButton.addEventListener("click", calcularIMC);

// Define a função para calcular o IMC
function calcularIMC() {
  const peso = parseFloat(pesoInput.value);
  const altura = parseFloat(alturaInput.value);

  if (!peso || !altura) {
    alert("Por favor, insira o peso e a altura corretamente.");
    return;
  }

  const imc = peso / (altura * altura);
  const classificacao = getClassificacaoIMC(imc);

  resultadoDiv.innerHTML = `Seu IMC é ${imc.toFixed(2)}. Você está ${classificacao}.`;
}

// Define a função para obter a classificação do IMC
function getClassificacaoIMC(imc) {
  if (imc < 18.5) {
    return "abaixo do peso";
  } else if (imc < 25) {
    return "com o peso ideal";
  } else if (imc < 30) {
    return "com sobrepeso";
  } else {
    return "obeso";
  }
}
