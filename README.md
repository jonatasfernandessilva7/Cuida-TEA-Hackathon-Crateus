# CUIDA TEA

Protótipo funcional de sistema informatizado para gestão do cuidado a pessoas com Transtorno do Espectro Autista (TEA) na rede pública de saúde de Crateús-CE.

Desenvolvido para o hackathon proposto pela Secretaria Municipal de Planejamento e Tecnologia da Informação (SEPLATI) em parceria com a Secretaria Municipal de Saúde de Crateús-CE.

## Contexto

A rede municipal de Crateús (NASF, NAPE, CREAES, Casa Mais Azul e CRASF) hoje não possui um sistema informatizado único para gerenciar o atendimento a pacientes com TEA. Os registros são feitos em papel, fragmentados entre os serviços, o que gera:

* Duplicidade de cadastros e de atendimentos;
* Ausência de histórico único e compartilhado entre os profissionais;
* Dificuldade de gerenciar filas de atendimento multidisciplinar;
* Falta de indicadores para gestão da rede.

## O que o protótipo resolve

O CUIDA TEA centraliza as quatro frentes exigidas no edital do hackathon:

1. **Gestão informatizada da fila de atendimento multidisciplinar** — fila unificada, ordenada por tempo de espera e prioridade clínica/social, com ação de registrar atendimento.
2. **Identificação de duplicidade de atendimento** — ao cadastrar um paciente, o sistema verifica automaticamente se já existe um registro pelo CNS ou CPF do responsável, evitando reabertura de prontuário.
3. **Registro sistemático e contínuo do histórico do paciente** — linha do tempo por paciente, com todos os atendimentos, tipo de intervenção e confirmação de comparecimento/falta.
4. **Integração entre os serviços da rede** — o cadastro do paciente é único e visível para todos os serviços (NASF, NAPE, CREAES, Casa Mais Azul, CRASF), evitando fragmentação da informação.

## Telas incluídas

|Tela|Descrição|
|-|-|
|Acesso ao Portal|Login institucional por CPF/matrícula e seleção da unidade de atendimento|
|Painel Geral|Indicadores da unidade, atalhos rápidos, próximos atendimentos e alertas da rede|
|Pacientes \& Prontuário|Cadastro único de paciente com verificação de duplicidade + histórico/timeline|
|Servidores \& Escalas|Cadastro de profissionais da rede municipal e listagem de vínculos|
|Agendamentos \& Frequência|Agenda semanal multidisciplinar com status de confirmação/falta|
|Fila de Espera \& Priorização|Fila unificada de regulação, ordenada por tempo de espera e prioridade|

## Stack técnica

Protótipo construído como uma **aplicação de página única (SPA)** em HTML, CSS e JavaScript puro (vanilla), sem dependências de build ou backend — o que permite rodar em qualquer navegador apenas abrindo o arquivo, ideal para demonstração em tempo de hackathon.

* **HTML5 + CSS3** — layout responsivo (desktop e mobile), com tokens de cor e tipografia (Inter via Google Fonts)
* **JavaScript (ES6)** — toda a lógica de navegação, formulários, verificação de duplicidade, fila e agenda roda no cliente, com dados de demonstração (mock) mantidos em memória
* Nenhuma biblioteca externa além da fonte Inter (Google Fonts)

> \*\*Nota:\*\* os dados exibidos (pacientes, profissionais, fila, agenda) são fictícios, usados apenas para demonstração. Para uma versão de produção, o próximo passo seria conectar este front-end a uma API real (ex.: Node.js/Express + PostgreSQL) com persistência de dados, autenticação real e conformidade com a LGPD.

## Como rodar localmente

Não há dependências. Basta abrir o arquivo no navegador:

```bash
# Clone o repositório
git clone <url-do-repositorio>
cd cuida-tea

# Abra o arquivo diretamente no navegador
open index.html      # macOS
xdg-open index.html  # Linux
start index.html     # Windows
```

Ou sirva localmente com qualquer servidor estático:

```bash
python3 -m http.server 8000
# acesse http://localhost:8000/index.html
```

## Estrutura do repositório sugerida

```
cuida-tea/
├── index.html      # aplicação completa (HTML + CSS + JS)
└── README.md        # este arquivo
```

## Requisitos funcionais mínimos atendidos (conforme edital)

* \[x] Cadastro único do usuário/paciente, evitando duplicidade de registros
* \[x] Fila de atendimento visível e priorizável por serviço
* \[x] Linha do tempo de atendimentos por paciente (histórico)
* \[x] Registro de comparecimento/falta em cada atendimento
* \[x] Painel de indicadores básicos (nº de atendimentos, faltas, encaminhamentos ativos)
* \[ ] Mecanismo de compartilhamento de informações entre os serviços com conformidade LGPD — modelado na camada de dados do protótipo (paciente vinculado a múltiplos serviços); a implementação de controle de acesso e auditoria de dados sensíveis fica para a fase de produção

## Autoria

Protótipo desenvolvido pela equipe Baixa Imunidade, para o Hackathon Banco do Nordeste / UFC / Prefeitura de Crateús-CE, a partir do tema proposto pela SEPLATI (13/09/2026).

