### Objetivos da Comunidade Brasileira OpenMRS

- [ ] Integração Carol para triagem - https://carol.orango.io
- [x] tradução de O3 pt-br - https://explore.transifex.com/openmrs/openmrs3/ https://talk.openmrs.org/t/o3-translations/43737/18
- [ ] criação de formulários pt e arquivos de configurações - Hospitais (Emergência, Triagem e Enfermaria), Ambulatório de Mastologista e Atenção Básica
- [ ] Assinatura digital contato ICP - https://developers.integraicp.com.br/api-reference/icp/v3/index.html#/
- [ ] RNDS - https://rnds-guia.saude.gov.br/docs/introducao/
- [ ] dark mode - https://talk.openmrs.org/t/dark-mode-please/44104

# Instalação da Aplicação em para uso no Brasil (Docker)

## Realizar clone de repositório principal

```sh
git clone git@github.com:openmrs/openmrs-distro-referenceapplication.git
```

## Configurações iniciais

As configurações dos módulos estão disponíveis em `distro/configuration/` no qual cada pasta é um domínio com seus próprios recursos configuráveis. Todos os arquivos que contém `-core_demo` são dados de demosntração e você pode querer editá-los, por exemplo em `distro/configuration/locations/locations-core_demo.csv` para não ficar mostrando vários locais de atendimento que não existem em sua realidade.

As configurações de frontend podem ser encontradas em `forntend/config-core_demo.json`

## Rodar instalação

```sh
docker compose build
docker compose up -d
```

Após alguma mudança no json de configurações do forntend vocês precisa rodar os comandos abaixo e atualizar a página sem cache para aplicar as alterações:

```sh
docker compose build --no-cache frontend
docker compose up -d frontend
```

