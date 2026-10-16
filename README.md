# 🏦 ByteBank ATM

Simulador de caixa eletrônico (ATM) com interface gráfica, pensado para rodar em modo Kiosk (tela cheia bloqueada).

- **O que faz:** autenticação por conta e senha, saque, depósito, transferência entre contas, extrato e emissão de comprovantes `.txt`. Encerra a sessão após 30 segundos de inatividade.
- **Com o que foi feito:** Python 3, Tkinter e JSON para persistência. Som das teclas via `canberra-gtk-play` (Linux).
- **Por que foi construído:** trabalho acadêmico que serve como aplicação principal de uma remasterização customizada do Ubuntu 26 LTS, simulando um terminal de autoatendimento bancário.
  [Download da ISO](https://drive.google.com/drive/folders/1uvSzPTsW___l3kGXn5YfClX2yKXkoyHY?usp=sharing)

## Instruções de instalação

1. Instale o Python 3.x (o `tkinter` já vem na instalação padrão; no Ubuntu: `sudo apt install python3-tk`).
2. Clone o repositório:
   ```bash
   git clone https://github.com/HallissonEduardo/ByteBank-ATM---Simulador-de-Caixa-Eletronico.git
   cd ByteBank-ATM---Simulador-de-Caixa-Eletronico
   ```
3. (Opcional, Linux) Instale o som das teclas: `sudo apt install libcanberra-gtk-module`.

## Instruções de uso

1. Execute a partir da raiz do projeto:
   ```bash
   python3 main.py
   ```
2. Na primeira execução, `data/accounts.json` é criado com contas de teste:

   | Conta | Senha | Titular |
   |-------|-------|---------|
   | 001 | 1234 | João Silva |
   | 002 | 5678 | Maria Santos |

3. Faça login e use o menu: Saque, Depósito, Extrato ou Transferência.
4. Comprovantes são salvos em `data/recibos/`.

> O modo Kiosk bloqueia `Esc` e o botão de fechar da janela. Para encerrar durante o desenvolvimento, finalize o processo pelo terminal (`Ctrl+C`).

## Licença

[MIT](https://opensource.org/license/mit).

## Padrões para contribuir

- Siga a **PEP 8** e mantenha docstrings em português.
- Respeite a separação de responsabilidades: interface em `gui/`, regras de negócio em `models/`, configurações e estilos em `config.py` e `gui/styles.py`.
- Telas de transação devem herdar de `BaseTransactionScreen` e implementar apenas `executar()`.
- Não deixe valores fixos de cor, fonte ou limite no código das telas; use o `config.py`.
- Crie uma branch por alteração (`feature/nome` ou `fix/nome`) e abra um Pull Request com descrição objetiva.
