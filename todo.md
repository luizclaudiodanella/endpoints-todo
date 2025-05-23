# LISTA COMPLETA DE ENDPOINTS

## **GESTÃO DE CONTAS**
- ✅ `GET /client/me` - Buscar dados do perfil do usuário
- ✅ `GET /client/accounts` - Buscar dados bancários para compartilhamento
- ❌ `PUT /client/social_name` - Alterar nome social
- ❌ `PUT /client/email` - Alterar e-mail (envia código de validação)
- ❌ `PUT /client/phone` - Alterar celular (envia código de validação)
- ❌ `POST /client/validate_change` - Validar código de alteração (e-mail/celular)
- ✅ `GET /account/balance/snapshot` - Verificar saldo para encerramento
- ❌ `GET /account/closure_reasons` - Listar motivos de encerramento
- ✅ `POST /account/{account_code}/close` - Encerrar conta

## **SENHAS E SEGURANÇA**
- ✅ `POST /client/auth/` - Validar senha atual
- ❌ `PUT /client/change_password` - Alterar senha do aplicativo
- 🔧 `POST /client/transaction_password` - Alterar e criar senha transacional
- 🔧 `POST /client/forgot_password` - Esqueci senha (envia código)
- 🔧 `POST /client/reset_password` - Resetar senha com código
- ❌ `PUT /client/biometry` - Habilitar/desabilitar biometria

## **GESTÃO DE CARTÕES**
- ✅ `GET /account/cards` - Listar todos os cartões do usuário
- ✅ `GET /account/cards/{card_id}` - Detalhes de um cartão específico
- ✅ `POST /account/cards/{card_id}/virtual` - Criar novo cartão virtual
- ❌ `PUT /account/cards/virtual/{card_id}/regenerate` - Atualizar número do cartão virtual
- ❌ `GET /account/cards/{card_id}/details` - Ver dados completos do cartão (com senha)
- ❌ `POST /account/cards/physical/request` - Solicitar cartão físico
- ❌ `POST /account/cards/physical/{card_id}/activate` - Ativar cartão físico
- ❌ `POST /account/cards/physical/{card_id}/replacement` - Solicitar segunda via
- ❌ `PUT /account/cards/{card_id}/block` - Bloquear cartão
- ❌ `PUT /account/cards/{card_id}/unblock` - Desbloquear cartão
- ❌ `PUT /account/cards/{card_id}/settings` - Configurações do cartão
- ❌ `DELETE /account/cards/virtual/{card_id}` - Excluir cartão virtual
- ❌ `GET /account/cards/fees` - Consultar taxas de cartões
- ❌ `POST /account/cards/fees/calculate` - Calcular custo antes da solicitação
- ❌ `GET /account/cards/{card_id}/transactions` - Extrato do cartão
- ❌ `GET /account/cards/{card_id}/limits` - Consultar limites do cartão
- ✅ `PATCH /account/cards/{card_id}/status` - Atualizar Status do cartão
- ❌ `GET /account/cards/{card_id}/status` - Status detalhado do cartão

## **CHAVES PIX**
- ❌ `GET /account/pix/keys` - Listar chaves do usuário
- ❌ `POST /account/pix/keys` - Criar nova chave PIX
- ❌ `POST /account/pix/keys/{key_id}/validate` - Validar chave (SMS/Email)
- ❌ `DELETE /account/pix/keys/{key_id}` - Excluir chave PIX
- ❌ `POST /account/pix/keys/{key_id}/share` - Compartilhar chave
- ❌ `POST /account/pix/keys/portability/request` - Solicitar portabilidade (trazer chave)
- ❌ `POST /account/pix/keys/{key_id}/portability/approve` - Aprovar saída de chave
- ❌ `GET /account/pix/keys/portability/pending` - Listar solicitações pendentes

## **PIX TRANSAÇÕES**
- ❌ `POST /account/pix/validate-recipient` - Validar destinatário
- 🔧 `POST /account/pix/send` - Enviar PIX
- ❌ `POST /account/pix/send/validate` - Validar antes de enviar (saldo, limites)
- ❌ `POST /account/pix/schedule` - Agendar PIX
- ❌ `GET /account/pix/scheduled` - Listar PIX agendados
- ❌ `DELETE /account/pix/scheduled/{id}` - Cancelar PIX agendado
- ❌ `POST /account/pix/recurring` - Criar PIX recorrente
- ❌ `GET /account/pix/recurring` - Listar PIX recorrentes
- ❌ `PUT /account/pix/recurring/{id}/pause` - Pausar/reativar recorrente

## **PIX RECEBIMENTO**
- ❌ `POST /account/pix/qrcode/generate` - Gerar QR Code para recebimento
- ❌ `GET /account/pix/qrcode/{qr_id}/status` - Status da cobrança
- ❌ `GET /account/pix/contacts/recent` - Contatos recentes
- ❌ `POST /account/pix/contacts/{contact_id}/favorite` - Marcar como favorito
- ❌ `DELETE /account/pix/contacts/{contact_id}` - Remover contato

## **PIX RELATÓRIOS**
- ❌ `GET /account/pix/statement` - Extrato PIX
- ❌ `GET /account/pix/limits` - Consultar limites PIX
- ❌ `PUT /account/pix/limits/request-change` - Solicitar alteração de limite
- ❌ `GET /account/pix/receipt/{transaction_id}` - Gerar comprovante
- ❌ `POST /account/pix/receipt/{transaction_id}/share` - Compartilhar comprovante

## **ENDEREÇOS**
- ❌ `GET /client/addresses` - Listar endereços salvos
- ❌ `POST /client/addresses` - Adicionar novo endereço
- ❌ `POST /client/addresses/validate` - Validar endereço (integração Google Places)

## **FAQ E SUPORTE**
- ❌ `GET /oraganization/support/faq` - Listar perguntas frequentes
- ❌ `GET /oraganization/support/faq/{category_id}` - Buscar FAQ por categoria
- ❌ `GET /oraganization/support/search` - Buscar no FAQ
- ❌ `GET /oraganization/support/contact-info` - Informações de contato

## **WEBHOOKS**
- ❌ `POST /account/pix/notifications/webhook` - Receber notificações PIX da Dock
- ❌ `POST /account/cards/notifications/webhook` - Receber notificações de cartão da Dock
