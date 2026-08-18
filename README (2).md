# A Ilha do Mapa Perdido 🏴‍☠️

Jogo de exploração em 3ª pessoa (Three.js), primeira fase, baseado no documento de design.
Um único arquivo (`index.html`), sem build step — roda direto no navegador, em PC e celular.

## O que está implementado

- Personagem em 3ª pessoa: andar, correr, pular, câmera orbital (mouse/touch), colisão simples com objetos
- Navio explorável: convés, mastro/vela, leme, cabine (mesa, cama, cadeira), baú, barris e caixas empurráveis, lanternas ligáveis/desligáveis
- Ilha com praia, vegetação (palmeiras, arbustos, pedras reaproveitados), uma ruína e um mirante
- Oceano animado (ondas por vértice, sem custo de geometria excessivo) e céu com sol e nuvens
- Sistema de interação via raycaster ("[E] Interagir" no PC, botão "AGIR" no celular)
- Inventário simples (mapa, moedas, chaves) e missão "Onde está o mapa?" com checklist ao vivo
- Overlay do mapa (desenhado em `<canvas>` 2D) marcando o ponto da ruína
- Tela de "FASE 1 CONCLUÍDA"
- Controles mobile: joystick virtual + arraste para câmera + botões de ação
- Áudio ambiente leve via Web Audio API (opcional, botão 🔈 no topo)

## Como jogar localmente

Não precisa de instalação. Só não pode abrir o `index.html` direto com `file://` porque o navegador
bloqueia o `import` de módulos ES nesse esquema — precisa de um servidor local simples:

```bash
cd pasta-do-projeto
python3 -m http.server 8000
# depois abra http://localhost:8000 no navegador
```

(ou `npx serve` se preferir Node.)

## Como subir no GitHub e publicar com GitHub Pages

1. Crie um repositório novo no GitHub (pode ser público), por exemplo `ilha-do-mapa-perdido`.
2. Na pasta do projeto:

```bash
git init
git add index.html README.md
git commit -m "Fase 1: A Ilha do Mapa Perdido"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/ilha-do-mapa-perdido.git
git push -u origin main
```

3. No GitHub, vá em **Settings → Pages**.
4. Em "Build and deployment", escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
5. Salve e aguarde ~1 minuto. O jogo ficará em:
   `https://SEU_USUARIO.github.io/ilha-do-mapa-perdido/`

Como é um único arquivo HTML com o Three.js carregado via CDN (unpkg), não há build step nem
dependências para instalar — igual ao padrão que você já usa nos seus outros projetos.

## Controles

**PC**
- `WASD` — mover
- Mouse (arrastar) — câmera
- `Shift` — correr
- `Espaço` — pular
- `E` — interagir

**Celular**
- Joystick à esquerda — mover
- Arrastar à direita — câmera
- Botões CORRER / AGIR / PULAR

## Próximos passos sugeridos (fora do escopo desta fase)

- Controlar o navio a partir do leme (navegação até outra ilha)
- Sistema de combate
- Ciclo dia/noite
- Sons reais (arquivos de áudio) no lugar do áudio procedural
- Multiplayer

Esses itens já estão marcados como "fora da primeira fase" no documento de design original.
