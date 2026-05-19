# Google Ads Editor — Estrutura de Campanhas Search

Use esta skill sempre que o usuário quiser criar uma estrutura de campanhas Google Ads Search, seja para um novo cliente ou novo produto. A skill gera os 4 blocos TSV prontos para colar no modo **"Fazer várias alterações"** do Google Ads Editor.

## Contexto do Usuário

O usuário opera a **V4**, agência de tráfego pago. As estruturas são criadas no Google Ads Editor (desktop) e importadas via **"Editar → Fazer várias alterações"**. O Editor usa nomes de colunas em **inglês**.

---

## Padrão de Nomenclatura

### Campanhas
```
[Cliente] | Search | [Produto] | [Localização]
```
Exemplos:
- `Elevate | Search | Majestic - Praia | Sudeste` *(incorporadora imobiliária, imóveis de praia)*
- `Prado | Search | Empreendimentos | Curitiba` *(imobiliária multi-produto)*
- `MaidPad | Search | Software Gestao | Brasil` *(SaaS B2B, sem acento na URL path)*

### Grupos de anúncios
Nomes descritivos em português, sem símbolos especiais. Exemplos:
- `Imovel Praia Generico` *(Elevate — intenção ampla)*
- `Apartamento Litoral Norte` *(Elevate — especificação por localização)*
- `Software Gestao Diaristas` *(MaidPad — intenção específica)*
- `Lancamento Curitiba` *(Prado — empreendimento genérico)*

---

## Configurações Padrão de Campanha

| Configuração | Valor padrão |
|---|---|
| Rede | Somente Pesquisa (Display e Parceiros desativados) |
| Idioma | Português |
| Localização | Cidade principal + raio de 40km |
| Horário | Seg–Sex 7h–18h, Sáb 8h–12h |
| Ajuste por dispositivo | Desktop +20%, Mobile –20% |
| Estratégia de lances | Maximizar Cliques (início) → Target CPA após 30 conversões |
| Rotação de anúncios | Otimizar (melhor desempenho) |

---

## Estrutura de Grupos de Anúncios

Para cada campanha (produto), criar **2 grupos**:

| Grupo | Foco | Exemplos de keywords |
|---|---|---|
| **Genérico** | Intenção ampla de compra/contato | Elevate: "apartamento na praia sp", "imóvel litoral norte" / MaidPad: "software gestão de limpeza", "app para diaristas" |
| **Específico / Localização** | Intenção por produto, modelo ou cidade | Elevate: "apartamento caraguatatuba praia", "lançamento litoral norte sp" / Prado: "lançamento imóvel curitiba", "apartamento alto padrão curitiba" |

Regra: o grupo genérico captura quem ainda está pesquisando. O grupo específico captura quem já sabe o que quer e onde.

---

## Padrão de Palavras-chave

- Usar **Exact** e **Phrase** apenas — sem Broad
- Incluir variações com e sem localização
- Incluir termos com intenção de urgência/prazo quando relevante
- Mínimo: 6–10 keywords por grupo

---

## Padrão de Negativos (nível de campanha)

Negativos globais aplicados em todas as campanhas:

```
curso, cursos, vagas, emprego, empregos, como fazer, tutorial, grátis,
gratuito, diy, apostila, manual, youtube, mercado livre, shopee, olx,
amazon, salário, freelancer
```

---

## Padrão de Negativos Cruzados (nível de grupo de anúncios)

**Regra obrigatória:** todas as keywords de cada grupo devem ser negativadas nos outros grupos da mesma campanha — sem exceção, mesmo que não haja risco real de sobreposição.

Exemplo:
- No grupo "Fabricante": negar todas as keywords do grupo "Especificação" (Phrase)
- No grupo "Especificação": negar todas as keywords do grupo "Fabricante" (Phrase)

---

## Padrão de Anúncios RSA

| Campo | Limite | Quantidade |
|---|---|---|
| Headline | 30 caracteres | 15 (obrigatório preencher todos) |
| Description | 90 caracteres | 4 (obrigatório preencher todos) |
| Display Path 1 | sem acento, sem espaço | 1 |
| Display Path 2 | sem acento, sem espaço | 1 |
| Final URL | URL real da landing page | 1 |

### Temas de headline a cobrir (distribuir entre os 15):
1. Produto + cidade — ex: "Apartamento na Praia SP", "Imóvel em Curitiba"
2. Marca / incorporadora + produto — ex: "Elevate Incorporadora", "Prado Lançamentos"
3. Urgência / condição — ex: "Últimas Unidades", "Período de Lançamento"
4. Qualidade / padrão — ex: "Alto Padrão Litoral Norte", "Acabamento Premium"
5. Atendimento rápido — ex: "Fale com Consultor em 24h", "Orçamento Grátis"
6. Personalização / sob medida — ex: "Planta Flexível", "Escolha Seu Andar"
7. Visita / tour — ex: "Agende Visita ao Decorado", "Tour Virtual Disponível"
8. CTA: WhatsApp / formulário — ex: "Solicite Tabela de Preços", "Fale no WhatsApp"
9. Geo — ex: "Atendemos Curitiba e Região", "Caraguatatuba e Litoral Norte"
10. Diferencial específico — ex: "Vista Mar Garantida", "Gestão de Equipes em 1 App" *(MaidPad)*

### Temas de description a cobrir (1 por description):
1. Produto + localização + prazo/condição — ex: "Lançamento de apartamentos no Litoral Norte SP. Condições especiais durante o pré-lançamento."
2. Qualidade + especificação — ex: "Empreendimento de alto padrão com vista para o mar. Entrega prevista em 2027."
3. Geo + ICP — ex: "Ideal para investidores e famílias do interior de SP que buscam segunda residência na praia."
4. Urgência + CTA — ex: "Últimas unidades disponíveis. Fale agora com um consultor e receba a tabela de preços."

---

## Padrão de Extensões

### Sitelinks (mínimo 4, ideal 5–6)
| Título (25 chars) | Linha 1 (35 chars) | Linha 2 (35 chars) |
|---|---|---|
| Solicitar Orçamento | Proposta técnica em 24 horas | Sem compromisso, resposta rápida |
| Falar no WhatsApp | Atendimento direto com a equipe | Segunda a sexta, das 7h às 18h |
| Nossos Produtos | [listar produtos principais] | Fabricação sob encomenda |
| Visita Técnica | Visita ao local em até 48h | [cidade] e região metropolitana |
| Sobre a [Cliente] | [diferencial principal] | [cidade/estado] |

### Callouts (máx. 25 chars cada, mínimo 6)
Exemplos baseados nos diferenciais do cliente:
```
# Imobiliária / Incorporadora (Elevate, Prado):
Vista Mar Garantida
Alto Padrão de Acabamento
Consultor Especializado
Tabela de Preços em 24h
Visita ao Decorado
Pré-Lançamento com Desconto
Financiamento Facilitado
Segunda Residência Ideal

# SaaS B2B (MaidPad):
Teste Grátis por 14 Dias
Gestão de Equipes Simples
Agenda Automática
Relatórios em Tempo Real
Suporte em Português
Sem Contrato de Fidelidade
```

### Snippets estruturados
```
Tipo: Produtos
Valores: [listar produtos/serviços do cliente]
```

### Extensão de chamada
Número de WhatsApp do cliente.

### Extensão de local
Vincular ao Google Meu Negócio (se disponível).

---

## Os 5 Blocos TSV que Devem Ser Gerados

Ao executar a skill, gerar sempre os 5 blocos abaixo, nesta ordem, cada um pronto para colar em sua respectiva opção no "Fazer várias alterações":

### BLOCO 1 — Palavras-chave
Seção: **Keywords and targeting → Keywords**
Colunas: `Campaign | Ad Group | Keyword | Match Type`
Valores de Match Type: `Exact` ou `Phrase`

### BLOCO 2 — Negativos de campanha
Seção: **Keywords and targeting → Campaign negative keywords**
Colunas: `Campaign | Negative Keyword | Match Type`
Valores de Match Type: `Broad` (para negativos genéricos) ou `Phrase` (para frases específicas)

### BLOCO 3 — Negativos cruzados (nível de grupo)
Seção: **Keywords and targeting → Ad group negative keywords**
Colunas: `Campaign | Ad Group | Negative Keyword | Match Type`
Regra: todas as keywords de cada grupo negativadas nos outros grupos. Match Type: `Phrase`.

### BLOCO 4 — Anúncios RSA
Seção: **Ads and extensions → Responsive search ads**
Colunas: `Campaign | Ad Group | Headline 1 | Headline 2 | ... | Headline 15 | Description 1 | Description 2 | Description 3 | Description 4 | Final URL | Display Path 1 | Display Path 2`

> Lembrar o usuário de substituir `[URL-LANDING-PAGE]` pela URL real antes de colar o bloco 4.

### BLOCO 5 — Sitelinks
Seção: **Ads and extensions → Sitelinks**
Colunas: `Campaign | Link Text | Line 1 | Line 2 | Final URL`

Regras:
- `Link Text`: máx. 25 caracteres
- `Line 1` e `Line 2`: máx. 35 caracteres cada
- `Final URL`: URL real de destino (pode ser a mesma landing page ou URLs específicas por seção do site)
- Mínimo 4 sitelinks por campanha, ideal 6
- Sitelinks são no nível de campanha — repetir o nome da campanha em cada linha

Exemplo de estrutura:
```
Campaign	Link Text	Line 1	Line 2	Final URL
Elevate | Search | Majestic - Praia | Sudeste	Solicitar Orçamento	Proposta em até 24 horas	Sem compromisso	[URL]
Elevate | Search | Majestic - Praia | Sudeste	Falar no WhatsApp	Atendimento direto com consultor	Segunda a sexta, 9h às 18h	[URL]
Elevate | Search | Majestic - Praia | Sudeste	Nossos Empreendimentos	Conheça o portfólio completo	Alto padrão no Litoral Norte	[URL]
Elevate | Search | Majestic - Praia | Sudeste	Agendar Visita	Visite o decorado presencialmente	Caraguatatuba e região	[URL]
Elevate | Search | Majestic - Praia | Sudeste	Sobre a Elevate	Incorporadora com projetos premiados	SP e Litoral Norte	[URL]
```

---

## Como Executar

1. **Perguntar ao usuário** (se não forneceu):
   - Nome do cliente
   - Produtos/serviços a anunciar (uma campanha por produto)
   - Cidade/região alvo
   - Diferenciais do negócio (prazo, qualidade, tecnologia, etc.)
   - ICP (quem compra: engenheiro, médico, consumidor final, etc.)
   - URL da landing page
   - URLs específicas por seção do site (para sitelinks, se disponíveis)

2. **Definir campanhas** — uma por produto principal

3. **Definir grupos de anúncios** — Genérico + Específico por campanha

4. **Gerar keywords** — baseadas no produto, localização e intenção

5. **Gerar os 5 blocos TSV** na ordem correta

6. **Gerar tabela de extensões** separada para callouts, snippets e extensão de chamada (configurar manualmente no Editor)

---

## Observações Técnicas

- Campanhas e grupos de anúncios precisam existir no Editor antes de importar keywords e anúncios via "Fazer várias alterações"
- O usuário deve estar com a conta específica selecionada no Editor (não "Todas as contas") antes de colar os dados
- Após colar todos os blocos, clicar em **"Postar alterações"** para subir ao Google Ads
- A programação de horários (Ad Schedule) é configurada manualmente: aba "Ad Schedule" no painel inferior do Editor
