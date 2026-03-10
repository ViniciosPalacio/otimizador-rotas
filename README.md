# 🗺️ Sistema de Otimização Logística de Rotas (PWA)

Desenvolvimento de um sistema avançado de roteamento projetado para solucionar o Problema do Caixeiro-Viajante (TSP) aplicado a operações de campo. 

O núcleo algorítmico foi concebido inicialmente em Python para processamento de matrizes e, posteriormente, reestruturado para um ambiente *Front-End* escalável. A arquitetura atual é implementada como um *Progressive Web App* (PWA), garantindo alta disponibilidade e zero dependência de infraestrutura de servidores intermediários para a execução do cálculo.

## ⚙️ Arquitetura de Engenharia

O ecossistema opera sob processamento *Client-Side*, otimizando o uso de dados móveis e garantindo resposta em tempo real no dispositivo do operador.

* **Linguagens Base:** HTML5, CSS3, Vanilla JavaScript (ES6+).
* **Interface (UI/UX):** Bootstrap 5, estruturado no modelo *Mobile-First*.
* **Motor Geográfico:** Integração nativa com Google Maps Cloud Services (Directions API e Geocoding API).
* **Resiliência de Rede:** Implementação de *Service Workers* (*Cache First*) para carregamento instantâneo da interface gráfica mesmo em zonas sem cobertura de rede.

## 🛡️ Capacidades e Segurança do Sistema

A aplicação foi desenhada com tolerância a falhas e contenção de estresse operacional:

1. **Processamento de Rota Ótima:** Capacidade de receber matrizes de múltiplos endereços e reordená-los automaticamente para o trajeto de menor tempo e distância.
2. **Blindagem de Requisições:** Travas algorítmicas no *front-end* impedem o estouro de limites de *waypoints* ou chamadas nulas (proteção contra o erro `OVER_QUERY_LIMIT` e preservação de cota de faturamento).
3. **Hand-off Nativo (Universal Links):** O sistema web calcula a rota e injeta as coordenadas diretamente nos aplicativos de GPS nativos do dispositivo (Waze ou Google Maps) para iniciar a navegação *turn-by-turn*.
4. **Persistência de Dados:** Histórico de rotas criptografado em formato `.json` e armazenado no *Local Storage* do dispositivo, permitindo recuperação instantânea de malhas logísticas previamente mapeadas.

## 🔒 Status do Projeto

Este repositório contém a documentação da arquitetura lógica. O sistema encontra-se em operação controlada e requer credenciais privadas de nuvem e aprovação de origem (HTTP Referrers) para interagir com a API de roteamento.
