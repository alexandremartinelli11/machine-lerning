# Template de Entrega


???+ info inline end "Edição"

    2025.1


## Entrega Individual 

1. [Alexandre Martinelli](https://github.com/alexandremartinelli11){:target='_blank'}


## Introdução
1. Exploração de dados: Ao selecionar uma base no [kagle](https://www.kaggle.com/datasets/uciml/red-wine-quality-cortez-et-al-2009){:target='_blank'} referentes a vinhos da marca Vinho Verde, contendo medições sobre a acidez fixa, acidez volatil, acidez citrica, açucar residual, cloretos, dioxido de enxofre livre e total, densidade, ph, sulfatos e qualidade (totalizando 12 colunas). 

### Colunas
    1 - fixed acidity (acidez fixa): Essa coluna é responsavel por medir os acidos de evaporação    lenta presentes no vinho, o tipo de dado dessa coluna é float/decimal. 
    2 - volatile acidity (acidez volatil):  

Use o [Mermaid](https://mermaid.js.org/intro/){:target='_blank'} para criar os diagramas de documentação.

[Mermaid Live Editor](https://mermaid.live/){:target='_blank'}


``` mermaid
flowchart TD
    Deployment:::orange -->|defines| ReplicaSet
    ReplicaSet -->|manages| pod((Pod))
    pod:::red -->|runs| Container
    Deployment -->|scales| pod
    Deployment -->|updates| pod

    Service:::orange -->|exposes| pod

    subgraph  
        ConfigMap:::orange
        Secret:::orange
    end

    ConfigMap --> Deployment
    Secret --> Deployment
    classDef red fill:#f55
    classDef orange fill:#ffa500
```



## Códigos

=== "De um arquivo remoto"

    ``` { .yaml .copy .select linenums='1' title="main.yaml" }
    --8<-- "https://raw.githubusercontent.com/hsandmann/documentation.template/refs/heads/main/.github/workflows/main.yaml"
    ```

=== "Anotações no código"

    ``` { .yaml title="compose.yaml" }
    name: app

        db:
            image: postgres:17
            environment:
                POSTGRES_DB: ${POSTGRES_DB:-projeto} # (1)!
                POSTGRES_USER: ${POSTGRES_USER:-projeto}
                POSTGRES_PASSWORD: ${POSTGRES_PASSWORD:-projeto}
            ports:
                - 5432:5432 #(2)!
    ```

    1.  Caso a variável de ambiente `POSTGRES_DB` não exista ou seja nula - não seja definida no arquivo `.env` - o valor padrão será `projeto`. Vide [documentação](https://docs.docker.com/reference/compose-file/interpolation/){target='_blank'}.

    2. Aqui é feito um túnel da porta 5432 do container do banco de dados para a porta 5432 do host (no caso localhost). Em um ambiente de produção, essa porta não deve ser exposta, pois ninguém de fora do compose deveria acessar o banco de dados diretamente.


## Exemplo de vídeo

Lorem ipsum dolor sit amet

<iframe width="100%" height="470" src="https://www.youtube.com/embed/3574AYQml8w" allowfullscreen></iframe>


## Referências

[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/reference/){:target='_blank'}