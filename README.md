# thesispuc-alpha
 Thesis PUC com suporte para bibliografia alfanumérico

Esse é uma cópia do estilo de tese da PUC-Rio (disponível [aqui](http://www.puc-rio.br/ensinopesq/ccpg/apresentacao_ted.html)), mas com suporte para bibliografia no estilo sobrenome (ano) (ex.: Knuth (1984)), e mais umas pequenas alterações. 

## Como usar

Baixe esse estilo e use exatamente como o estilo da PUC.

## Bibliografia

Agora, no comando `\documentclass`, você deve escolher uma das duas opções (além das opções _master_ ou _phd_ e _brazilian_ ou _american_):

* _numeric_, para a bibliografia indexada por número
* _authordate_, para a bibliografia no estilo sobrenome (ano)

### Importante:

* **No caso de _authordate_, você tem que adicionar o pacote `natbib` (use a opção round para o ano em parênteses). No caso da opção _numeric_ você não pode usar o natbib.**

* **Em alguns sistemas, quando você trocar de numeric para authordate, você vai ter que apagar o arquivo `nome_da_tese.bbl` para o LaTeX atualizar a bibliografia**
 
## Exemplo

O exemplo Julio, do original, conta com duas versões agora: uma numérica e uma com o authordate

Só para ficar absolutamente claro: se você está fazendo uma tese de mestrado em inglês e quer a bibliografia no estilo sobrenome (ano), então o seu documento vai começar com:

```

\documentclass[american,master,authordate]{ThesisPUC}

\usepackage[round]{natbib}

```

No caso de bibliografia numérica:

```

\documentclass[american,master,numeric]{ThesisPUC}

```

## Outras alterações

Por algum motivo os ambientes de Teorema, Prova, estavam em português mesmo quando a tese estava com a opção `american`. Essa versão também resolve isso, mudando os nomes dos ambientes conforme a língua especificada.

## _Under the hood_

Basicamente tudo que foi feito é adicionar um \ifelsethen no arquivo de estilo (`ThesisPUC.cls`) onde tem o comando `\bibliographystyle`.

A segunda coisa (mais trabalhosa, mas mais fácil de reaproveitar), é o arquivo ThesisPUC2.bst. Esse arquivo define como o BibTeX escreve a bibliografia no arquivo. Ele é um tanto o quanto hermêtico, e se você quiser se entender com ele leia o [_Taming the BeaST_](http://tug.ctan.org/info/bibtex/tamethebeast/ttb_en.pdf) 

## Créditos e mais informações

[Veja a documentação original da PUC-Rio](http://www.puc-rio.br/ensinopesq/ccpg/download/ThesisPUC-1.0.11.pdf)

