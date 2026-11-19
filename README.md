# prova-pratica-sistemas-distribuidos-p2 

Evidencia 2

Alteração no limite de concorrência

Foi alterada a configuração MAXIMO_SIMULTANEO de 3 para 2, utilizando threading.Semaphore(2).

Motivo: adequar o sistema à regra da empresa, que permite apenas dois pedidos em processamento simultâneo. O terceiro pedido deverá aguardar a liberação de uma vaga.

Evidencia 3 

Foi corrigida a função sincronizar() para que a réplica receba o estoque atualizado do servidor principal, em vez de copiar seus próprios dados. Também foi ajustada a função

consultar_estoque() para que, em caso de falha do servidor principal, o sistema consulte automaticamente a réplica, garantindo a continuidade das consultas.




