
---

<h1 align="center">Análise de Sobrevivência: Churn de Clientes</h1>

<p align="justify"><h3>1. Definição do Modelo Matemático</h3></p>

<p align="justify">A análise utiliza o <b>Modelo de Riscos Proporcionais de Cox</b> para estimar a probabilidade de um cliente permanecer ativo. A função de risco é definida pela equação:</p>

<p align="center">
<b>h(t | x) = h<sub>0</sub>(t) · exp(Σ β<sub>i</sub> · x<sub>i</sub>)</b>
</p>

<p align="justify">No contexto do notebook, o objetivo é encontrar os coeficientes <b>β</b> que determinam como variáveis como <i>MonthlyCharges</i> (Cobranças Mensais) e <i>tenure</i> (tempo de contrato) aumentam ou diminuem o risco de evasão.</p>

<p align="justify"><h3>2. A "Mágica" da Análise de Sobrevivência</h3></p>

<p align="justify">O grande trunfo de usar o modelo de Cox (via biblioteca <b>lifelines</b>) é que ele permite lidar com dados censurados e prever o comportamento futuro dos clientes com base em restrições e características específicas:</p>

* <p align="justify"><b>Efeito das Variáveis:</b> "Como o aumento de 10 reais na fatura mensal impacta a chance de o cliente cancelar o serviço?" (Estimativa de coeficientes).</p>
* <p align="justify"><b>Previsão Individualizada:</b> "Dada a configuração atual deste cliente, qual a probabilidade de ele ainda estar conosco daqui a 12 meses?" (Função de sobrevivência parcial).</p>
* <p align="justify"><b>Comparação de Perfis:</b> "Qual a diferença de retenção entre um cliente de 'Alto Uso' (60 meses, fatura de 90.00) versus um de 'Baixo Uso' (12 meses, fatura de 50.00)?"</p>

<p align="justify"><h3>3. Resultados e Observações</h3></p>

<p align="justify">A análise conduzida no código revelou que o comportamento de <i>churn</i> no dataset Telco é relativamente linear. Foi observado que:</p>

* <p align="justify"><b>Curvas de Sobrevivência:</b> Clientes com maior tempo de casa (<i>tenure</i>) e contas mais altas tendem a apresentar uma probabilidade de sobrevivência significativamente maior, indicando que o valor da conta pode estar atrelado a pacotes de serviços que geram maior fidelidade (como combos).</p>
* <p align="justify"><b>Aplicações Práticas:</b> O modelo permite que a empresa identifique preventivamente clientes em zonas de risco e formule estratégias de retenção personalizadas antes que o evento de <i>churn</i> ocorra.</p>

---
