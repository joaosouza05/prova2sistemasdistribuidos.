# prova-pratica-sistemas-distribuidos-p2 

Evidencia 2

Alteração no limite de concorrência

Foi alterada a configuração MAXIMO_SIMULTANEO de 3 para 2, utilizando threading.Semaphore(2).

Motivo: adequar o sistema à regra da empresa, que permite apenas dois pedidos em processamento simultâneo. O terceiro pedido deverá aguardar a liberação de uma vaga.

Evidencia 3 

Foi corrigida a função sincronizar() para que a réplica receba o estoque atualizado do servidor principal, em vez de copiar seus próprios dados. Também foi ajustada a função

consultar_estoque() para que, em caso de falha do servidor principal, o sistema consulte automaticamente a réplica, garantindo a continuidade das consultas.

Evidencia 4

Foram realizadas três alterações no sistema:

1. Controle de concorrência: o limite de processamento simultâneo foi reduzido de 3 para 2 pedidos, conforme a regra estabelecida pela empresa. O terceiro pedido precisa
  
 aguardar a liberação de uma vaga.

2. Sincronização: a função sincronizar() foi corrigida para copiar o estoque atualizado do servidor principal para a réplica, mantendo os dados iguais.

3.Consulta de estoque: a função consultar_estoque() foi corrigida para consultar a réplica automaticamente quando o servidor principal estiver offline.

Comportamento após as alterações: o sistema passou a respeitar o limite de dois pedidos simultâneos, manter o estoque da réplica atualizado e permitir consultas mesmo 

quando o

servidor principal apresentar falhas.

5. Questões:

1. Qual é a função do semáforo no processamento de pedidos?

O semáforo controla a quantidade de pedidos processados simultaneamente. No programa, foi configurado para permitir apenas dois pedidos ao mesmo tempo, conforme a regra 

estabelecida pela empresa. Os demais precisam aguardar a liberação de uma vaga.

2. Por que é necessário sincronizar os dados entre o servidor principal e a réplica?

Para manter os dados atualizados e iguais nos dois servidores. Assim, se o servidor principal apresentar uma falha, a réplica poderá fornecer informações corretas sobre o 

estoque.

3. O que significa tolerância a falhas e como ela aparece neste programa?

Tolerância a falhas é a capacidade de um sistema continuar funcionando mesmo quando ocorre uma falha em algum componente. No programa, isso acontece quando o servidor 

principal fica offline e o sistema utiliza a réplica para consultar o estoque.

4. Para que serve o Lock no programa e como o controle de acesso aos recursos ajuda a prevenir problemas de concorrência?

O Lock impede que duas threads alterem o estoque ao mesmo tempo. Isso evita problemas como descontos duplicados ou valores incorretos no estoque, garantindo que cada pedido

atualize os dados de forma segura.

5. Considerando a sequência de eventos, a sincronização do estoque deve acontecer antes ou depois do processamento dos pedidos? Explique a relação de causalidade.

A sincronização deve acontecer depois do processamento dos pedidos, pois primeiro o servidor principal precisa atualizar o estoque com os descontos dos pedidos confirmados.

Depois, a réplica recebe o valor atualizado. Dessa forma, se o servidor principal falhar, a réplica terá a informação mais recente do estoque.




