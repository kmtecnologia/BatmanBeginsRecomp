# Guia do Batman Begins Recomp — KM Tecnologia

Este documento explica como instalar, executar e diagnosticar o port publicado
no fork da KM Tecnologia.

## 1. Baixar o port

Use o arquivo `BatmanBegins.zip` no
[Release v1.1.0](https://github.com/kmtecnologia/BatmanBeginsRecomp/releases/tag/v1.1.0).
O pacote contém o executável, o compilador usado na primeira execução e as
licenças necessárias. Ele não contém o jogo.

## 2. Atualizar da versão 1.0.0

1. Baixe o `BatmanBegins.zip` do Release `v1.1.0`.
2. Extraia-o em uma nova pasta.
3. Copie a pasta `assets` da instalação antiga para a nova, ou coloque nela
   novamente a sua ISO.
4. Copie `hdd`, `settings.toml` e, se desejar, `shaders.cache` da instalação
   antiga para a nova.
5. Execute o novo `BatmanBegins.exe`.

Não é necessário copiar a pasta `compiler`; ela será recriada pela nova versão.
Os saves ficam em `hdd\E\UDATA` e devem ser mantidos para continuar a campanha.

## 3. Adicionar o jogo

O port aceita somente a versão americana de Batman Begins para Xbox.

1. Extraia o ZIP em uma pasta com espaço livre.
2. Abra a pasta `assets`.
3. Coloque ali a ISO do jogo ou os arquivos extraídos do disco.
4. Não modifique a ISO original.

O executável verifica a versão do `default.xbe` na inicialização. Outras regiões
ou versões são recusadas.

## 4. Primeira execução

Execute `BatmanBegins.exe`. Uma janela de progresso recompila o código do jogo
localmente. Esse processo acontece uma vez e pode levar de menos de um minuto a
alguns minutos.

Se a janela for fechada, a próxima execução continua de onde parou. Quando
aparecer **The game is ready**, pressione Start. Os logos iniciais podem levar
cerca de 45 segundos.

Não feche o jogo enquanto a mensagem de salvamento estiver na tela. Para sair,
pause, use Save / Quit e salve o último checkpoint antes de pressionar Alt+F4.

## 5. Linux usando Proton

O executável distribuído é para Windows, mas foi testado com sucesso no Linux
através do Proton.

1. Adicione `BatmanBegins.exe` à Steam como jogo não Steam, ou execute-o pelo
   launcher compatível com Proton.
2. Selecione Proton Experimental ou uma versão recente do Proton.
3. Mantenha a pasta `assets` ao lado do executável.
4. Inicie o jogo e aguarde a recompilação inicial.

Este projeto ainda não possui build nativo para Linux. Steam Deck não foi
validado separadamente.

## 6. Arquivos criados pelo jogo

Todos ficam na pasta do port:

- `assets`: ISO ou arquivos do jogo.
- `hdd\E\UDATA`: saves.
- `settings.toml`: configurações.
- `logs`: logs das últimas sessões.
- `CrashDumps`: relatórios de encerramentos por erro.
- `shaders.cache`: cache dos shaders.
- `compiler`: arquivos usados somente na recompilação inicial.

Depois que o jogo estiver pronto, a própria janela oferece a opção de remover
os arquivos do compilador. Faça isso somente se não precisar recompilar.

## 7. Solução de problemas

### O jogo recusa o arquivo

Confirme que a cópia é a edição americana suportada e que `default.xbe` está
presente em `assets`. Não use uma ISO de outra região.

### O jogo fecha ou trava

Verifique primeiro `logs\batman.log`. Se houver uma pasta `CrashDumps`, envie o
arquivo mais recente junto com o log. Não envie a ISO ou os arquivos do jogo.

### O primeiro carregamento parece parado

A recompilação inicial pode demorar em computadores com menos núcleos. Aguarde
alguns minutos; se a janela for fechada, o processo pode continuar depois.

### Há travamentos ao aparecer um efeito novo

Isso pode ocorrer na primeira compilação de shaders. O cache é salvo em
`shaders.cache` e os efeitos normalmente não repetem o mesmo atraso.

## 8. Configurações recomendadas

- Use 30 FPS para a experiência mais próxima do comportamento original.
- Use 60 FPS apenas como opção experimental.
- Use 4:3 para manter a proporção original dos menus e HUD, ou 16:9 para
  widescreen.
- A tela de opções abre com Esc, ou com Back + Start no controle.

## 9. Desenvolvimento

Para alterar o código, instale Visual Studio com desenvolvimento C++, ferramentas
Clang e CMake, além de Git e Python 3.10 ou superior. Os testes e instruções de
compilação ficam no próprio repositório; a análise de arquitetura está em
[TECHNICAL.md](TECHNICAL.md).

O repositório não deve receber ISO, assets, DLLs geradas, executáveis ou código
recompilado do jogo.
