----------------------------------------------------
**V.1.102.1 - firebase-setup-guide - 10/09/2026**
----------------------------------------------------
Eventos de carrinho (início de checkout, finalização, abandono e compra) agora geram um único registro, com valor total, quantidade total e a lista de produtos numa nova coluna items. Eventos por produto (visualização, adicionar/remover do carrinho) continuam individuais, e os relatórios do funil já leem os produtos de dentro dessa lista, mantendo compatibilidade com os dados antigos.

-- Tabela Supabase deve ser modificada. Adiciona coluna items na tabela product_events
ALTER TABLE public.product_events ADD COLUMN IF NOT EXISTS items jsonb;
