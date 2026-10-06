# Mapeamento dos Povos e Comunidades Tradicionais de Terreiro e de Matriz Africana de Alagoas

WebGIS para o mapeamento das casas de matriz africana e de religiosidade afro-indígena no estado de Alagoas.

> **Versão de teste.** O mapa reúne as primeiras 126 respostas do questionário de campo, com a pesquisa ainda em andamento. Os números mudam à medida que novos questionários forem incorporados.

**Realização:** Secretaria de Estado dos Direitos Humanos (SEDH – AL) e Universidade Estadual de Alagoas (UNEAL).

🔗 **Acesse:** https://SEU-USUARIO.github.io/terreiros-alagoas/

---

## O que o sistema faz

- Localiza cada terreiro em um mapa interativo, com agrupamento automático dos pontos próximos.
- Permite buscar por nome da casa, município, bairro ou modalidade religiosa.
- Filtra os registros em seis grupos: território, identidade religiosa, sede e infraestrutura, situação jurídica e do registro, ações sociais, e direitos e segurança.
- Gera três leituras analíticas — distribuição espacial, densidade e quantitativo por município — e permite colorir os pontos por modalidade, zona, situação da sede, racismo religioso, situação do registro ou precisão da localização.
- Apresenta estatísticas em cinco abas que acompanham os módulos do questionário: visão geral, sede e infraestrutura, pessoas, economia e ações, direitos e segurança.
- Abre, para cada terreiro, uma ficha completa com as respostas organizadas por módulo.
- Reúne a lista completa em tabela ordenável, com ligação direta ao ponto no mapa.
- Oferece formulário resumido para registro de casas ainda não mapeadas.

## Camadas disponíveis

| Camada | Conteúdo | Origem |
|---|---|---|
| Terreiros | Pontos dos registros | Levantamento de campo do projeto |
| Municípios de Alagoas | 102 limites municipais | Malha territorial do IBGE |
| Microrregiões de Alagoas | 13 microrregiões | Malha territorial do IBGE |
| Mesorregiões de Alagoas | 3 mesorregiões | Malha territorial do IBGE |
| Estados do Nordeste | 9 unidades federativas | Malha territorial do IBGE |
| Nomes dos municípios | Rótulos | Derivado da malha municipal |

Mapas base: Esri World Street Map (ruas) e Esri World Imagery (satélite). Ambos de uso livre, sem chave de acesso.

---

## Como funciona

Todo o sistema está em um único arquivo `index.html`. Não há servidor, banco de dados nem instalação: os dados geográficos e os registros estão embutidos no próprio arquivo, e todo o processamento acontece no navegador de quem acessa.

Isso significa que qualquer hospedagem de arquivos estáticos serve — GitHub Pages, um servidor da universidade ou até um pendrive.

**Bibliotecas usadas** (carregadas por CDN): Leaflet 1.9, Leaflet.markercluster 1.5 e Leaflet.heat 0.2.

---

## Publicação no GitHub Pages

1. Envie o `index.html` para a raiz do repositório.
2. Vá em **Settings → Pages**.
3. Em *Source*, escolha **Deploy from a branch**, com a branch `main` e a pasta `/ (root)`.
4. O endereço aparece na própria tela em um ou dois minutos.

O repositório precisa ser público para usar o GitHub Pages gratuito.

---

## Origem e tratamento dos dados

Os registros vêm do formulário do Google Forms aplicado pelas equipes de campo, organizado em cinco módulos: identificação do terreiro e da liderança; perfil socioeconômico dos participantes; representatividade e comunicação; potencial econômico e ações sociais; e perfil socioantropológico, que inclui território, segurança e racismo religioso.

Na conversão da planilha de respostas:

- os nomes de municípios foram padronizados contra a lista oficial do IBGE;
- as coordenadas foram lidas em graus decimais, graus-minutos-segundos, Plus Code e links do Google Maps, e conferidas contra o limite do município declarado;
- as respostas de múltipla escolha e os campos numéricos foram normalizados, e os casos ambíguos foram listados para conferência.

**Localização.** Terreiros sem coordenada legível aparecem numa posição aproximada dentro do município, com o marcador em anel tracejado. O filtro "Localização" e a opção "Precisão da localização" em "Colorir pontos por" mostram quais são.

**Situação do registro.** "Completo" indica que a resposta não tem pendências que afetem o mapa ou as estatísticas; "Com pendências" indica o contrário. A lista de pendências de cada registro aparece no topo da sua ficha.

## Privacidade

Não entram no WebGIS: nome civil, data e local de nascimento, endereço, telefone, e-mail, redes sociais pessoais, estado civil e orientação sexual da liderança, nem o endereço e o telefone do terreiro. A orientação sexual dos participantes aparece apenas nas estatísticas agregadas.

## Fotografias

As fotos das fachadas foram enviadas pelo formulário e ficam no Google Drive da pesquisa. O mapa tenta carregá-las de lá e, se não conseguir — pasta sem acesso público, arquivo removido ou mudança no serviço do Google —, mostra uma ilustração gerada pelo sistema, identificada como tal.

Para uma solução definitiva, independente do Drive, coloque as imagens numa pasta `fotos/` ao lado do `index.html`, em JPEG de cerca de 640×320 pixels, e ajuste a função `imagem(p)` no código para apontar para `fotos/${p.id}.jpg`.

---

## Dados sensíveis

A localização de casas de religião de matriz africana é informação sensível, e há histórico de perseguição a esses espaços em Alagoas. Antes de publicar coordenadas exatas:

- obtenha autorização escrita das lideranças, tanto para a localização quanto para o uso das imagens e a divulgação dos relatos de violência;
- considere publicar ponto aproximado ou agregação por município nos casos sem autorização;
- lembre que, em repositório público, o arquivo inteiro pode ser baixado — não apenas visualizado no mapa. Para dados restritos, mantenha uma versão separada em repositório privado, de acesso exclusivo da equipe.

---

## Créditos

Limites territoriais: Instituto Brasileiro de Geografia e Estatística (IBGE).
Mapas base: Esri, HERE, Garmin, INCREMENT P, Maxar, Earthstar Geographics e colaboradores do OpenStreetMap.

Secretaria de Estado dos Direitos Humanos de Alagoas (SEDH – AL)
Universidade Estadual de Alagoas (UNEAL) — *Ad sapientiam populi*
