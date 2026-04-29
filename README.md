# 🛡️ AWS Security Hub Fundamentals - Study Notes

Bem-vindo ao meu repositório de estudos sobre o **AWS Security Hub**. Este projeto documenta meu aprendizado prático, testes de laboratório e estratégias de hardening utilizando o Security Hub como orquestrador central de postura de segurança na AWS.

## 📌 Visão Geral
O AWS Security Hub é um serviço que centraliza alertas de segurança (findings) de vários serviços AWS e parceiros. Ele verifica o ambiente contra padrões de conformidade e melhores práticas da indústria.


---

## 🏗️ Estrutura do Repositório

- `/docs`: Conceitos teóricos e notas de estudo.
- `/images`: Prints de console anotados e diagramas.
- `/labs`: Cenários de ataque e remediação testados.
- `/scripts`: Trechos de Terraform e AWS CLI para automação.

---

## 🚀 Principais Conceitos Estudados

### 1. Padrões de Segurança (Security Standards)
Foco nos benchmarks que o serviço utiliza para avaliar as contas:
- **AWS Foundational Security Best Practices:** O conjunto básico de controles da AWS.
- **CIS AWS Foundations Benchmark:** Padrão ouro da indústria.
- **PCI DSS:** Controles para conformidade com cartões de crédito.

### 2. Gerenciamento de Findings
Documentação do ciclo de vida de um achado:
- **Severidade:** Critical, High, Medium, Low e Informational.
- **Workflow Status:** `NEW` -> `NOTIFIED` -> `RESOLVED` ou `SUPPRESSED`.

---

## 🧪 Laboratórios Práticos (Labs)

### Lab 01: Identificação de Buckets S3 Públicos
- **Objetivo:** Detectar via Security Hub um bucket configurado incorretamente.
- **Status:** ✅ Concluído
- **Notas:** [Link para o Lab 01](./labs/lab01-s3-public.md)

### Lab 02: Remediação com EventBridge + Lambda
- **Objetivo:** Automatizar a correção de um security group aberto na porta 22 (SSH).
- **Status:** ⏳ Em progresso

---

## 🛠️ Comandos Úteis (CLI Cheat Sheet)

```bash
# Verificar o status de habilitação do Security Hub
aws securityhub describe-hub

# Listar todos os controles de um padrão específico
aws securityhub describe-standards-controls --standards-control-association-arn "ARN_AQUI"

# Filtrar findings críticos
aws securityhub get-findings --filters '{"SeverityLabel": [{"Value": "CRITICAL", "Comparison": "EQUALS"}]}'