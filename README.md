# PBr₃ — Laboratório molecular

Visualização interativa do tribrometo de fósforo, em português. Aplicativo estático sem dependências, CDN, instalação de pacotes, backend ou conexão obrigatória à internet.

## Usar

Abra `index.html` em um navegador moderno. Para servir localmente, execute `python -m http.server 8000` nesta pasta e acesse http://localhost:8000.

- Arraste para girar livremente. Use a roda do mouse, a pinça ou o controle de zoom para ampliar.
- No canvas focado, use as setas para girar, +/− para zoom e Home para restaurar.
- Clique/toque em um átomo ou selecione P, Br₁, Br₂ e Br₃ pelo painel de informações.
- Compare esferas e varetas, varetas, espaço preenchido, nuvens esquemáticas e Lewis.
- Ative os 6 elétrons ligantes, os 20 elétrons em pares livres, o ângulo e a polaridade.
- O modo espaço preenchido oculta os elétrons para preservar a visualização do volume. Lewis mostra todos os 26 elétrons e desativa os controles exclusivos de 3D.

## Publicar pelo GitHub Actions

1. Crie ou escolha um repositório no GitHub. O Pages precisa estar disponível para a visibilidade/plano desse repositório.
2. Envie `index.html` e `.github/workflows/pages.yml`, preservando a pasta `.github`. O workflow usa a branch `master`; altere `branches` se sua branch padrão tiver outro nome.
3. No repositório, abra **Settings → Pages → Build and deployment → Source → GitHub Actions**.
4. Abra **Actions → Publicar laboratório molecular → Run workflow** ou envie um novo commit à `master`.
5. Após a execução concluir, abra o endereço mostrado no ambiente `github-pages`.

O workflow publica somente `index.html` e `.nojekyll`. Não exige token pessoal, secrets, npm ou build de JavaScript. O `GITHUB_TOKEN` recebe `pages: write` e `id-token: write` apenas no job de publicação. O pacote foi preparado para implantação; uma execução real depende do acesso e das configurações do repositório.

## Precisão científica

As coordenadas nucleares seguem o NIST CCCBDB para PBr₃ (CAS 7789-60-8), com permutação dos eixos para visualização. Distância P–Br ≈ 2,220 Å e ângulo Br–P–Br ≈ 101°. A geometria molecular é piramidal trigonal (C₃ᵥ), com classificação VSEPR AX₃E e quatro domínios eletrônicos no P. A molécula é polar.

São 26 elétrons de valência: 3 pares ligantes (6 elétrons), 1 par livre no P (2 elétrons) e 3 pares livres em cada Br (18 elétrons). Cargas formais de todos os átomos são zero na estrutura de Lewis. As configurações eletrônicas do painel são dos átomos neutros isolados, não de orbitais moleculares.

Os elétrons pontuais, nuvens, raios das esferas e direções dos pares livres são representações didáticas. Não são cálculos de orbitais, densidade eletrônica nem trajetórias de elétrons. δ+/δ− representam polarização qualitativa. O modo Lewis é plano e não preserva ângulos.

A renderização projeta coordenadas 3D com perspectiva sobre Canvas 2D e ordenação de profundidade; não depende de WebGL. Nuvens translúcidas e sobreposições usam aproximações gráficas.

## Fontes

- Geometria experimental: https://cccbdb.nist.gov/exp2x.asp?casno=7789608&charge=0
- Workflow oficial do GitHub Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages
