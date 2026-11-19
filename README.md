# prova-pratica-sistemas-distribuidos-p2 

Evidencia 2

Alteração no limite de concorrência

Foi alterada a configuração MAXIMO_SIMULTANEO de 3 para 2, utilizando threading.Semaphore(2).

Motivo: adequar o sistema à regra da empresa, que permite apenas dois pedidos em processamento simultâneo. O terceiro pedido deverá aguardar a liberação de uma vaga.
