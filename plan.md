# Plano — páginas de Clínica Geral e Urgência

## Escopo e implementação

Adicionar duas páginas estáticas ao site Ponte São João para campanhas independentes: `/clinica-geral` e `/urgencia-odontologica`, sob o domínio atual `https://www.pontesaojoaoimplantes.com.br`. Preservar a página de implantes, seus ativos e padrões visuais. Criar HTML semântico em `public/<rota>/index.html` para que conteúdo, títulos, descrições, canonicals e metadados sociais estejam presentes no HTML inicial. Ajustar `server.mjs` para servir `index.html` em diretórios e devolver 404 para rotas inexistentes. Atualizar `public/manus-routes.json` para declarar as três páginas públicas.

Cada página terá title, description, canonical, Open Graph, Twitter Card e dados estruturados próprios, usando imagens já versionadas em `public/assets/`. Adicionar `public/sitemap.xml` e `public/robots.txt`. CTAs usarão o WhatsApp ou telefone oficial, com mensagens que identifiquem o assunto da página. O `public/main.js` continuará registrando cliques de contato, canal, posição e parâmetros UTM, sem coletar sintomas ou dados pessoais. A página inicial oferecerá links explícitos às novas páginas, com navegação de retorno e entre elas.

Clínica Geral será baseada no conteúdo antigo sobre prevenção, higiene oral, cáries, saúde periodontal e consultas regulares, sem diagnóstico ou promessa de resultado. Urgência explicará que existe atendimento odontológico de urgência 24 horas, somente mediante contato/agendamento prévio e confirmação de disponibilidade; sem prometer atendimento imediato ou contínuo. Ambas informarão atendimento particular e não aceitação de convênios, e orientarão o visitante a confirmar detalhes com a equipe.

## Estrutura do projeto

- `public/index.html`: página institucional atual; recebe acesso visível às novas páginas.
- `public/clinica-geral/index.html`: landing page de Clínica Geral.
- `public/urgencia-odontologica/index.html`: landing page de Urgência.
- `public/styles.css`: estilos responsivos compartilhados e regras pontuais.
- `public/main.js`: navegação e mensuração existente de contato, preservadas.
- `public/manus-routes.json`: manifesto de rotas HTML.
- `public/sitemap.xml` e `public/robots.txt`: sinais básicos de rastreamento.
- `server.mjs`: servidor local para `index.html` de diretórios e respostas 404.
- `scripts/build.mjs`: copia os arquivos de `public/` para `dist/`, sem dependência nova.

## Design

**Movimento:** reutilizar o editorial acolhedor e contemporâneo do site atual, com referências a revistas de saúde e hospitalidade. **Princípios:** consistência com a home; leitura rápida no celular; informação prática antes de conteúdo complementar; linguagem cuidadosa, clara e sem exageros. **Cores:** azul-marinho para confiança, terracota para ações/destaques e creme para continuidade visual. **Layout:** hero com texto e foto real do consultório, blocos de informação, sequência breve de próximos passos, FAQ e contato/localização. **Elementos-assinatura:** títulos em Playfair Display, etiquetas pequenas em terracota e cartões/linhas em creme e azul. **Interação:** WhatsApp e telefone evidentes, navegação entre home e as duas páginas, FAQ nativa acessível por teclado. **Animação:** conservar transições discretas e respeitar `prefers-reduced-motion`. **Tipografia:** Playfair Display para títulos e DM Sans para leitura/interface. **Essência da marca:** clínica odontológica de Jundiaí com comunicação próxima, cuidadosa e profissional. **Voz:** frases diretas e serenas; CTAs sem prometer resultados clínicos. **Marca:** preservar a logomarca oficial. **Cores de referência:** azul `#184080` e terracota `#dc6c3d`.

## Limites e estado da publicação

A implementação foi validada localmente, registrada no commit `d002248` e enviada à branch `main` do repositório informado. A alteração não configura campanhas, palavras-chave ou tags de conversão no Google Ads. A verificação de produção em 13/11/2026 retornou 404 para as novas rotas; não há vínculo ou automação Vercel visível neste repositório. Portanto, a publicação no domínio está pendente de acesso/autorização ao projeto Vercel correto. Não reconectar o repositório nem alterar o projeto/domínio de hospedagem sem autorização explícita.
