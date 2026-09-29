# Visualizador 3D de produtos

Visualizador 3D interativo para páginas de produto, feito com [`<model-viewer>`](https://modelviewer.dev/), publicado no GitHub Pages e embutido no WordPress por iframe.

**Demo:** https://lucasmede1ros.github.io/3d/

## Como funciona

- Uma única página (`index.html`) carrega o modelo `.glb` do produto e o exibe com `model-viewer`.
- O WordPress incorpora a página com um `<iframe>`. Todos os produtos usam a mesma URL, e só o parâmetro que indica o modelo muda.
- Os controles do visualizador são definidos por campos do ACF no WordPress, sem precisar editar código.
- Cada produto tem a sua própria pasta de modelos.

## Destaques técnicos

- **Modelos otimizados:** arquivos `.glb` com texturas comprimidas em **KTX2**, para carregar mais rápido sem abrir mão da qualidade visual.
- **Compatibilidade:** ajustes para diferenças entre navegadores e para limitações de GPU em dispositivos móveis.
- **Integração simples:** trocar o produto exige alterar um único parâmetro na URL do iframe.
- **Hospedagem estática:** HTML publicado direto pelo GitHub Pages, sem servidor próprio.

## Como usar

<!-- Troque PARAMETRO pelo nome real do parâmetro lido no index.html -->
```html
<iframe
  src="https://lucasmede1ros.github.io/3d/?PARAMETRO=NOME-DO-MODELO"
  width="100%"
  height="600"
  style="border:0"
  allow="fullscreen"
  loading="lazy"
  title="Visualizador 3D do produto">
</iframe>
```

## Estrutura

```
3d/
├── index.html
├── robots.txt
├── cycles/
├── cycles-z/
├── donek-s/
├── freefire/
├── halley/
├── omega-s/
└── super-nova-signature/
```

## Adicionando um produto

1. Otimize o `.glb` (texturas em KTX2).
2. Crie a pasta do produto, com o nome em minúsculas e sem espaços, e coloque o modelo dentro.
3. Faça commit e push na branch `main`. O GitHub Pages publica automaticamente.
4. No WordPress, ajuste o parâmetro do iframe do produto.

## Aviso

Os modelos 3D e as marcas presentes neste repositório pertencem aos seus respectivos titulares. O código não possui licença de uso aberta.
