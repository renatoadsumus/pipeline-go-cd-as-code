# devops-gocd-pipelines-as-code
Repositório aonde estão presentes os códigos dos pipelines do GoCD e templates da sintaxe do pipeline as code do GoCD no formato JSON.

Todos os códigos JSON foram criados utilizando como base as diretrizes presentes no arquivo README.md do repositório https://github.com/tomzo/gocd-json-config-plugin.git

------------------------------------------------------------------------------------------------------------------------------------------
# UTILIZAÇÃO

Para utilizar os códigos do pipeline do GoCD, é necessário seguir as instruções de inserção da tag config-repos, como indicado em https://docs.gocd.org/current/advanced_usage/pipelines_as_code.html

O repositório de exemplo deve ser substituído por https://github.com/Infoglobo/devops-gocd-pipelines-as-code.git

------------------------------------------------------------------------------------------------------------------------------------------
# TEMPLATES E CRIAÇÃO DE NOVOS PIPELINES

O diretório de templates contém exemplos de códigos básicos para criação de novos pipelines.

Todos os pipelines devem ser criados com o seguinte formato de nome:

nome.do.pipeline.gocd.gopipeline.json

------------------------------------------------------------------------------------------------------------------------------------------
# GERAÇÃO DE SENHAS

Quando for necessário configurar senhas nos pipelines, é necessário passar essas senhas pela API do GoCD para que seja gerada a senha criptografada de acordo com a chave da instância do GoCD.

Para gerar essa senha criptograda, é necessário enviar uma requisição POST para o servidor do GoCD. O exemplo de requisição com curl é:

curl -k 'https://endereco_maquina:porta/go/api/admin/encrypt' -u 'username:password' -H 'Accept: application/vnd.go.cd.v1+json' -H 'Content-Type: application/json' -X POST -d '{"value": "VALOR_DA_SENHA"}'
