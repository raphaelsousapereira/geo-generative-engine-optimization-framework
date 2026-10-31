# GEO Score Seguros Brasil — metodologia experimental v0.1.1

**Autor:** Raphael Sousa Pereira. **Recorte:** seguro auto, página pública de produto.

## Pergunta de pesquisa

As páginas de produto publicam os sinais técnicos e as informações necessárias
para uma pessoa ou sistema de busca encontrar e interpretar a oferta de seguro
auto, suas coberturas, restrições, documentos e canais de atendimento?

O índice é uma rubrica autoral de prontidão informacional sobre HTML coletado.
Não mede citações reais em IA, qualidade de seguro, solvência, atendimento ou
conformidade regulatória. Não é certificação da SUSEP nem recomendação de compra.

## Unidade e piloto

- Uma página oficial de seguro auto por marca declarada de seguradora.
- Seis alvos fixados antes da coleta: Porto Seguro, Allianz, MAPFRE, Tokio Marine,
  HDI e Zurich. A escolha é por conveniência de pesquisa, sem representatividade
  estatística do mercado, ponderação por receita ou alegação de cobertura integral.
- O produto procurado é a oferta pública de seguro auto com cobertura de casco e
  opções adicionais, para pessoas físicas. Uma marca pode redirecionar sua página;
  esse destino é preservado e precisa ser revisado antes de interpretação comercial.
- Não misturar corretoras, comparadores, proteção patrimonial mutualista e
  seguradoras. O papel declarado no cadastro não comprova autorização regulatória.
- A página de produto é a fonte das verificações de conteúdo. O rodapé pode
  fornecer identidade, mas menus/rodapés não contam como explicação de produto.
- Opcionalmente, busca-se um link distinto para condições ou documentos no domínio
  ou subdomínio da instituição. A prioridade é conteúdo principal, maior prefixo
  compartilhado com a página de produto e, em empate, ordem do HTML. Isso verifica descoberta e acesso, não adequação
  jurídica, correspondência da versão com uma apólice ou conteúdo do PDF.

## Fontes de desenho da rubrica

A SUSEP orienta o consumidor a examinar coberturas, riscos excluídos, franquia e
condições contratuais. Essas orientações justificam a seleção de temas, não os
pesos numéricos e nem uma validação do índice pela Autarquia.

- https://www.gov.br/susep/pt-br/assuntos/meu-futuro-seguro/seguros-previdencia-e-capitalizacao/seguros/seguro-de-automoveis
- https://www.gov.br/susep/pt-br/assuntos/meu-futuro-seguro/seguros-previdencia-e-capitalizacao/seguros/informacoes-importantes
- https://www.gov.br/pt-br/servicos/consultar-entidades-licenciadas-pela-susep
- https://developers.google.com/search/docs/appearance/ai-features
- https://developers.google.com/search/docs/fundamentals/creating-helpful-content

## Dimensões e pesos

| Dimensão | Peso | Sinais observáveis |
|---|---:|---|
| Acesso e indexabilidade | 12 | Texto principal no HTML; ausência de noindex; regras robots declaradas para três robôs de busca IA |
| Identidade e responsabilidades | 12 | Marca, indicação textual do responsável, CNPJ publicado |
| Coberturas descritas em HTML | 12 | Riscos, terceiros/passageiros e diferenciação de opções |
| Franquias, exclusões e limites em HTML | 14 | Passagens com conteúdo sobre esses temas, não apenas títulos |
| Descoberta de condições contratuais | 12 | Link, acesso ao destino e indício de contexto auto no HTML documental |
| Sinistro e assistência | 10 | Orientação textual e canal acionável |
| Respostas e explicações autocontidas | 10 | Passagens de explicação e perguntas seguidas de resposta |
| Estrutura de descoberta da página | 8 | Título/H1 temáticos, canonical e segmentação por headings |
| Dados estruturados publicados | 6 | JSON-LD parseável e nó de organização/serviço/produto |
| Referências e atualização identificável | 4 | Versão/vigência/atualização identificável e link a fonte oficial |

Não se exige llms.txt, FAQPage, HowTo ou qualquer suposto schema especial de IA.
Presença de JSON-LD não comprova coerência semântica, verdade ou adoção pelo buscador.
Um CNPJ encontrado é sinal de identificação publicada, sem validar cadastro.

### Fórmula

Cada verificação vale entre 0 e 1 ou fica sem medida. A nota da dimensão é a
média das verificações medidas multiplicada por 100. A nota global é:

`nota = 10 × soma(peso_dimensão × nota_dimensão) / soma(pesos_dimensões_medidas)`

A cobertura considera a fração medida de cada dimensão:

`cobertura = soma(peso_dimensão × verificações_medidas / verificações_previstas)`

Sem página de produto HTML legível, com permissão robots, HTTP 200 e pelo menos
100 palavras no texto principal, não há nota. Ausência de coleta não vira zero.
Em página lida, um sinal não localizado pode receber zero **somente no corpus
observado**, sem concluir que inexiste no site inteiro ou na documentação contratual.

Um destino de condições não coletado fica desconhecido. Se a página lida não
oferece link documental identificável, a falta de descoberta é uma observação.
PDF acessível pontua acesso ao documento; conteúdo e contexto do PDF não são
extraídos. HTTP 200 em página institucional não comprova destino de seguro auto;
uma verificação separada busca esse indício no HTML e continua sendo heurística.

### Ranking e comparabilidade

- A ordenação é experimental e requer revisão. Requer classificação de captura observada e
  cobertura mínima de 80%. Dados sintéticos nunca entram.
- Métodos, protocolo, segmento e mês precisam ser os mesmos. Edição mensal usa
  a data de captura convertida para America/Sao_Paulo.
- Notas iguais recebem a mesma posição. A ordem alfabética do ID só estabiliza a saída.
- Publicar notas e posições com pesos iguais ao lado da ponderação autoral.
- Não comparar as notas deste recorte com índices de outros setores ou de menções em IA.
- Mudança em heurísticas, limiares ou pesos exige nova versão e hash de método.
- Não converter ganho da rubrica em previsão de tráfego, receita ou citações.

## Protocolo de captura desta edição

Captura em 30/10/2026 no horário de Brasília (31/10 em UTC), a partir de
infraestrutura nos Estados Unidos. Seis páginas de produto foram previstas e
quatro puderam ser medidas. Nenhum modelo de IA ou API comercial foi consultado.

- Apenas HTTPS público na porta 443; resolução de endereços públicos e verificação TLS.
- Sem autenticação, cookies, formulários, proxy de ambiente ou execução de JavaScript.
- Consulta a robots.txt antes das páginas e redirecionamentos. Política desconhecida
  ou negada interrompe a visita; exige-se HTTP 200 com text/plain para estabelecer a política.
- Redirecionamentos externos à instituição ou para HTTP são interrompidos.
- Limite de 30 requisições na rodada e de 2,5 MB por resposta; cache e limites de tempo.
- Uma página de produto e, quando possível, um destino documental por marca.
- Horários, URLs, estados HTTP e hashes são preservados na captura. Os metadados
  selecionados estão em `fontes_e_capturas.json`.

Allianz e HDI ficaram sem medida porque robots.txt respondeu HTTP 403 nesta origem.
Isso não equivale a nota zero nem prova bloqueio de robôs reais de busca de IA.

## Critérios registrados

Os identificadores, descrições, valores e URLs-fonte de cada verificação medida
estão em `dados.json`, em `measurements[].dimensions[].checks[]`. Valor 0 indica
sinal não localizado no corpus segundo a rubrica; 1 indica sinal localizado.
Valor nulo indica verificação não medida. As entidades sem página elegível
não recebem nota e apresentam listas de verificações vazias.

| Dimensão | Verificação | Descrição |
|---|---|---|
| Acesso e indexabilidade | `html` | Texto principal entregue no HTML |
| Acesso e indexabilidade | `index` | Sem diretiva noindex observada |
| Acesso e indexabilidade | `robots` | Permissão declarada para três robôs de busca IA |
| Identidade e responsabilidades | `brand` | Marca identificada no texto público |
| Identidade e responsabilidades | `responsibility` | Sinal textual de instituição responsável |
| Identidade e responsabilidades | `cnpj` | CNPJ identificado no HTML público |
| Coberturas descritas em HTML | `perils` | Descrição de riscos cobertos |
| Coberturas descritas em HTML | `third_party` | Descrição sobre terceiros ou passageiros |
| Coberturas descritas em HTML | `optional` | Diferenciação textual de opção/contratação |
| Franquias, exclusões e limites em HTML | `deductible` | Explicação sobre franquia em HTML |
| Franquias, exclusões e limites em HTML | `exclusions` | Explicação sobre exclusões em HTML |
| Franquias, exclusões e limites em HTML | `limits` | Descrição de limites/condições de uso em HTML |
| Descoberta de condições contratuais | `link` | Link identificável para condições/documentos |
| Descoberta de condições contratuais | `retrieval` | Destino documental coletado com HTTP 200 |
| Descoberta de condições contratuais | `product_context` | Indício documental de seguro auto no destino HTML |
| Sinistro e assistência | `process` | Orientação sobre sinistro |
| Sinistro e assistência | `assistance` | Descrição de assistência/atendimento |
| Sinistro e assistência | `channel` | Canal acionável publicado |
| Respostas e explicações autocontidas | `paragraphs` | Passagens de explicação entre 20 e 160 palavras |
| Respostas e explicações autocontidas | `qa` | Perguntas seguidas de resposta textual |
| Estrutura de descoberta da página | `title` | Título e H1 identificam o tema automóvel |
| Estrutura de descoberta da página | `canonical` | Canonical aponta para a própria página |
| Estrutura de descoberta da página | `headings` | Conteúdo segmentado em títulos |
| Dados estruturados publicados | `syntax` | JSON-LD presente e parseável |
| Dados estruturados publicados | `entity` | Nó de organização ou serviço/produto identificado |
| Referências e atualização identificável | `dated` | Versão/vigência/atualização identificável no produto |
| Referências e atualização identificável | `reference` | Referência oficial identificável |

## Leitura dos resultados e limitações

- Nas quatro páginas medidas, a rubrica não localizou passagens explicativas de
  exclusões com os sinais pesquisados. Isso não demonstra ausência em contratos,
  PDFs, outras páginas ou conteúdo entregue por JavaScript.
- Na captura da Porto, o botão “Acessar condições gerais” levou à página
  institucional “Empresas do Grupo”. HTTP 200 não comprova contexto documental auto.
- Com pesos iguais, Tokio Marine e MAPFRE empatam em 750,0; a ordem ponderada
  é sensível à escolha dos pesos. Nenhuma superioridade comercial é estabelecida.
- Heurísticas textuais podem gerar falsos positivos e negativos. A leitura de HTML
  inicial não comprova renderização, acessibilidade visual ou suficiência jurídica.
- Identificação textual de marca, responsável e CNPJ não autentica os dados.
- Acesso a um PDF não implica análise de seu conteúdo. Essa análise não foi feita.
- Pesos e limiares são hipóteses autorais, sem calibração independente contra
  citações de IA, conversão ou decisões de consumidores.
- A amostra é de conveniência: uma página de produto por marca, sem representação
  estatística de todo o mercado, de outros ramos ou de todos os sites.
- Os dados não medem qualidade de seguros, solvência, conformidade regulatória,
  presença real em respostas de IA ou recomendação de contratação.

## Integridade e revisão editorial

`SHA256SUMS.txt` permite conferir os arquivos deste pacote público. Os hashes
`input_sha256`, `report_sha256` e `methodology_sha256` são identificadores dos
registros originais. Não devem ser recalculados como se fossem hashes do JSON
público editado. Os estados `REVIEW_REQUIRED` e `ranking_draft` da consolidação
original são preservados como proveniência da saída experimental, sem constituir
certificação independente ou ranking definitivo de mercado. Hashes conferem
integridade; não autenticam origem, atualidade ou verdade das informações.

A revisão técnica conferiu os seis relatórios e a consolidação. Os dados aqui
publicados são uma seleção com resultados, critérios, fontes e metadados; não
contêm cópias integrais dos sites de terceiros. O protocolo, os pesos e as
limitações precisam acompanhar qualquer comparação ou citação dos resultados.

**Declaração de interesse:** Raphael Sousa Pereira criou a rubrica e oferece
serviços de SEO/GEO. As marcas não são apresentadas como clientes, patrocinadoras
ou endossantes da pesquisa.
