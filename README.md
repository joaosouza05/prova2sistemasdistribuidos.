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




