<div align="center">
  <img src="https://shields.io" alt="OSINT Badge">
  <img src="https://shields.io" alt="Python Badge">



   <div align="center">
  <img 
    src="assets/Have I Been Pwned.png"
    alt="Preview do projeto"
    width="800"
    height="400"
    style="object-fit: cover;"
  />
</div>


  <h1>🕵️‍♂️ Relatório OSINT & Automação Hunter.io</h1>

  <p>
    <b>Laboratório prático de footprinting passivo, mapeamento de superfície de ataque e análise de vazamento de credenciais.</b>
  </p>

  <p><i>Este repositório documenta técnicas de inteligência de fontes abertas e inclui um script automatizado de terminal para auditoria de domínios corporativos.</i></p>
</div>

<hr>

## 📊 Relatório Técnico de Reconhecimento

Este relatório consolida as descobertas obtidas durante a fase de inteligência de fontes abertas (OSINT) aplicada ao ambiente alvo para analisar a exposição de identidades corporativas na internet.

### 1. Resumo Executivo
*   **Organização Alvo:** Banco do Nordeste do Brasil (BNB)
*   **Domínio Investigado:** `bnb.gov.br`
*   **Técnica Aplicada:** Reconhecimento Passivo (Mapeamento de e-mails corporativos e análise de exposição externa).
*   **Total de E-mails Mapeados:** 5 endereços institucionais identificados.
*   **Contas com Alerta de Exposição:** 1 e-mail associado a supostos vazamentos históricos no ecossistema da Dark Web.
*   **Nível de Severidade Inicial:** <span style="color:orange">**MÉDIO**</span> (Alvo em potencial para engenharia social direcionada).

### 2. Metodologia de Coleta
O processo de reconhecimento foi executado através de auditoria assistida por ferramentas, cruzando duas etapas críticas:
1.  **Mapeamento de Estrutura:** Utilização da inteligência de dados da plataforma *Hunter.io* para isolar o padrão de e-mails legítimos do domínio alvo.
2.  **Validação de Incidentes:** Cruzamento manual de assinaturas digitais na base de dados global do *Have I Been Pwned* para identificar registros públicos expostos.

### 3. Cenários Globais de Ameaça Observados
A exposição de contas institucionais está diretamente atrelada a ameaças comuns que afetam organizações modernas:
*   **InfoStealers (Malwares de Roubo):** Coleta de credenciais salvas em navegadores de máquinas infectadas por vírus.
*   **Vazamentos de Plataformas Terceiras:** Quebras de segurança em ambientes de ensino (e-learning), eventos ou serviços externos onde o funcionário utilizou o e-mail corporativo para cadastro.
*   **Compilações de Fóruns (Combo Lists):** Agrupamento de bancos de dados antigos disponibilizados em canais maliciosos e fóruns cibernéticos.

---

## 🛠️ Automação: Ferramenta Hunter-Terminal (CLI)

Para otimizar o processo de footprinting e viabilizar auditorias rápidas diretamente pela linha de comando, foi desenvolvido um script robusto em **Python 3** sem dependências externas (utilizando apenas módulos nativos).

### ⚙️ Funcionalidades do Script
*   `setup`: Salva de forma segura sua chave de API ocultando a digitação (`getpass`) e restringindo permissões de leitura no arquivo local (`chmod 600`).
*   `domain`: Realiza a busca detalhada de e-mails válidos indexados para qualquer domínio informado.
*   `find`: Tenta deduzir o e-mail exato de um funcionário com base no Primeiro Nome, Sobrenome e Domínio.
*   `verify`: Executa uma checagem de entregabilidade e status de um e-mail específico.
*   `account`: Exibe os dados da sua conta e o consumo atual de créditos da API.

### 🚀 Como Configurar e Utilizar

**1. Instalação:**
Salve o arquivo do script no seu ambiente com o nome `hunter_cli.py` e conceda permissão de execução:
```bash
chmod +x hunter_cli.py
```

**2. Configuração Inicial:**
Execute o comando de setup para salvar sua credencial do Hunter.io com segurança:
```bash
./hunter_cli.py setup
```

**3. Exemplos de Uso Prático:**

*   **Mapear e-mails de um domínio corporativo:**
    ```bash
    ./hunter_cli.py domain bnb.gov.br --limit 5
    ```

*   **Verificar a validade de uma conta específica:**
    ```bash
    ./hunter_cli.py verify teste@dominio.com
    ```

*   **Consultar saldo de créditos restantes:**
    ```bash
    ./hunter_cli.py account
    ```

---

## ⚖️ Aviso Legal (Disclaimer)

Este projeto foi desenvolvido estritamente para **fins educacionais e de estudo acadêmico de segurança cibernética**. Toda a coleta de informações foi realizada em fontes públicas de dados abertos (OSINT) e de forma puramente passiva. Nenhuma tentativa de intrusão, quebra de criptografia, engenharia reversa de senhas ou acesso não autorizado a sistemas foi realizada. O autor não se responsabiliza pelo uso indevido das técnicas e ferramentas descritas neste repositório.
