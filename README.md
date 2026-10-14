# Nuvio Badges — Idiomas

Configuração comunitária de badges para streams no **NuvioDesktop**, com foco em identificar idiomas a partir do texto disponível nos resultados.

> **Status: experimental.** Este projeto não é oficial do Nuvio e não garante que o idioma será detectado em todos os provedores. As regras dependem dos campos de texto que o Nuvio disponibiliza ao mecanismo de badges.

## Arquivo principal

Use esta URL direta no Nuvio:

```text
https://raw.githubusercontent.com/queirozlm/nuvio-badges/main/GOLD-NONAMES-IDIOMAS.json
```

No NuvioDesktop, abra **Settings → Layout → Streams → Fusion Badge URLs**, adicione a URL e salve. O nome exato do menu pode variar entre versões.

## O que está incluído

O JSON mantém as regras de qualidade, resolução, vídeo, áudio e canais do pacote GOLD-NONAMES original e adiciona/ajusta regras de idioma para:

| Badge | Exemplos de termos reconhecidos |
|---|---|
| 🇧🇷 PT-BR | `PT-BR`, `POR-BR`, `Brazilian Portuguese`, `Português Brasil`, `Dublado BR` |
| 🇵🇹 POR | `POR`, `Portuguese`, `Português`, `PT-PT`, `PTG` |
| 🇬🇧 ENG | `ENG`, `English`, `EN-US`, `EN-GB` |
| 🇪🇸 ESP | `ESP`, `SPA`, `Spanish`, `Español`, alguns códigos regionais `ES` |
| 🇫🇷 FRA | `FRA`, `FRE`, `French`, `Français`, `FR-FR` |
| 🇩🇪 DEU | `GER`, `DEU`, `German`, `Deutsch`, `DE-DE` |
| 🌐 MULTI | `MULTI`, `DUAL`, `DUAL AUDIO`, `MULTI AUDIO` |

As expressões são heurísticas. Siglas curtas podem gerar falsos positivos ou não corresponder dependendo de como o título é escrito. As badges de idioma são etiquetas textuais; não são necessariamente imagens de bandeiras.

## Limitação importante: metadados do Torrentio

Alguns resultados mostram os idiomas em uma linha separada, por exemplo `Dual Audio / GB / PT / ES`, enquanto o nome do arquivo contém apenas `DUAL`. Se essa linha de idiomas não fizer parte do texto que o mecanismo de badges analisa, este JSON **não consegue ler esses metadados separados**. Nesse cenário, poderá aparecer a badge `MULTI`, mas não é possível deduzir com segurança todas as línguas do stream a partir de `DUAL` sozinho.

O comportamento precisa ser testado na versão do NuvioDesktop e com o provedor usado. Este repositório não altera o Torrentio nem extrai metadados de streams.

## Como testar

1. Adicione a URL direta do JSON nas configurações de Fusion Badge URLs.
2. Abra um título que tenha streams com idiomas explícitos no nome, como `PT-BR`, `ENG` ou `DUAL AUDIO`.
3. Compare a badge exibida com o nome completo do stream.
4. Se uma badge não aparecer, copie o nome exato do stream e abra uma issue com a versão do NuvioDesktop. Não inclua dados pessoais.

## Desenvolvimento e contribuições

- Mantenha o JSON válido.
- Preserve os grupos e as regras existentes de qualidade, resolução, vídeo, áudio e canais ao alterar os idiomas.
- Use padrões específicos e limites de palavra quando possível, para reduzir correspondências acidentais.
- Teste cada alteração com exemplos positivos e negativos.
- Não prometa a detecção de metadados que não estejam presentes no texto analisado pelo Nuvio.

Para relatar um problema ou sugerir uma melhoria, abra uma [issue](https://github.com/queirozlm/nuvio-badges/issues) descrevendo a versão do NuvioDesktop, a regra esperada e um exemplo de nome de stream.

## Créditos e escopo

Este projeto adapta regras para uso pessoal/comunitário e se baseia no formato de configuração de badges usado pelo Nuvio e no pacote GOLD-NONAMES de [k45sle/NUVIO_BADGES](https://github.com/k45sle/NUVIO_BADGES). Consulte o repositório de origem para créditos e licenciamento dos recursos originais. Este repositório não é afiliado nem endossado pelo Nuvio, Torrentio ou seus mantenedores.
