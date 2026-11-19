# Projeto axiomático da bancada de engrenamento

**OBJ-01. Verificar experimentalmente um modelo dinâmico de engrenagens, comparando suas previsões com a resposta medida em ensaios controlados.**

**RF-0.** Produzir dados experimentais comparáveis às previsões do modelo dinâmico de engrenagens.

A bancada deve reproduzir condições conhecidas e medir a resposta do conjunto. A comparação com as previsões é parte do protocolo de pesquisa. A bancada pode cumprir sua função mesmo quando os resultados mostram que o modelo precisa ser revisto. Se parte dos ensaios for usada para ajustar parâmetros do modelo, reserve condições independentes para avaliar sua capacidade preditiva.

A [planilha de trabalho](01_objetivos_e_requisitos_funcionais.xlsx) contém os enunciados, critérios a definir, métodos de verificação propostos e referências às linhas de [Bancada.txt](Bancada.txt).

## Hierarquia funcional

O RF-0 descreve a função global da bancada. Os **RF primários** detalham as funções principais diretamente ligadas ao RF-0. Os **RF secundários** detalham o que precisa ser satisfeito dentro de cada função primária. O nível indica posição na hierarquia. A prioridade de implementação depende do escopo de cada etapa.

| RF primário | Função | RF secundários |
| --- | --- | --- |
| **RF-1** | Configurar os pares de engrenagens para o ensaio | **1.1** acomodar a configuração de pares prevista. **1.2** admitir os tipos de dentado previstos. **1.3** ajustar e reproduzir o backlash inicial. |
| **RF-2** | Estabelecer as condições operacionais | **2.1** controlar a rotação. **2.2** controlar o torque. **2.3** estabelecer a condição de lubrificação. |
| **RF-3** | Limitar excitações parasitas | **3.1** limitar a contribuição do acionamento. **3.2** limitar a vibração externa transmitida. **3.3** limitar a contribuição do desbalanceamento dos eixos. **3.4** limitar a contribuição do desbalanceamento das engrenagens montadas. |
| **RF-4** | Medir e registrar as condições e a resposta dinâmica | **4.1** amplitude de vibração. **4.2** temperatura do lubrificante. **4.3** nível de óleo, quando aplicável. **4.4** relação de fase entre eixos. **4.5** distância entre centros em operação. **4.6** extremos de deslocamento, nos ensaios aplicáveis. **4.7** torque e rotação reais. **4.8** configuração e identificação do ensaio. |
| **RF-5** | Proteger o operador | **5.1** impedir o acesso a partes móveis perigosas em operação. **5.2** interromper a operação e levar a bancada a uma condição segura quando necessário. |

A planilha marca **RF-4.7**, **RF-4.8** e **RF-5** com seus filhos como propostas. RF-4.7 associa as entradas reais à resposta medida. RF-4.8 dá rastreabilidade à comparação e às repetições. RF-5 cobre operação e ajuste com partes móveis. **RF-4.6** é uma interpretação provisória da anotação sobre deslocamentos máximos e mínimos.

## Condições de escopo e decisões abertas

- **C-01 · Capacidade.** Dois pares na etapa inicial, com expansão para quatro ou seis. É preciso esclarecer se o número indica pares operando simultaneamente ou configurações intercambiáveis e como os pares se distribuem na transmissão (D-02).
- **C-02 · Dentado.** Engrenagens cilíndricas de dentes retos na etapa inicial e possibilidade de usar helicoidais depois. Se a etapa helicoidal exigir uma reação axial que mude os apoios, avaliar o impacto sobre a montagem e a dinâmica.
- **C-03 · Material.** Engrenagens de aço representativas da aplicação. A aplicação de referência orienta a escolha da liga, do tratamento e do acabamento.
- **C-04 · Lubrificação.** Fluido lubrificante ou graxa conforme a configuração. O requisito de medir nível se aplica aos arranjos em que houver nível de óleo definido.
- **D-01, D-04, D-05 e D-08 · Geometria.** Diâmetros e relação de transmissão são decisões abertas. Tolerâncias geométricas, vão entre mancais e distância nominal entre centros são dados do projeto a definir. Se o vão ou outra grandeza precisar variar de forma controlada durante a pesquisa, acrescentar a função de ajuste e seu critério.
- **D-03, D-06 e D-07 · Medição e ensaio.** Definir o significado dos extremos de deslocamento, a banda de interesse, o envelope torque × rotação e o protocolo de comparação com o modelo.

## O que precisa ficar verificável

| Tema | Como transformar em critério |
| --- | --- |
| **Comparação com o modelo (RF-0)** | Escolher observáveis previstos pelo modelo. Para cada caso, registrar condições de contorno, métrica de comparação, limite de concordância e incerteza. Definir repetições e separar os ensaios de ajuste dos ensaios de avaliação, quando houver ajuste. |
| **Torque e rotação (RF-2.1, RF-2.2, RF-4.7)** | Especificar pares de torque e rotação que a bancada deve sustentar, eixos de referência, regimes, tempo por ponto e erros admissíveis. Verificar os valores efetivamente atingidos sob carga. |
| **Acionamento, ambiente e desbalanceamento (RF-3)** | Traduzir “não interferir” em contribuição admissível nos canais e na banda em que o modelo será avaliado. Caracterizar fontes em ensaios de referência e distinguir frequências externas de componentes ligadas à rotação ou ao engrenamento. Fixar os limites de desbalanceamento conforme a influência no sinal de interesse. |
| **Backlash, deslocamento e centros (RF-1.3, RF-4.5, RF-4.6)** | Medir o backlash estático com posição e condição de referência especificadas. Definir se a distância entre centros em operação precisa revelar deriva lenta, variações dinâmicas ou ambas. Especificar o referencial e a janela usados para calcular extremos de deslocamento. |
| **Vibração, fase e aquisição (RF-4.1, RF-4.4)** | Definir pontos, direções, grandeza, unidade, banda e métrica de amplitude. Para a relação angular, definir eixos, índices de referência, razão cinemática e sincronismo. Se o modelo prevê erro de transmissão dinâmico, especificar como obter a diferença angular residual em relação ao movimento cinemático nominal. |
| **Lubrificação (RF-2.3, RF-4.2, RF-4.3)** | Identificar o lubrificante e a condição de aplicação. Estabelecer ponto e faixa de medição de temperatura. Quando houver nível de óleo mensurável, definir a referência e o momento da leitura. |
| **Proteção (RF-5)** | Descrever os cenários em operação, ajuste e troca de configuração. Definir condições de acesso, eventos de parada e estado seguro. Verificar a resposta da bancada nos cenários definidos. |

## Como avançar pela metodologia

1. **Definir o escopo do primeiro ensaio.** Fechar a configuração dos dois pares, os observáveis do modelo, os pontos de operação e as condições de referência. Separar os critérios da primeira fase das condições previstas para expansão.
2. **Escolher um PP-0 candidato.** O parâmetro de projeto global representa a arquitetura física da bancada para cumprir RF-0. Para cada arquitetura considerada, associar os RF primários aos PP correspondentes. Só então revisar a decomposição de cada par RF–PP e propor PP secundários. Esta alternância entre o domínio funcional e o físico é o *zigue-zague*. Por isso, a hierarquia secundária atual é uma hipótese de trabalho. [MIT — Conceitos de Projeto Axiomático](https://web.mit.edu/axiom/www/introduction.shtml)
3. **Avaliar a independência.** Abrir a aba **Matriz N1** para uma arquitetura por vez. Cada linha é um RF primário e cada coluna representa seu PP correspondente. Registrar **X** quando variar o PP afetar de forma relevante o atendimento ao RF, **0** quando o efeito for desprezível no envelope avaliado e **?** enquanto faltar evidência. Justificar os efeitos por análise, simulação ou medição. Numa matriz quadrada, uma forma diagonal indica independência direta. Uma forma triangular com diagonal funcional indica dependência tratável por uma sequência definida de ajuste. Reavaliar os acoplamentos também no detalhamento. [Melvin e Suh — Beyond the Hierarchy](https://web.mit.edu/cmp/publications/papers/jwmicad02.pdf)
4. **Comparar soluções que satisfaçam o primeiro axioma.** Depois de definir tolerâncias e conhecer a dispersão do desempenho, aplicar o axioma da informação. Para uma probabilidade de sucesso conjunta `p`, o conteúdo de informação é `I = −log₂(p)`. Menor `I` corresponde a maior probabilidade de atender ao conjunto de requisitos. Se houver dependência estatística entre os resultados, avaliar a probabilidade conjunta com essa dependência. [MIT — Axioma da Informação](https://web.mit.edu/2.882/www/chapter1/chapter1.htm)

Três interações merecem exame na matriz. O PP de aplicação de carga pode alterar a vibração medida e a rotação. Um ajuste de alinhamento ou backlash pode alterar a distância entre centros e a relação de fase. O PP de apoio e isolamento pode mudar as condições de contorno em relação às usadas no modelo. Essas hipóteses orientam a análise de efeitos cruzados.

## Perguntas para fechar o primeiro ciclo

1. **O que o modelo prevê e o que será comparado?** Quais são as entradas, condições de contorno e observáveis prioritários? Qual métrica, limite de concordância e incerteza serão aceitos? Quais casos podem ser reservados para a avaliação do modelo? **(D-07)**
2. **Como serão usados os pares de engrenagens?** Os dois pares iniciais operarão ao mesmo tempo? Serão montados em série, em outra configuração ou trocados entre ensaios? Quais interfaces devem ser previstas desde a primeira montagem para chegar a quatro ou seis? **(C-01, D-02)**
3. **Qual envelope torque × rotação é necessário?** Em quais eixos os valores são especificados? Quais combinações, regimes e durações precisam ser sustentados? **(D-06, RF-2.1, RF-2.2)**
4. **Quais geometrias e materiais representam a aplicação?** Os diâmetros e as razões por par ou global serão fixos? Quais dentes retos serão usados primeiro? Qual geometria helicoidal deve caber depois? Qual aplicação orienta a seleção do aço? **(C-02, C-03, D-01)**
5. **Quais sinais a bancada deve entregar?** A amplitude é de aceleração, velocidade ou deslocamento? Em quais direções, locais e bandas? A defasagem é entre referências angulares dos eixos ou se quer também o erro de transmissão dinâmico? **(RF-4.1, RF-4.4, D-06)**
6. **O que significam os deslocamentos máximo e mínimo?** São extremos medidos, limites aceitáveis de movimento ou a faixa exigida da instrumentação? Em quais pontos e referenciais? A distância entre centros precisa ser acompanhada em quais pares e com que banda? **(D-03, D-08)**
7. **Quais efeitos externos precisam ser atenuados?** Que faixas ou ordens interessam? Qual contribuição residual do acionamento, do piso e dos conjuntos rotativos é admissível em cada canal? **(RF-3, D-06)**
8. **Quais dimensões precisam ser ajustáveis e com que tolerância?** Qual é a folga estática inicial e em que condição será medida? O vão entre mancais é variável experimental? Quais desvios geométricos entram no modelo ou no orçamento de incerteza? **(D-04, D-05, D-08, RF-1.3)**
9. **Quando usar óleo ou graxa?** Qual configuração exige cada lubrificante? Que ponto de temperatura é representativo e em que arranjos faz sentido medir nível? **(C-04, RF-2.3, RF-4.2, RF-4.3)**
10. **Quais modos de acesso e parada precisam ser atendidos?** Como se fazem ajustes, configuração e operação? Quais condições exigem parada e como se constata o estado seguro? **(RF-5)**
