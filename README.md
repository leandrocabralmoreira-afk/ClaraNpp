# Clara Markdown — Versão 1 (protótipo compilável)

O Clara Markdown é um plugin para a versão portátil x64 do Notepad++. A proposta desta versão é manter o editor original e acrescentar uma barra de comandos Markdown.

## Recursos da versão 1

- Mantém as funcionalidades originais do Notepad++.
- Barra Markdown registrada como painel acoplável na região superior do editor (quando suportado pelo Notepad++); se o registro falhar, usa uma janela simples.
- Comandos para negrito, itálico, tachado, títulos H1/H2/H3, listas com marcadores e numeradas, links, imagens por caminho, código inline, citações, linha horizontal, tabelas e blocos de código.
- Formata o texto selecionado; para títulos/listas/citações, prefixa cada linha selecionada.
- Usa Markdown padrão e permite salvar arquivos `.md` pelo diálogo normal do Notepad++.
- Workflow do GitHub Actions para compilar o plugin e empacotá-lo com a versão portátil x64 oficial mais recente do Notepad++.

## Limitações explícitas

- Este pacote é o **código-fonte e a receita de compilação**, não um executável já compilado. A compilação Windows ainda precisa ser executada pelo GitHub Actions.
- Não inclui WYSIWYG, alternância visual/código, imagens Base64 nem conversão de formatos.
- Imagens inseridas pela barra usam um caminho Markdown (`![descrição](imagem.png)`); o arquivo de imagem continua separado.
- A compatibilidade com Zettel Notes é esperada para Markdown comum, mas ainda precisa de teste real no aplicativo Android.
- A posição do painel depende do gerenciador de docking do Notepad++; pode ser necessário ajustá-la uma vez na interface.
- O workflow baixa a versão portátil oficial mais recente no momento da execução. O plugin é compilado para x64.

## Como gerar o ZIP portátil sem instalar ferramentas no computador

1. Crie um repositório no GitHub e envie para ele todos os arquivos desta pasta, mantendo a estrutura de diretórios.
2. Abra a aba **Actions** do repositório.
3. Selecione **Build Clara Markdown Portable** e clique em **Run workflow** (ou faça push de uma alteração nos arquivos acompanhados).
4. Aguarde a execução terminar com sucesso.
5. Na página da execução, em **Artifacts**, baixe `ClaraMarkdown-Portable-x64`.
6. Extraia o ZIP em uma pasta e execute `notepad++.exe`.
7. Se a barra não aparecer automaticamente, abra `Plugins > Clara Markdown > Mostrar/ocultar barra Markdown`.

## Estrutura esperada do plugin

`plugins/ClaraMarkdown/ClaraMarkdown.dll`

## Licença

O projeto segue GPL-3.0-or-later. Consulte `LICENSE` e os termos do Notepad++ original.
