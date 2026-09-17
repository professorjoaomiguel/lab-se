# AGENTS.md — Fonte única de instruções para IA

Este arquivo é a fonte única de instrução (SSoT — Single Source of Truth) para
agentes de IA neste repositório, no padrão `agents.md`. Qualquer interação
(Claude, Gemini, Copilot, ChatGPT, etc.) deve seguir rigorosamente estes
combinados.

## Identificação

- **Repositório:** Lab SE — laboratório de experimentos ESP32 + MicroPython.
- **Uso:** repositório de referência técnica, usado como base de hardware por
  outras disciplinas/repositórios (ver "Repositórios irmãos" abaixo), não
  vinculado a uma única turma ou semestre.
- **Docente:** Prof. João Miguel Lac Roehe.

## Objetivo

Padronizar o comportamento de qualquer agente de IA no contexto do Lab SE.

## 🇧🇷 Língua Oficial

- Toda a documentação, READMEs, comentários de código e mensagens de commit
  devem ser em **Português (Brasil)**.
- Exceções: comandos de sistema, palavras-chave da linguagem Python e termos
  técnicos universais.

## 🎓 Diretriz Central — Metodologia Pedagógica: "IA como Mentor"

O objetivo é que o aluno desenvolva autonomia. Para isso:

1. **Estrutura em Etapas:** todo experimento deve ter uma **Etapa
   Intermediária** (validação técnica) e uma **Etapa Final** (projeto
   aplicado).
2. **Reflexão Obrigatória:** arquivos `template.py` devem conter uma seção de
   reflexão técnica para evitar o "copia e cola" sem entendimento.
3. **Prompts de IA:** cada README deve sugerir um prompt que peça à IA para
   atuar como tutor (explicar conceitos e dar pistas) em vez de resolver o
   exercício.
4. **Validação Oral:** o professor reserva-se o direito de pedir explicações
   sobre qualquer linha de código.

## 🛠️ Contexto Técnico (ESP32 + MicroPython)

- **Hardware Base:** ESP32 (UNO Form Factor, WROOM-32) + Shield Multifuncional
  9-em-1. Documentação de hardware em [`docs/`](../docs/) (`shield_9in1.md`,
  `esp32_tecnico.md`, `esp32_pinout.md`, `componentes.md`).
- **Mapeamento de Pinos (Fonte da Verdade):**
  - Botões: SW1 (18), SW2 (17) — Pull-up interno.
  - LEDs: Azul (12), Vermelho (13).
  - LED RGB: Red (9), Green (10), Blue (11).
  - Sensores Analógicos: Potenciômetro (36), LDR (1), LM35 (2).
  - Sensores Digitais: DHT11 (4), Buzzer (5).
- **ADC:** usar sempre `ADC.ATTN_11DB` e `ADC.WIDTH_12BIT`.
- **Modularização:** funções genéricas devem estar em `lib/utils.py`.

## 💻 Fluxo de Trabalho (Git & IDE)

- **IDE:** Thonny IDE é a ferramenta padrão.
- **Atalhos Thonny:** F5 (Executar), Ctrl+C (Interromper), Ctrl+D (Soft Reset).
- **Git para Alunos:**
  1. `git clone` do repositório.
  2. Criar branch pessoal: `git checkout -b seu-nome-sobrenome`.
  3. Resolver no `template.py`.
  4. Commits descritivos.

## Repositórios irmãos

- [`lab_dev_boards`](https://github.com/professorjoaomiguel/lab_dev_boards) —
  documentação de placas e shields (fotos, esquemáticos, componentes,
  periféricos); referência de hardware mais ampla que este repositório.
- [`S086_2026-2`](https://github.com/professorjoaomiguel/S086_2026-2) — usa
  este repositório como referência de hardware (placas ESP32/Arduino), mas
  programa em **C/C++ via Arduino IDE**, não MicroPython. **Atenção ao citar
  este repositório de fora:** `docs/esp32_tecnico.md` descreve o
  ESP32-WROOM-32 clássico — não se aplica diretamente a variantes como o
  ESP32-S3; confirmar pinout específico da placa antes de reaproveitar.

## Hierarquia de Documentos

- Este arquivo (`.ai/AGENTS.md`) é canônico.
- Arquivos de agente específico (`GEMINI.md`, `CLAUDE.md`,
  `.github/copilot-instructions.md` etc.) devem apenas referenciar este
  documento, nunca duplicar ou divergir do conteúdo aqui.
- Em conflito de instrução, prevalece `.ai/AGENTS.md`.

## Conteúdo

- [`docs/`](../docs/) — documentação técnica de hardware, setup do ambiente
  (Thonny), guia de uso de IA e referências pedagógicas.
- [`experiments/01_pisca_pisca/`](../experiments/) ... `09_wifi/` — um
  diretório por experimento, cada um com `main.py` (solução de referência),
  `template.py` (esqueleto para o aluno) e `README.md`.
- [`lib/utils.py`](../lib/utils.py) — funções genéricas reutilizadas pelos
  experimentos.
- [`livro/`](../livro/) — material de apoio (livro-texto sobre IoT com
  MicroPython/NodeMCU).

## 🔐 Privacidade e Ideias

- Notas pedagógicas, bugs intencionais e planos de aula "de bastidores" devem
  ser mantidos no arquivo local **`IDEIAS.md`** (localizado fora do
  repositório Git) para garantir a privacidade do professor.

---
*Documento atualizado em 16 de setembro de 2026.*
