# 📋 LISTA COMPLETA DE ENDPOINTS

## 👤 **GESTÃO DE CONTAS**
- `GET /client/me` - Buscar dados do perfil do usuário - ok
- `GET /client/accounts` - Buscar dados bancários para compartilhamento - ok
- `PUT /client/social_name` - Alterar nome social - falta
- `PUT /client/email` - Alterar e-mail (envia código de validação) - falta
- `PUT /client/phone` - Alterar celular (envia código de validação) - falta
- `POST /api/user/validate_change` - Validar código de alteração (e-mail/celular) - falta
- `GET /api/account/balance/snapshot` - Verificar saldo para encerramento - ok
- `GET /api/account/closure_reasons` - Listar motivos de encerramento - falta
- `POST /api/account/{account_code}/close` - Encerrar conta - ok

## 🔐 **SENHAS E SEGURANÇA**
- `POST /client/auth/` - Validar senha atual - ok
- `PUT /api/auth/change_password` - Alterar senha do aplicativo - falta
- `POST /client/transaction_password` - Alterar e criar senha transacional - corrigir
- `POST /client/forgot_password` - Esqueci senha (envia código) - corrigir
- `POST /client/reset_password` - Resetar senha com código - corrigir
- `PUT /client/biometry` - Habilitar/desabilitar biometria - falta

## 💳 **GESTÃO DE CARTÕES**
- `GET /account/cards` - Listar todos os cartões do usuário - ok
- `GET /account/cards/{card_id}` - Detalhes de um cartão específico - ok
- `POST /account/cards/{card_id}/virtual` - Criar novo cartão virtual - ok
- `PUT /account/cards/virtual/{card_id}/regenerate` - Atualizar número do cartão virtual - falta
- `GET /account/cards/{card_id}/details` - Ver dados completos do cartão (com senha) - falta
- `POST /account/cards/physical/request` - Solicitar cartão físico - falta
- `POST /account/cards/physical/{card_id}/activate` - Ativar cartão físico - falta
- `POST /account/cards/physical/{card_id}/replacement` - Solicitar segunda via - falta
- `PUT /account/cards/{card_id}/block` - Bloquear cartão - falta (removendo de update)
- `PUT /account/cards/{card_id}/unblock ` - Desbloquear cartão - falta (removendo de update)
- `PUT /account/cards/{card_id}/settings` - Configurações do cartão - falta (contatless, etc)
- `DELETE /account/cards/virtual/{card_id}` - Excluir cartão virtual - falta
- `GET /account/cards/fees` - Consultar taxas de cartões - falta
- `POST /account/cards/fees/calculate` - Calcular custo antes da solicitação - falta
- `GET /account/cards/{card_id}/transactions` - Extrato do cartão - falta
- `GET /account/cards/{card_id}/limits` - Consultar limites do cartão - falta
- `PATCH /account/cards/{card_id}/status` - Atualizar Status do cartão - ok
- `GET /account/cards/{card_id}/status` - Status detalhado do cartão - falta

## 🔑 **CHAVES PIX**
- `GET /account/pix/keys` - Listar chaves do usuário - falta
- `POST /account/pix/keys` - Criar nova chave PIX - falta
- `POST /account/pix/keys/{key_id}/validate` - Validar chave (SMS/Email) - falta
- `DELETE /account/pix/keys/{key_id}` - Excluir chave PIX - falta
- `POST /account/pix/keys/{key_id}/share` - Compartilhar chave - falta
- `POST /account/pix/keys/portability/request` - Solicitar portabilidade (trazer chave) - falta
- `POST /account/pix/keys/{key_id}/portability/approve` - Aprovar saída de chave - falta
- `GET /account/pix/keys/portability/pending` - Listar solicitações pendentes - falta

## 💸 **PIX TRANSAÇÕES**
- `POST /account/pix/validate-recipient` - Validar destinatário - falta
- `POST /account/pix/send` - Enviar PIX - atualizar
- `POST /account/pix/send/validate` - Validar antes de enviar (saldo, limites)
- `POST /account/pix/schedule` - Agendar PIX - falta
- `GET /account/pix/scheduled` - Listar PIX agendados - falta
- `DELETE /account/pix/scheduled/{id}` - Cancelar PIX agendado - falta
- `POST /account/pix/recurring` - Criar PIX recorrente - falta
- `GET /account/pix/recurring` - Listar PIX recorrentes - falta
- `PUT /account/pix/recurring/{id}/pause` - Pausar/reativar recorrente - falta

## 📱 **PIX RECEBIMENTO**
- `POST /account/pix/qrcode/generate` - Gerar QR Code para recebimento - falta
- `GET /account/pix/qrcode/{qr_id}/status` - Status da cobrança - falta
- `GET /account/pix/contacts/recent` - Contatos recentes - falta
- `POST /account/pix/contacts/{contact_id}/favorite` - Marcar como favorito - falta
- `DELETE /account/pix/contacts/{contact_id}` - Remover contato - falta

## 📊 **PIX RELATÓRIOS**
- `GET /account/pix/statement` - Extrato PIX
- `GET /account/pix/limits` - Consultar limites PIX
- `PUT /account/pix/limits/request-change` - Solicitar alteração de limite
- `GET /account/pix/receipt/{transaction_id}` - Gerar comprovante
- `POST /account/pix/receipt/{transaction_id}/share` - Compartilhar comprovante

## 📍 **ENDEREÇOS**
- `GET /client/addresses` - Listar endereços salvos - falta
- `POST /client/addresses` - Adicionar novo endereço - falta
- `POST /client/addresses/validate` - Validar endereço (integração Google Places) - falta

## ❓ **FAQ E SUPORTE**
- `GET /oraganization/support/faq` - Listar perguntas frequentes - falta
- `GET /oraganization/support/faq/{category_id}` - Buscar FAQ por categoria - falta
- `GET /oraganization/support/search` - Buscar no FAQ - falta
- `GET /oraganization/support/contact-info` - Informações de contato - falta

## 🔔 **WEBHOOKS**
- `POST /account/pix/notifications/webhook` - Receber notificações PIX da Dock
- `POST /account/cards/notifications/webhook` - Receber notificações de cartão da Dock
