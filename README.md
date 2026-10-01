# 🛒 VulnShop

> Laboratório de segurança ofensiva e defensiva em uma aplicação de e-commerce **deliberadamente vulnerável**.

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)
![License](https://img.shields.io/badge/license-MIT-blue)
![Security](https://img.shields.io/badge/purpose-educational-red)

---

## ⚠️ Aviso

Este projeto foi criado **exclusivamente para fins educacionais e de portfólio**, no contexto de um laboratório controlado de segurança ofensiva (Red Team) e defensiva (Blue Team).

- **Não** faça deploy desta aplicação em ambiente de produção.
- **Não** utilize as técnicas demonstradas aqui contra sistemas de terceiros sem autorização explícita.
- Todas as vulnerabilidades presentes são **intencionais**, documentadas e usadas apenas para fins de estudo e demonstração.

---

## 🎯 Objetivo

Construir uma aplicação de e-commerce funcional, identificar vulnerabilidades de segurança através de testes de invasão, corrigi-las e validar as correções através de um novo ciclo de testes — documentando todo o processo de ponta a ponta (encontrar → explorar → corrigir → validar).

O projeto simula um fluxo real de trabalho colaborativo entre:

- 🔴 **Red Team** — ofensivo, responsável por identificar e explorar vulnerabilidades
- 🔵 **Blue Team** — defensivo, responsável por construir a aplicação e aplicar as correções

---

## 👥 Equipe e papéis

| | Red Team (Ofensivo) | Blue Team (Defensivo) |
|---|---|---|
| **Responsável** | Alysson | Pedro e Guilherme |
| **Foco** | Pentest, exploração, documentação de vulnerabilidades | Desenvolvimento da aplicação, banco de dados, correções |
| **Entregas** | Relatórios de pentest (v1 e v2), PoCs, metodologia de teste | Aplicação funcional, schema do banco, patches de segurança |

Veja o detalhamento completo de responsabilidades em [`docs/architecture.md`](docs/architecture.md).

---

## 🏗️ Arquitetura

```
vulnshop/
├── app/
│   ├── backend/          # API REST
│   ├── frontend/         # Interface web
│   └── database/         # Scripts SQL, seeds, migrations
├── docs/
│   ├── architecture.md   # Arquitetura técnica do sistema
│   ├── threat-model.md   # Modelagem de ameaças
│   └── setup.md          # Guia de instalação e execução
├── security/
│   ├── vulnerabilities/  # Uma ficha técnica por vulnerabilidade
│   ├── evidence/         # Screenshots, requests/responses (PoCs)
│   ├── pentest-report-v1.md  # Relatório do estado vulnerável
│   └── pentest-report-v2.md  # Relatório pós-correção
├── docker-compose.yml
└── CHANGELOG.md
```

---

## 🛠️ Stack técnica

**Aplicação**
- Backend: Node.js (Express)
- Frontend: React
- Banco de dados: PostgreSQL
- Infraestrutura: Docker + Docker Compose

**Testes de segurança**
- Burp Suite Community
- OWASP ZAP
- sqlmap
- Postman

---

## 🐞 Vulnerabilidades trabalhadas

Baseado no OWASP Top 10, mapeadas neste projeto:

| ID | Vulnerabilidade | Local | Status |
|---|---|---|---|
| VULN-001 | SQL Injection | Login | 🔴 Aberto |
| VULN-002 | IDOR | Pedidos de usuário | 🔴 Aberto |
| VULN-003 | XSS Armazenado | Comentários/avaliações | 🔴 Aberto |
| VULN-004 | Broken Access Control | Painel admin | 🔴 Aberto |
| VULN-005 | Autenticação fraca | Senha/JWT | 🔴 Aberto |
| VULN-006 | Exposição de dados sensíveis | API de usuários | 🔴 Aberto |
| VULN-007 | CSRF | Checkout | 🔴 Aberto |
| VULN-008 | Upload inseguro de arquivo | Foto de perfil | 🔴 Aberto |

Status será atualizado para 🟢 Corrigido conforme o ciclo de correção/reteste avançar. Detalhes de cada uma em [`security/vulnerabilities/`](security/vulnerabilities/).

---

## 🔄 Metodologia

1. **Planejamento** — definição de escopo, arquitetura e vulnerabilidades-alvo
2. **Construção (v1)** — Blue Team desenvolve a aplicação com as falhas propositais
3. **Pentest (v1)** — Red Team executa testes seguindo o OWASP Testing Guide e documenta achados
4. **Correção** — Blue Team aplica as remediações com base no relatório
5. **Reteste (v2)** — Red Team valida se as correções eliminaram as vulnerabilidades
6. **Documentação final** — comparação antes/depois, relatório final e publicação

---

## 🚀 Como rodar o projeto

```bash
git clone https://github.com/alysonovv/vulnshop.git
cd vulnshop
docker-compose up --build
```

Guia completo de instalação em [`docs/setup.md`](docs/setup.md).

---

## 📄 Licença

Este projeto está sob a licença MIT — veja [LICENSE](LICENSE) para mais detalhes.

---

## 📬 Contato

- Alysson — Red Team — [[LinkedIn]](https://www.linkedin.com/in/alysson-paulino/) | [[GitHub]](https://github.com/alysonovv/)
- Pedro — Blue Team — [[LinkedIn]](https://www.linkedin.com/in/psousadev7/) | [[GitHub]](https://github.com/SousaDev7)
- Guilherme - Blue Team [[LinkedIn]](https://www.linkedin.com/in/guilherme-de-aquino-9829b0263/) | [[GitHub]](https://github.com/GuilhermeDeAquino)
