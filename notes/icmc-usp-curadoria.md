# ICMC-USP: curadoria para hardware, reversa e sistemas

Revisão em 15/10/2026 do acervo pessoal [ropalma/ICMC-USP](https://github.com/ropalma/ICMC-USP).

O snapshot analisado é de 22/03/2019. O valor principal está nos fundamentos de computação; não é uma referência atual de ferramentas ofensivas. Esta seleção não pressupõe que todo arquivo do acervo seja uma publicação oficial da USP.

Foram conferidos o índice, os tópicos e páginas iniciais das aulas selecionadas, a lista completa de exercícios de banco de memória e o exemplo de código citado. Não foi feita uma auditoria integral de todos os PDFs nem executados os programas.

## 1. Lógica digital — prioridade alta

Aulas de SSC512, Prof. Dr. Danilo Spatti, ICMC-USP, 2018. Os conceitos continuam úteis; os exemplos não substituem especificações elétricas e temporais de componentes reais.

| Material | Por que estudar |
| --- | --- |
| [Sistemas de numeração](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Elementos%20de%20L%C3%B2gica%20Digital/Aula%201%20-%20Sistemas%20de%20Numeracao/Aula%201%20-%20Sistemas%20de%20Numera%C3%A7%C3%A3o.pdf) | Conversões e representação de valores. Base para ler dumps, endereços e registradores. |
| [Álgebra de Boole](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Elementos%20de%20L%C3%B2gica%20Digital/Aula%202%20-%20Algebra%20de%20Boole/Algebra%20de%20Boole.pdf) | Funções lógicas e raciocínio sobre circuitos. Relacionar com máscaras e operações bit a bit. |
| [Mux e demux](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Elementos%20de%20L%C3%B2gica%20Digital/Aula%207%20-%20Mux%20e%20Demux/Aula%207%20-%20Mux%20e%20Demux.pdf) | Seleção e encaminhamento de sinais. Base para entender caminhos de dados. |
| [Latches e flip-flops](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Elementos%20de%20L%C3%B2gica%20Digital/Aula%208%20-%20Latches%20e%20Flip-Flops/Aula%208%20-%20Latches%20e%20Flip%20Flops.pdf) | Estado e circuitos sequenciais. Pré-requisito para estudar comportamento temporal de hardware. |
| [Registradores](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Elementos%20de%20L%C3%B2gica%20Digital/Aula%209%20-%20Registradores/Aula%2009%20-%20Registradores.pdf) | Armazenamento e transferência de bits. Complementar com o datasheet do dispositivo estudado. |

## 2. C, ponteiros e memória — prioridade alta

Estes materiais ajudam a conectar código-fonte a endereços, estruturas e chamadas vistas no depurador. Exemplos de aula devem ser revisados antes de reutilização; não foram validados como código de produção.

- [Ponteiros — Parte I](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Introdu%C3%A7%C3%A3o%20a%20Ci%C3%AAncias%20da%20Computa%C3%A7%C3%A3o/T%C3%B3pico%2010%20-%20Ponteiros%20Parte%20I.pdf) — Ponteiros, vetores e alocação dinâmica.
- [Ponteiros — Parte II](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Introdu%C3%A7%C3%A3o%20a%20Ci%C3%AAncias%20da%20Computa%C3%A7%C3%A3o/T%C3%B3pico%2011%20-%20Ponteiros%20Parte%20II.pdf) — const, sizeof, ponteiros para ponteiros e ponteiros para funções.
- [Exercícios de banco de memória](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Estruturas%20de%20Dados/Exercicios/Exercicios%20-%20Banco%20de%20Memoria.pdf) — Listas, filas e pilhas sobre um banco com capacidade fixa. Lista de SCC0502, Prof. Dr. Bruno Matheus e Rafael Nakanishi.

**Exemplo para leitura crítica:** [banco de memoria.c](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/Principais%20Estruturas%20de%20Dados/Banco%20de%20Memoria%20Estatico%20em%20C/banco%20de%20memoria.c) e [cabeçalho](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/Principais%20Estruturas%20de%20Dados/Banco%20de%20Memoria%20Estatico%20em%20C/banco%20de%20memoria.h). O código usa um vetor de 10 posições e índices para representar encadeamento e posições livres. A função `freenode` pressupõe um índice válido e não verifica liberação repetida. É um bom exercício perguntar quais invariantes o chamador precisa manter; não é um alocador pronto para produção.

**Prática sugerida:** implementar sua própria versão, testar capacidade esgotada, remoção de estrutura vazia e índices inválidos, e observar os estados no depurador. Não assumir que tamanhos de ponteiros ou tipos são iguais entre plataformas.

## 3. Análise de algoritmos — apoio à graduação

- [Crescimento de funções](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Analise%20de%20Algoritmos/T%C3%B3pico%202%20-%20Crescimento%20Fun%C3%A7%C3%B5es.pdf) — Base para analisar custo de busca e processamento de entradas.
- [Indução e corretude](https://github.com/ropalma/ICMC-USP/blob/a5aef33b27adf14769d866cfa249d4a09a10e812/USP%20-%20Analise%20de%20Algoritmos/T%C3%B3pico%203%20-%20Indu%C3%A7%C3%A3o%20e%20Corretude.pdf) — Base para justificar invariantes e raciocinar sobre a correção de algoritmos.

Esses fundamentos permanecem relevantes. Complexidade assintótica não equivale a tempo exato em segundos e não deve ser confundida com comportamento de temporização constante em criptografia.

## 4. Referências do acervo que vale acompanhar na fonte

| Referência | Aplicação e limite |
| --- | --- |
| [Fundamentos de Engenharia Reversa — Fernando Mercês / Mente Binária](https://mentebinaria.gitbook.io/engenharia-reversa) | Prioridade alta para reversa. A apresentação delimita o foco a Windows, Intel e programas de 32 bits; não é um manual de ARM, RISC-V ou firmware. |
| [FreeBSD Handbook — documentação oficial](https://docs.freebsd.org/en/books/handbook/) | Complemento para sistemas, permissões, dispositivos, redes e administração. Consultar a versão online para instruções operacionais. |
| [Guia Foca — site oficial](https://www.guiafoca.org/) | Referência em português para Linux. Conferir a edição e a documentação da distribuição antes de executar procedimentos. |

## O que ficou fora da seleção

- PDFs comerciais de arquitetura, redes, sistemas operacionais e assembly: os assuntos são relevantes, mas a presença no GitHub não comprova permissão de redistribuição. Esta curadoria não republica esses livros.
- Guias genéricos de hacking e wireless: não foram validados como procedimentos atuais e não entram na seleção prioritária.
- Marketing, gestão, desenvolvimento pessoal e outros temas distantes do foco atual.
- Cópias repetidas de aulas, resoluções e material de Git/Linux já coberto no faultlines.

**Cuidado com o README de origem:** ele agrupa SHA-1 e SHA-2/SHA-256 como não recomendados, sem delimitar adequadamente o uso, e chama funções de derivação/hash de senha de encriptação. Para armazenamento de senhas, consulte a [orientação atual da OWASP](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html). SHA-256 puro ser inadequado para armazenar senhas não significa que toda utilização de SHA-256 seja insegura; a própria orientação contempla PBKDF2-HMAC-SHA-256 em um contexto específico.

## Ordem sugerida

1. Numeração e Boole, junto das suas tabelas ASCII/hexadecimal.
2. Ponteiros I e II, escrevendo pequenos programas e observando memória.
3. Mux/demux, latches e registradores, relacionando com um datasheet real.
4. Banco de memória, com sua implementação e seus próprios testes.
5. Fundamentos de Engenharia Reversa, acompanhado de exercícios.
6. Crescimento de funções e corretude, conforme as disciplinas da graduação.

## Atribuição e reprodução

Os links de aulas e código apontam para o snapshot revisado do acervo de ropalma. Autoria dos materiais permanece com os respectivos autores; o texto de seleção e os comentários acima foram preparados para faultlines. Não foi encontrada uma licença geral no acervo que autorizasse republicar indiscriminadamente as aulas, códigos e livros. Por isso, esta inclusão contém links e comentários, sem copiar os arquivos de terceiros.
