# 📋 LISTA COMPLETA DE ENDPOINTS

## 👤 **GESTÃO DE CONTAS**
- `GET /api/account/profile` - Buscar dados do perfil do usuário
- `GET /api/account/bank-data` - Buscar dados bancários para compartilhamento
- `GET /api/user/personal-data` - Buscar dados pessoais
- `PUT /api/user/social-name` - Alterar nome social
- `PUT /api/user/email` - Alterar e-mail (envia código de validação)
- `PUT /api/user/phone` - Alterar celular (envia código de validação)
- `POST /api/user/validate-change` - Validar código de alteração (e-mail/celular)
- `GET /api/account/balance` - Verificar saldo para encerramento
- `GET /api/account/closure-reasons` - Listar motivos de encerramento
- `POST /api/account/close` - Encerrar conta

## 🔐 **SENHAS E SEGURANÇA**
- `POST /api/auth/validate-password` - Validar senha atual
- `PUT /api/auth/change-app-password` - Alterar senha do aplicativo
- `PUT /api/auth/change-transaction-password` - Alterar senha transacional
- `POST /api/auth/forgot-password` - Esqueci senha (envia código)
- `POST /api/auth/reset-password` - Resetar senha com código
- `PUT /api/auth/biometry` - Habilitar/desabilitar biometria

## 💳 **GESTÃO DE CARTÕES**
- `GET /api/cards` - Listar todos os cartões do usuário
- `GET /api/cards/{card_id}` - Detalhes de um cartão específico
- `POST /api/cards/virtual` - Criar novo cartão virtual
- `PUT /api/cards/virtual/{card_id}/regenerate` - Atualizar número do cartão virtual
- `GET /api/cards/{card_id}/details` - Ver dados completos do cartão (com senha)
- `POST /api/cards/physical/request` - Solicitar cartão físico
- `POST /api/cards/physical/{card_id}/activate` - Ativar cartão físico
- `POST /api/cards/physical/{card_id}/replacement` - Solicitar segunda via
- `PUT /api/cards/{card_id}/block` - Bloquear cartão
- `PUT /api/cards/{card_id}/settings` - Configurações do cartão
- `DELETE /api/cards/virtual/{card_id}` - Excluir cartão virtual
- `GET /api/cards/fees` - Consultar taxas de cartões
- `POST /api/cards/fees/calculate` - Calcular custo antes da solicitação
- `GET /api/cards/{card_id}/transactions` - Extrato do cartão
- `GET /api/cards/{card_id}/limits` - Consultar limites do cartão
- `GET /api/cards/{card_id}/status` - Status detalhado do cartão

## 🔑 **CHAVES PIX**
- `GET /api/pix/keys` - Listar chaves do usuário
- `POST /api/pix/keys` - Criar nova chave PIX
- `POST /api/pix/keys/{key_id}/validate` - Validar chave (SMS/Email)
- `DELETE /api/pix/keys/{key_id}` - Excluir chave PIX
- `POST /api/pix/keys/{key_id}/share` - Compartilhar chave
- `POST /api/pix/keys/portability/request` - Solicitar portabilidade (trazer chave)
- `POST /api/pix/keys/{key_id}/portability/approve` - Aprovar saída de chave
- `GET /api/pix/keys/portability/pending` - Listar solicitações pendentes

## 💸 **PIX TRANSAÇÕES**
- `POST /api/pix/validate-recipient` - Validar destinatário
- `POST /api/pix/send` - Enviar PIX
- `POST /api/pix/send/validate` - Validar antes de enviar (saldo, limites)
- `POST /api/pix/schedule` - Agendar PIX
- `GET /api/pix/scheduled` - Listar PIX agendados
- `DELETE /api/pix/scheduled/{id}` - Cancelar PIX agendado
- `POST /api/pix/recurring` - Criar PIX recorrente
- `GET /api/pix/recurring` - Listar PIX recorrentes
- `PUT /api/pix/recurring/{id}/pause` - Pausar/reativar recorrente

## 📱 **PIX RECEBIMENTO**
- `POST /api/pix/qrcode/generate` - Gerar QR Code para recebimento
- `GET /api/pix/qrcode/{qr_id}/status` - Status da cobrança
- `GET /api/pix/contacts/recent` - Contatos recentes
- `POST /api/pix/contacts/{contact_id}/favorite` - Marcar como favorito
- `DELETE /api/pix/contacts/{contact_id}` - Remover contato

## 📊 **PIX RELATÓRIOS**
- `GET /api/pix/statement` - Extrato PIX
- `GET /api/pix/limits` - Consultar limites PIX
- `PUT /api/pix/limits/request-change` - Solicitar alteração de limite
- `GET /api/pix/receipt/{transaction_id}` - Gerar comprovante
- `POST /api/pix/receipt/{transaction_id}/share` - Compartilhar comprovante

## 📍 **ENDEREÇOS**
- `GET /api/user/addresses` - Listar endereços salvos
- `POST /api/user/addresses` - Adicionar novo endereço
- `POST /api/addresses/validate` - Validar endereço (integração Google Places)

## ❓ **FAQ E SUPORTE**
- `GET /api/support/faq` - Listar perguntas frequentes
- `GET /api/support/faq/{category_id}` - Buscar FAQ por categoria
- `GET /api/support/search` - Buscar no FAQ
- `POST /api/support/faq/{question_id}/helpful` - Marcar pergunta como útil
- `GET /api/support/contact-info` - Informações de contato
- `POST /api/support/ticket` - Abrir ticket de suporte
- `GET /api/support/tickets` - Listar meus tickets
- `GET /api/support/tickets/{ticket_id}` - Detalhes do ticket

## 🔔 **WEBHOOKS**
- `POST /api/pix/notifications/webhook` - Receber notificações PIX da Dock
- `POST /api/cards/notifications/webhook` - Receber notificações de cartão da Dock

---

## 📊 **RESUMO POR PRIORIDADE**

### **🔥 MVP - Sprint 1 (33 endpoints)**
- Gestão básica de contas e senhas
- PIX enviar/receber básico
- Cartões virtual/físico essencial
- FAQ básico

### **⚡ Intermediário - Sprint 2 (25 endpoints)**
- PIX agendado/recorrente
- Cartões avançados
- Portabilidade PIX
- Sistema de suporte

### **📌 Avançado - Sprint 3 (15 endpoints)**
- Relatórios e extratos
- Webhooks completos
- Funcionalidades premium
