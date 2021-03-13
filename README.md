# CalculadoraFV
Fórmula para conversão de taxa de juros anual para mensal
iM=(√(12&(1+iA) ))-1
Onde:
	iM = taxa mensal
	iA = taxa anual
Como a biblioteca de javascript não trabalha com radiciação, podemos converter essa fórmula para potenciação, conforme demonstrado abaixo:
iM%=((1+iA%)^(1/12) )-1
Código equivalente:
 var i = ((Math.pow((1+(i/100)),(1/12)))-1)*100
OBS: no final foi multiplicado por 100 para colocar o resultado em formato de por cento novamente.
Fórmula para valor futuro com aporte mensal
FV=(PMT*[(1+i)^n-1])/i
Onde:
	FV = Valor futuro
	PMT = valor dos aportes mensais
	n = número de meses da aplicação
	i = taxa fixa %(a.m)
Fórmula para valor futuro
FV=PV*(1+i)^n
Onde:
	FV = Valor futuro
	PV = valor presente
	n = número de meses da aplicação
	i = taxa fixa %(a.m)
Portanto, para calcular o valor futuro de uma aplicação com aportes mensais e valor inicial temos:
FV=((PMT*[(1+i)^n-1])/i)+PV*(1+i)^n
Código equivalente:
function FV(PMT, i, n, PV) {
          var i = i / 100 //converter porcentagem
          return ((PV * (Math.pow(1+i, n)))) + ((PMT * (Math.pow(1 + i, n) - 1)) / i)
        }
Referência:
https://blog.rico.com.vc/juros-compostos-o-que-sao
https://www.somatematica.com.br/emedio/finan9.php
https://www.capitalresearch.com.br/blog/investimentos/taxa-anual-para-mensal-calcular/
