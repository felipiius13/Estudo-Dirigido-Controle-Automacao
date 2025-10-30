
# Resumo Teórico: Capítulo 6 - A Estabilidade de Sistemas Lineares

O Capítulo 6, "A Estabilidade de Sistemas Lineares com Realimentação", aborda o conceito mais crítico em sistemas de controle.

* **Conceito de Estabilidade:** Um sistema é considerado estável se, para qualquer entrada limitada, sua saída também for limitada (critério BIBO - Bounded-Input, Bounded-Output). Em termos práticos, um sistema estável é aquele cuja resposta a uma perturbação transitória retorna a um estado de equilíbrio. Um sistema instável terá uma saída que diverge, geralmente de forma oscilatória ou exponencial, podendo levar a falhas catastróficas.
* **Localização dos Polos:** A estabilidade de um sistema linear e invariante no tempo (LTI) é determinada pela localização dos polos de sua função de transferência de malha fechada no plano complexo 's'.
    * **Polos no semiplano esquerdo (parte real negativa):** O sistema é estável.
    * **Polos no semiplano direito (parte real positiva):** O sistema é instável.
    * **Polos no eixo imaginário:** O sistema é marginalmente estável (se não houver polos repetidos) ou instável (se houver polos repetidos).
* **Critério de Estabilidade de Routh-Hurwitz:** É um método analítico que permite determinar o número de polos de malha fechada no semiplano direito sem a necessidade de calcular os polos explicitamente. O critério se baseia na construção de um arranjo (tabela de Routh) a partir dos coeficientes do polinômio característico da equação do sistema. O número de trocas de sinal na primeira coluna do arranjo indica o número de raízes instáveis. É uma ferramenta poderosa para analisar a estabilidade em função de um ganho variável (K).

### Conexão com a Indústria 4.0

* **Confiabilidade em DCS e SIS (Safety Instrumented Systems):** A análise de estabilidade é a base da **confiabilidade** em sistemas de controle industrial. Em um **DCS (Distributed Control System)** que controla centenas de malhas em uma refinaria, um controlador mal sintonizado (um ganho `K` muito alto) pode levar uma malha à instabilidade, causando oscilações que se propagam pelo processo e podem levar a uma parada de produção. A situação é ainda mais crítica em um **SIS (Sistema Instrumentado de Segurança)**. Esses sistemas são projetados para levar o processo a um estado seguro em caso de falha. A instabilidade em um SIS é inaceitável, pois significa que o sistema de segurança falhou em sua função primária. O critério de Routh-Hurwitz é uma ferramenta clássica usada no projeto para garantir que, dentro da faixa operacional de ganhos, o sistema de segurança permaneça sempre estável.
