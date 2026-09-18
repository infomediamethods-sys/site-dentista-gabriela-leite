# Performance notes

Contexto: o site da Dra. Deyseane Mendes esta visualmente aprovado. O problema em aberto e a sensacao de scroll travado no Chrome.

Testes feitos que nao resolveram de forma satisfatoria:

- Adicionar Lenis para suavizar scroll.
- Ajustar Lenis com duracao menor, `lerp`, `wheelMultiplier` e `touchMultiplier`.
- Remover Lenis e voltar para scroll nativo.
- Adicionar/remover classe durante scroll para pausar transicoes e animacoes.
- Otimizar imagens do hero de PNG para JPG leve.
- Remover `backdrop-filter` do topo/card.
- Pausar/remover animacoes de entrada no scroll.
- Remover contador animado.
- Remover pulso do WhatsApp.
- Trocar Google Maps iframe por carregamento sob demanda.
- Parar marquee.
- Tirar header fixo/sticky e remover listener de scroll.
- Testar via servidor local HTTP em vez de `file://`.

Rodada aplicada depois da limpeza:

- Trocar imagens remotas dos cards e da secao sobre por arquivos locais otimizados.
- Manter apenas animacoes permanentes pequenas com composicao (`will-change`) no marquee e no pulso do WhatsApp.
- Adiar o carregamento do iframe do Google Maps para um momento ocioso do navegador.

Conclusao provisoria:

- Os testes da primeira lista melhoraram pouco ou nao resolveram.
- A rodada atual precisa ser testada visualmente no Chrome, porque reduz carga externa e trabalho de rede/decodificacao durante o scroll.
- A versao final deve preservar o visual aprovado: header, marquee, WhatsApp, mapa, animacoes e estrutura visual devem voltar ao comportamento normal.
- A limpeza estrutural deve remover codigo morto e assets nao usados sem alterar a aparencia aprovada.
