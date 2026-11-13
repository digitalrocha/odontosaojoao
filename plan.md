# Plano — páginas de Clínica Geral e Urgência

## Escopo e implementação

Adicionar duas páginas estáticas ao site existente da Ponte São João, no domínio atual `https://www.pontesaojoaoimplantes.com.br`, para campanhas separadas: `/clinica-geral/` e `/urgencia-odontologica/`. Preservar a página de implantes e os ativos e padrões visuais já publicados. Criar HTML semântico em `public/<rota>/index.html` para que conteúdo, título, descrição, canonical e metadados sociais estejam disponíveis no HTML inicial. Ajustar `server.mjs` para servir `index.html` em diretórios, sem mascarar rotas inexistentes. Atualizar `public/manus-routes.json` para declarar as três páginas públicas.

Cada página terá título, descrição, palavras-chave, canonical, Open Graph, Twitter Card e dados estruturados coerentes com a clínica, usando o domínio público atual e imagens já versionadas em `public/assets/`. CTAs vão para o WhatsApp ou telefone oficial; as mensagens indicam o assunto da página. O `public/main.js` existente continuará registrando cliques com canal, posição e parâmetros UTM, sem enviar sintomas ou dados pessoais. A home ganhará ligações explícitas para as duas páginas e o rodapé/nav das páginas permitirá retornar ao site.

Clínica Geral será baseada no conteúdo antigo sobre prevenção, higiene oral, cáries, saúde periodontal e consultas regulares, com linguagem informativa e sem diagnóstico ou promessa de resultado. Urgência esclarecerá que existe atendimento odontológico de urgência 24 horas, mas somente mediante contato/agendamento prévio e confirmação de disponibilidade; não prometerá atendimento imediato ou contínuo. Ambas informarão que o atendimento é particular e não atende convênios, e convidarão o visitante a confirmar detalhes com a equipe.

## Estrutura do projeto

- `public/index.html`: página institucional atual; recebe acesso visível às novas páginas.
- `public/clinica-geral/index.html`: landing page indexável de Clínica Geral.
- `public/urgencia-odontologica/index.html`: landing page indexável de Urgência.
- `public/styles.css`: estilos responsivos compartilhados e estilos pontuais das novas páginas.
- `public/main.js`: menu e mensuração atual de chamadas para WhatsApp/telefone, preservados.
- `public/manus-routes.json`: manifesto das rotas HTML.
- `server.mjs`: servidor local para diretórios com `index.html` e respostas 404 reais.
- `scripts/build.mjs`: cópia existente de `public/` para `dist/`, sem nova dependência.

## Design

**Movimento:** reutilizar o editorial acolhedor e contemporâneo já presente no site, com referências a revistas de saúde e hospitalidade. **Princípios:** consistência com a home; leitura rápida no celular; informação prática antes de conteúdo complementar; linguagem cuidadosa, clara e sem exageros. **Cores:** azul-marinho para confiança, terracota para ações e destaques, fundos creme para manter continuidade com a identidade atual. **Layout:** hero com texto e foto real do consultório, blocos assimétricos de informação, sequência breve de próximos passos, FAQ e contato/localização. **Elementos-assinatura:** detalhes tipográficos em Playfair Display, pequenas etiquetas de seção em terracota e cartões/linhas finas em creme e azul. **Interação:** WhatsApp e telefone evidentes, navegação para a home e para a outra página, âncoras de FAQ simples e operáveis por teclado. **Animação:** conservar transições discretas existentes e respeitar `prefers-reduced-motion`; não adicionar movimento que distraia de uma página de atendimento. **Tipografia:** Playfair Display para títulos e DM Sans para leitura e interface, usando os tamanhos e contrastes do projeto. **Essência da marca:** clínica odontológica de Jundiaí que oferece escuta e acesso claro a diferentes áreas de cuidado; personalidade próxima, cuidadosa e profissional. **Voz:** frases diretas e serenas; CTAs descrevem a ação, sem garantias clínicas. Exemplos: “Conte à equipe o que está acontecendo.” e “Confirme pelo WhatsApp a disponibilidade para atendimento de urgência.” **Marca:** preservar o logotipo oficial existente sem redesenhá-lo. **Cor proprietária:** manter o azul da marca `#184080` e o terracota de ação `#dc6c3d`.

## Limites

A alteração prepara páginas de destino, mas não configura campanhas, palavras-chave, tags de conversão no Google Ads ou acesso ao Google Tag Manager. A publicação ocorrerá pelo fluxo já existente do repositório/branch principal; nenhum domínio ou projeto de hospedagem será reconfigurado.
