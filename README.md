<p align="center">
  <img src="docs/images/banner.svg" alt="Batman Begins Recomp" width="100%">
</p>

# Batman Begins Recomp — KM Tecnologia

Port não oficial para PC de **Batman Begins (2005)**, versão original do Xbox,
usando recompilação estática. O código do jogo é recompilado localmente a partir
da cópia do usuário; não há emulação nem BIOS do Xbox.

> **Aviso:** este projeto não distribui ISO, assets ou código recompilado do
> jogo. Use somente uma cópia legalmente adquirida da versão americana.

## Download

Baixe o pacote para Windows x64 no
[Release v1.1.0](https://github.com/kmtecnologia/BatmanBeginsRecomp/releases/tag/v1.1.0).

Para instalação, controles, Proton e solução de problemas, consulte o
[Guia do usuário](docs/GUIA.md).

## Estado do projeto

- Campanha jogada até os créditos.
- Menus, vídeos, salvamento, teclado e controles funcionando.
- 30 FPS é o modo padrão do jogo.
- 60 FPS está disponível como opção nas configurações; 30 FPS continua sendo
  o modo padrão.
- A sequência do helicóptero foi corrigida e validada em gameplay a 60 FPS.
- O Release Windows foi testado com sucesso no Linux através do Proton.
- Não existe build nativo para Linux.
- Steam Deck ainda não foi testado separadamente.

## Requisitos

- Windows 10 ou 11 de 64 bits, ou Linux com Proton compatível.
- CPU x86-64 com SSE4.2 e POPCNT.
- GPU com suporte a Direct3D 12; no Linux, o Proton precisa traduzir essa
  funcionalidade.
- Cópia da versão americana de Batman Begins para Xbox em ISO ou arquivos
  extraídos.
- Aproximadamente 8,5 GB de espaço com a ISO e os arquivos recompilados.

## Instalação rápida

1. Baixe `BatmanBegins.zip` no Release e extraia-o.
2. Coloque sua ISO americana, ou os arquivos extraídos do disco, na pasta
   `assets`.
3. Execute `BatmanBegins.exe`.
4. Na primeira execução, aguarde o compilador preparar o código do jogo.
5. Quando aparecer **The game is ready**, pressione Start.

O primeiro carregamento pode levar alguns minutos, dependendo do computador.
O jogo cria saves, configurações, logs e cache de shaders na própria pasta.

## Controles padrão

| Ação | Teclado | Controle |
|---|---|---|
| Movimento | W, A, S, D | Analógico esquerdo |
| Câmera | I, J, K, L | Analógico direito |
| Pular | Espaço | A |
| Ação | C | B |
| Soco | E | X |
| Chute | Q | Y |
| LT / RT | Shift esquerdo / Ctrl esquerdo | LT / RT |
| Start / Back | Enter / Backspace | Start / Back |
| Opções | Esc | Back + Start |

Os controles podem ser alterados na tela de opções.

## Compilação do código-fonte

Para modificar o projeto, consulte o [Guia do desenvolvedor](docs/GUIA.md) e
o [guia técnico](docs/TECHNICAL.md).

O projeto usa Visual Studio com ferramentas C++, Clang, CMake, Git e Python.
Os assets do jogo ficam fora do Git e o código recompilado é gerado localmente.

## Créditos e licença

Este fork é baseado em
[christiansmmc/BatmanBeginsRecomp](https://github.com/christiansmmc/BatmanBeginsRecomp)
e usa o [Xbox XBE Recomp](https://github.com/TGP482/XboxXBE-Recomp).
Créditos adicionais e licenças estão em `LICENSE`, `THIRD_PARTY.txt` e nos
arquivos de licença incluídos no Release.

Batman Begins foi desenvolvido pela Eurocom. Batman e os elementos relacionados
são marcas e propriedades da DC Comics. Este projeto não é afiliado nem
endossado pela Warner Bros., DC, Electronic Arts ou Eurocom.
