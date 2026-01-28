# 🧾 Evolução de Software - Etapa 3: Auditoria de CI/CD

## 🎯 Objetivo

Avaliar a maturidade da infraestrutura de automação (CI/CD) do projeto **Screenpipe** e analisar como ela impacta a capacidade de evolução segura do software.

## 🔍 Cenário Identificado: Cenário A (Auditores de Processo)

O projeto analisado **já implementa CI/CD**. Identificamos fluxos de trabalho automatizados para Build, Testes (Unitários e E2E), Linting e Release.

## 🛠️ Artefatos Coletados

Os seguintes workflows foram extraídos para análise nesta auditoria:

- **Integração Contínua (CI):** `ci.yml`, `build-core-pipes.yml`
- **Qualidade de Código:** `style.yml` (Lint/Format)
- **Testes Automatizados:** `e2e-test.yml`, `linux-integration-test.yml`, `benchmark.yml`
- **Entrega Contínua (CD):** `release-app.yml`, `release-cli.yml`, `release-mcp.yml`

## 📝 Roteiro de Análise

### 1. Mapeamento (O que existe?)

- **Ferramentas:** Identificar o uso do GitHub Actions, Docker, Rust Toolchain, Bun, etc.
- **Fluxograma:** Desenhar o caminho do código: `Push` -> `Lint` -> `Test` -> `Build` -> `Release`.

### 2. Eficiência (Onde estão os gargalos?)

- **Tempo de Feedback:** Quanto tempo o `ci.yml` demora para aprovar um PR?
- **Confiabilidade:** Identificar testes instáveis (_flaky tests_) nos logs do repositório oficial.
- **Bloqueio:** O CI impede merges se o `style.yml` ou `e2e-test.yml` falharem?

### 3. Impacto na Evolução (Conclusão)

- **Dívida Técnica:** A automação encoraja refatorações ou o pipeline é lento demais?
- **Frequência de Releases:** Analisar as datas das tags geradas pelos workflows de release.
- **Barreira de Entrada:** O CI ajuda novos contribuidores a não quebrarem o código?

## 📦 Entregáveis da Atividade

1. **Repositório GitHub:** Contendo esta pasta `auditoria_workflows` e este README.
2. **Tutorial PDF:** Documento detalhando a análise dos pontos acima.
3. **Vídeo:** Demonstração de 7 min navegando pelos Actions do projeto original e explicando os achados.

---

**Equipe:** Antônio Camilo, Caio Rosberg, Davi Andrade, Gabriel Argôlo, Katyane dos Santos, Levy dos Santos, Victor Matos e Virna Oliveira.
**Disciplina:** Evolução de Software 2025-2
