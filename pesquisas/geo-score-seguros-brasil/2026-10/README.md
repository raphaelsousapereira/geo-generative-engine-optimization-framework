# GEO Score Seguros Brasil — dados públicos, outubro de 2026

**Autor:** Raphael Sousa Pereira · **Recorte:** piloto de seguro auto · **Método:** v0.1.1.

Os dados e a documentação metodológica desta pesquisa são públicos e estão
disponíveis nesta pasta. Captura: **30/10/2026, horário de Brasília**.

Foram selecionadas seis páginas oficiais de produto; quatro puderam ser medidas.
As notas descrevem sinais de prontidão informacional no HTML capturado.
A amostra é experimental e de conveniência, sem representatividade de todo o mercado.

| Marca | Nota /1000 | Pesos iguais /1000 | Cobertura das verificações |
|---|---:|---:|---:|
| Zurich | 883,3 | 816,7 | 100% |
| Tokio Marine | 803,3 | 750,0 | 100% |
| MAPFRE | 796,7 | 750,0 | 100% |
| Porto Seguro | 726,7 | 666,7 | 100% |
| Allianz | Sem medida | — | 0% |
| HDI | Sem medida | — | 0% |

Allianz e HDI: robots.txt respondeu HTTP 403 na origem desta coleta; a visita à
página de produto foi interrompida. Não é nota zero nem prova de bloqueio de IAs.
Tokio Marine e MAPFRE empatam com pesos iguais. Cobertura de 100% se refere às
verificações da rubrica, não à totalidade do site.

## Arquivos

- [Metodologia, critérios, pesos e limitações](METODOLOGIA.md).
- [Dados detalhados em JSON](dados.json): resultados, dimensões, verificações, fontes e identificadores de integridade.
- [Resultados em CSV](resultados.csv).
- [Dimensões em CSV](dimensoes.csv).
- [Fontes e metadados selecionados das capturas](fontes_e_capturas.json).
- [Hashes dos arquivos deste pacote](SHA256SUMS.txt).

Os resultados não medem qualidade do seguro, solvência, conformidade regulatória
ou citações reais em IA. Os pesos são autorais e não possuem calibração independente.
Um sinal não localizado no HTML não prova ausência na apólice ou no restante do site.
Não use as notas como recomendação de contratação.

## Como citar

Raphael Sousa Pereira. *GEO Score Seguros Brasil: piloto de seguro auto — dados e
metodologia públicos*. Edição 2026-10, metodologia v0.1.1. GitHub. Informe a data
de acesso e, para uma referência imutável, o identificador do commit consultado.

Declaração de interesse: o autor criou a rubrica e oferece serviços de SEO/GEO.
As marcas analisadas não são apresentadas como clientes ou endossantes.
