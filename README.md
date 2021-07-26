# tcc-datascience


select 
n.ID_NF                                identificador_nota_fiscal,
n.DT_EMISSAO                           data_emissao,          
n.CD_OPERACAO_FISCAL                   operacao_fiscal,     
n.CD_TIPO_TRANSACAO                    tipo_transacao,     
n.CD_TELEVENDA                         codigo_pedido_multicanal,
n.CD_FILIAL                            codigo_filial,
n.CD_TRANSACAO_CLIENTE                 transacao_cliente,
n.CD_ORIGEM_NF                         codigo_nota_fiscal_origem,
n.CD_FORMA_PAGTO                       forma_pagamento,     
n.VL_NF                                valor_nota_fiscal,  
n.NR_NF                                numero_nota_fiscal,    
n.DT_ATUALIZACAO                       data_atualizacao,
f.FL_24H                       loja_24h,
e.SG_ESTADO                              estado,
DS_ENDERECO                            endereco,
DS_BAIRRO                              bairro,
DS_CIDADE                              cidade,
NR_CEP                                 cep

FROM TB_NF n, TB_FILIAL F, TB_ENDERECO_GERAL e
WHERE  n.cd_filial = f.cd_filial
AND n.cd_filial = e.cd_filial
AND n.CD_OPERACAO_FISCAL = 1
AND n.DT_EMISSAO BETWEEN TO_DATE('01/01/2011','dd/mm/yyyy') and TO_DATE('31/12/2011','dd/mm/yyyy')

