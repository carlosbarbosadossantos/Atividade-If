#!/bin/bash
 
echo "Entre com o primeiro numero:"
read num1
 
echo "Entre com o segundo número:"
read num2

echo "Escolha uma operação:"
echo "1) Adição"
echo "2) Subtração"
echo "3) Multiplicação"
echo "4) Divisao"
read operacao

if [ $operacao -eq 1 ]; then
    resultado=$(echo "$num1 + $num2" | bc)
    echo "Resultado: $resultado"
elif [ $operacao -eq 2 ]; then
    resultado=$(echo "$num1 - $num2" | bc)
    echo "Resultado: $resultado"
elif [ $operacao -eq 3 ]; then
    resultado=$(echo "$num1 * $num2" | bc)
    echo "Resultado: $resultado"
elif [ $operacao -eq 4 ]; then
    if [ $num2 -eq 0 ]; then
        echo "Erro: Não é possível dividir por zero."
    else
        resultado=$(echo "scale=2; $num1 / $num2" | bc)
        echo "Resultado: $resultado"
    fi
else
    echo "Opção inválida."
fi

