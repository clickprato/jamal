----------------------------------------------------
**V. 1.63.1 - burger-menu-online - 20/08/2026**
----------------------------------------------------
Aplicada a normalização para o formato só dígitos de whatsapp/telefone em todas as tabelas que usam, ex. 5511512345678, via phoneDigitsBr antes de gravar):

Tabelas Supabase:
"profiles"
"users"
"fidelidade_progresso"
"fidelidade_histórico"
"pedidos_sabor_delivery"

Arquivos Alterados:
src/services/orderService.ts — telefone_cliente no insert de pedidos
src/services/fidelidadeService.ts — telefone normalizado no início de verificarFidelidade (afeta fidelidade_progresso e fidelidade_historico)
src/services/customerService.ts — telefone normalizado ao salvar/atualizar customer_data (e espelho em users)
src/services/authService.ts — telefone no metadata do signup (chega em profiles/users pelo trigger)
src/components/ProfileDrawer.tsx — updates de users e profiles
src/pages/Checkout.tsx — upsert em profiles e updateRegisteredPhone 
