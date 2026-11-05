# Órbita — demo de investimentos

Protótipo web responsivo de um dashboard de investimentos, feito para demonstração e navegação local. A aplicação é independente: não depende do AI Virtual Office, de um backend, de instalação de pacotes nem de serviços externos.

## Funcionalidades

- Dashboard fictício com patrimônio, rendimento, evolução e distribuição da carteira.
- Gráfico demonstrativo com seleção de período.
- Tabela de seis ativos inventados e busca por ticker, nome ou categoria.
- Regras configuráveis de stop loss e take profit em modo paper trading.
- Simulação de cenários com sinal visual de queda ou alta.
- Painel de insights estáticos, estado de carregamento e mensagem para busca sem resultados.
- Layout responsivo com tema escuro azul-violeta e gráficos em cores neon.

## Como executar

Não é necessário instalar dependências. Com Python 3 instalado, abra um terminal nesta pasta do projeto e execute:

```powershell
python -m http.server 5501
```

No navegador, acesse <http://localhost:5501>. Para parar o servidor, volte ao terminal e pressione `Ctrl+C`.

Também é possível abrir `index.html` diretamente no navegador, mas o servidor local é recomendado para a visualização.

## Regras de negócio demonstrativas

1. Preços, ativos, quantidades, variações, patrimônio, gráficos e insights são fictícios e estão definidos localmente na página.
2. A carteira começa com seis ativos e três regras: stop loss de 8% para PETR4, take profit de 15% para IVVB11 e stop loss de 6% para HGLG11.
3. O formulário permite selecionar PETR4, IVVB11 ou HGLG11 e configurar stop loss entre 0,5% e 50% e take profit entre 0,5% e 100%, em incrementos de 0,5 ponto percentual.
4. Os limites são calculados a partir do preço de referência fictício: preço de stop = referência × (1 − percentual / 100); preço-alvo = referência × (1 + percentual / 100).
5. Salvar substitui as regras do ativo escolhido por um stop loss e um take profit com os valores informados; regras dos outros ativos são mantidas.
6. Cada acionamento de “Simular variação fictícia” alterna entre uma queda que ultrapassa o stop e uma alta que ultrapassa o take profit. O painel atualiza o preço hipotético e o sinal, sem consultar mercado.
7. “Restaurar exemplo” recupera as três regras iniciais e limpa o sinal. Recarregar a página também restaura o estado inicial: as alterações existem apenas em memória durante a visita.

> **DEMO — dados fictícios; sem conexão com corretora; nenhuma ordem real; não é recomendação de investimento.**

Não há integração com corretoras, APIs externas de mercado, KYC, pagamentos, saques ou custódia. Nenhuma ordem é criada, enviada ou executada. Os insights são exemplos estáticos, não análises personalizadas nem recomendações financeiras.
