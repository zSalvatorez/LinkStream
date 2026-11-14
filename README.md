# LinkStream

Programa para quem joga no PC, tudo numa janela só:

- **Grava** os jogos em até 4K HDR, com a qualidade máxima da sua placa de vídeo.
- **Replay**: guarda sempre os últimos minutos. Aconteceu algo legal? Um atalho salva.
- **Live no YouTube** (até 4K HDR), com o **chat por cima do jogo**.
- **Link para os amigos** assistirem quase sem atraso, de qualquer lugar, sem instalar nada.
- **Cenas**, como no OBS: face cam, QR de doação, logo, textos, o jogo num quadro menor com um fundo atrás.
- **Overlay de estatísticas** por cima do jogo (FPS, frametime, GPU, CPU, temperaturas, RAM, VRAM), no estilo
  do MSI Afterburner/RivaTuner.

![Janela principal do LinkStream](imagens/janela-principal.png)

> Versão de teste. Se achar qualquer problema, avisa (veja "Como relatar um problema" lá embaixo).

### Novidades da versão 1.3

- **Identidade própria:** preto, branco e prata, novo logo e ícones. Online verde, Ausente amarelo e Não perturbe vermelho.
- **Grupos e conversas:** grupos na lateral direita e chat no centro, com texto, links, histórico e reenvio. O criador ativa a conversa quando quiser; listas anteriores continuam privadas.
- **Público da transmissão:** todos os amigos, pessoas escolhidas ou grupos. É preciso entrar na conta autorizada para assistir, inclusive no navegador.
- **Conversas e Ao vivo:** ao assistir, a tela abre na aba Ao vivo; voltar ao chat mantém o player e o som.
- **Janela redimensionável:** o tamanho inicial virou o mínimo; permite ampliar e maximizar. Os controles da gravação foram reorganizados para aproveitar a tela e caber no tamanho mínimo.
- **Prévia mais nítida e fluida**, com contador do FPS real. A taxa depende do computador; a gravação mantém a qualidade configurada.
- **Revisão do acesso às transmissões e do encerramento das conexões.** A conexão direta e o túnel de reserva continuam sendo usados.

Quem já tem instalado pode usar **Ajustes → Geral → Procurar atualizações**. O app baixa o instalador e abre novamente; ajustes, cenas e vídeos são preservados. Atualize também o app dos amigos. Grupos com conversa ativa dão acesso ao histórico anterior a quem entrar depois.

## Requisitos

- Windows 10 ou 11, 64 bits.
- Placa de vídeo NVIDIA (melhor), AMD ou Intel. Sem placa compatível, grava pelo processador (só SDR e até Full HD).
- Uns 1,5 GB livres no disco do Windows, mais o espaço dos vídeos e do replay.
- Webcam (opcional), para a face cam.

## Como instalar

1. Baixe o **LinkStreamSetup.exe** (em **Releases**, aqui ao lado). Tem uns 180 MB.
2. Abra. Como o programa não tem assinatura digital, o Windows mostra **"O Windows protegeu o computador"**:
   clique em **Mais informações → Executar assim mesmo**.
3. Logo em seguida o Windows pede **uma permissão só** (tela com fundo escuro): clique em **Sim**. É a única vez; com
   ela o instalador deixa tudo pronto de uma vez, sem perguntar mais nada:
   - instala o programa (com o OBS próprio, o servidor do link, o FFmpeg etc.);
   - instala o driver **PawnIO** (gratuito, código aberto, assinado), que lê a temperatura do processador;
   - libera o **FPS** do overlay (coloca seu usuário no grupo "Usuários de log de desempenho");
   - libera o **link** no Firewall do Windows (ele não pergunta "Permitir acesso?" quando você liga o link).
4. Clique em **Instalar**. Ele instala em `AppData\Local\Programs\LinkStream`, cria atalho no menu Iniciar
   (e na área de trabalho, se quiser) e aparece em "Aplicativos instalados" para desinstalar.
5. Para o FPS aparecer, **saia e entre de novo no Windows** (ou reinicie) uma vez.

Tudo o que o programa precisa vai junto (OBS próprio, FFmpeg, servidor do link, runtime do Visual C++): não precisa
instalar mais nada, e o seu OBS normal (se tiver) não é mexido. Para atualizar: ⚙ Ajustes → **Procurar atualizações**
(ou rodar o instalador novo por cima). Os seus ajustes e cenas ficam.

## Primeiros passos

- O LinkStream abre junto com o Windows, escondido perto do relógio. Clique duas vezes no ícone para abrir (ou clique
  no ícone dele na barra de tarefas / menu Iniciar). Para não abrir com o Windows: ⚙ Ajustes → "Iniciar com o Windows".
- Ele **detecta o jogo sozinho**. Em **Vídeo** (à direita) dá para escolher um jogo, uma janela ou a área de trabalho.
- **Atalhos** (funcionam dentro do jogo): `Ctrl+Alt+R` gravar · `Ctrl+Alt+S` salvar replay · `Ctrl+Alt+Y` YouTube ·
  `Ctrl+Alt+L` link · `Ctrl+Alt+O` overlay · `Ctrl+Alt+P` próxima posição da câmera. Dá para trocar em ⚙ Ajustes (e o do overlay na aba Estatísticas).
- **Controle** (Xbox ou PlayStation): segure **Select/View/Share** e aperte **Y** gravar · **B** replay · **X** print ·
  **A** live · **LB/L1** overlay · **RB/R1** próxima posição da câmera.
- Os vídeos ficam em `Vídeos\LinkStream` (botão **Abrir vídeos**).
- O manual completo vem junto: `COMO-USAR.md`, na pasta do programa.

## Live no YouTube

Cole a sua **chave de transmissão** em ⚙ Ajustes (YouTube Studio → Criar → Transmitir ao vivo → Stream) uma vez.
Depois é só clicar em **YouTube**: abre esta janelinha, onde dá para ajustar a live no YouTube Studio, informar o seu
canal (para o **chat aparecer por cima do jogo** e na live) e escolher a **cena**.

![Janelinha antes de abrir a live](imagens/janela-da-live.png)

**A live entrou no ar?** Depois de ~1 minuto o LinkStream confere no seu canal. Se o YouTube estiver recebendo o vídeo
mas a live não estiver no ar, ele reabre sozinho (até 2 vezes) e avisa por cima do jogo. Funciona com live **pública**
(ou não listada com o link colado na janelinha).

**Transmissão dupla / live vertical (Shorts):** o YouTube às vezes liga sozinho a "Transmissão dupla" e aí espera também
um vídeo vertical. Para o LinkStream mandar a vertical: no YouTube Studio → Transmitir ao vivo, deixe a parte vertical em
**"Codificador"**, copie a **"Chave: Vertical"** e cole em ⚙ Ajustes → **"Chave vertical (Shorts)"**. O LinkStream manda o
meio da tela em 1080x1920 só quando o YouTube pedir (ou sempre, se preferir).

## Cenas: face cam, QR de doação, overlays (novo)

Por padrão a cena é **Nenhum**: sai só o jogo, como sempre. Se quiser, monte cenas como no OBS e escolha qual usar no
seletor ao lado de "Gravar e transmitir". A cena vale para tudo: gravação, replay, live e link.

O botão **🎬 Cenas** abre o editor:

![Editor de cenas](imagens/editor-de-cenas.png)

- **＋ Adicionar fonte**: **imagem / overlay** (QR de doação, logo, moldura, fundo, GIF), **webcam** (face cam),
  **texto** (ex.: "!pix no chat"), **janela de outro programa** ou **vídeo em loop**.
- A **Captura (jogo / tela)** também é uma fonte: dá para deixar o jogo num quadro menor, com um fundo atrás.
- Na prévia: **arraste** para mover, puxe os **cantos** para mudar o tamanho (Shift = livre), **Delete** remove.
  Botão direito: frente/trás, tela cheia, centralizar. Borda com cor e espessura em qualquer fonte (ex.: moldura da face cam).
- Na lista: a de cima fica na frente, a caixinha mostra/esconde.
- **✔ Salvar** grava. Marque **"Deixar esta cena como principal"** para ela já ficar escolhida.

Com a cena do exemplo acima, a live fica assim:

![Como a cena aparece na live](imagens/cena-na-live.png)

## Overlay de estatísticas

Aba **📊 Estatísticas**: perfis Mínimo, Médio, Máximo ou Personalizado, posição, tamanho e se aparece também no
vídeo/live. Liga e desliga com `Ctrl+Alt+O` ou **Select + LB** no controle. Não injeta nada no jogo (sem risco com anti-cheat).

![Overlay de estatísticas por cima do jogo](imagens/overlay-estatisticas.png)

*(números de exemplo, sobre um jogo de demonstração)*

## Link para os amigos

Clique em **Ligar link**: o endereço já fica copiado, é só colar para os amigos (o botão **Copiar link** copia de novo). Abre no navegador do PC ou do celular, sem instalar
nada, quase sem atraso. Quem abre o link de mais de um amigo vê todas as telas na mesma aba, lado a lado; passe o mouse
numa tela para o som, o volume, a tela cheia ou para abrir em outra aba.
O endereço muda a cada
vez que o LinkStream abre, e só funciona enquanto o link está ligado.

## O que testar (ajuda muito!)

- Gravar e salvar replay num jogo.
- Live no YouTube e o link para os amigos.
- Cenas: face cam, imagem (QR/logo), texto, o jogo num quadro menor; e voltar para "Nenhum".
- Overlay de estatísticas: liga/desliga pelo atalho e pelo controle, perfis, posição, e a opção "No vídeo".
- Atalhos de teclado e do controle dentro do jogo.
- Tela cheia, sem bordas, monitor HDR, mais de um monitor, TV pelo Steam Big Picture.

## Como relatar um problema

Conte **o que fez, o que esperava e o que aconteceu**, e mande junto:

- o arquivo de registro: `%LOCALAPPDATA%\Programs\LinkStream\dados\linkstream.log`
  (cole esse caminho na barra do Explorador de Arquivos);
- sua placa de vídeo, processador e versão do Windows;
- um print, se for algo na tela.

**Não mande** os outros arquivos da pasta `dados`: eles têm a sua chave do YouTube e senhas.

## Desinstalar

Configurações → Aplicativos → Aplicativos instalados → **LinkStream** → Desinstalar. Os vídeos salvos ficam.
O driver PawnIO fica (outros programas também usam); para tirar, desinstale **PawnIO** na mesma lista.

## Programas que vão junto

OBS Studio (GPL-2.0), MediaMTX (MIT), cloudflared (Apache-2.0), FFmpeg (GPL, build do Gyan), PresentMon da Intel (MIT),
driver PawnIO e módulos da LibreHardwareMonitorLib (MPL-2.0). Licenças e links do código: nas pastas `bin\` de cada um
(`bin\sensores\LEIA-ME.txt` para o PawnIO) e em https://github.com/cloudflare/cloudflared para o cloudflared.
