Estado ANTERIOR
•	index (1).html
•	Importava 
style.css: <link rel="stylesheet" href="style.css" />
•	Banner:
•	<img src="imagem/banner.webp" alt= "Banner da Barbearia" class="img-fluid banner-img" />
•	Bootstrap já vinha via CDN minificado (CSS e bootstrap.bundle.min.js).
•	Havia apenas o script inline de inicialização dos carrosséis.
•	style.min.css, não existia antes (foi criado por mim).

<img width="1990" height="815" alt="image" src="https://github.com/user-attachments/assets/0d5a5c1f-7b59-4a38-bb76-a39f78949015" />


# Otimizações de Performance — Projeto Web

Este documento descreve todas as ações realizadas para melhorar o tempo de carregamento, reduzir peso desnecessário e otimizar métricas como LCP, CLS e INP.
As mudanças foram aplicadas de forma segura, sem alterar a estrutura principal da página.

---

## Ações Realizadas

### Imagens

* Banner mantido sem `loading="lazy"`, por ser uma imagem acima da dobra. Aplicar lazy load prejudicaria o Largest Contentful Paint (LCP).
* Não há outras tags `<img>` no projeto que possam receber lazy loading.

### Minificação de CSS

* Criado o arquivo `style.min.css`, totalmente minificado.
* O HTML foi atualizado para importar apenas o arquivo minificado.
* O CSS antigo (`style.css`) deixou de ser utilizado.

### Remoção de trechos não utilizados

* O arquivo `style.min.css` agora contém somente regras realmente aplicadas ao HTML.
* Estilos não utilizados foram removidos para reduzir peso.
* O script inline foi mantido apenas com a inicialização dos carrosséis, necessária para o funcionamento.

### Imports enxutos

* O projeto utiliza Bootstrap minificado via CDN:

  * `bootstrap.min.css`
  * `bootstrap.bundle.min.js` (inclui Popper, necessário para o Carrossel)
* Não foram adicionados recursos além do essencial.

---

## O que Foi Alterado

### HTML

* Atualizado o arquivo `index (1).html`.
* Atualizado para usar `style.min.css`.
* Mantida a imagem principal do banner sem lazy loading para evitar impacto negativo no LCP.

### CSS

* O arquivo `style.css` foi substituído por `style.min.css`.
* Conteúdo reduzido e otimizado, contendo apenas estilos usados:

  * Controles de setas dos carrosséis
  * Caixa de depoimentos
  * Classe `.preco`
  * `.banner-img` e `.titulo-banner`

---

## Resultado Esperado

* Redução do tamanho total do CSS
* Menos bytes transferidos
* Melhora no LCP ao manter a imagem acima da dobra carregando imediatamente
* Funcionamento correto dos carrosséis
* Página mais leve e eficiente
  
<img width="2000" height="825" alt="image" src="https://github.com/user-attachments/assets/8cd3d617-4ea8-4a4d-b840-93591ad25342" />


