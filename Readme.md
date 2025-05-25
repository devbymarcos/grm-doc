## Estrutura do JSON de Formulário Dinâmico

| Propriedade | Descrição                                                                           |
| ----------- | ----------------------------------------------------------------------------------- |
| `section`   | Título da seção do formulário. Agrupa os campos logicamente. Ex: "Status e Dados".  |
| `fields`    | Lista de campos que pertencem à seção. Cada item representa um campo do formulário. |

## Estrutura dos campos (fields)

| Propriedade | Tipo     | Obrigatório | Descrição                                                                  |
| ----------- | -------- | ----------- | -------------------------------------------------------------------------- |
| `name`      | `string` | Sim         | Identificador único do campo. Usado para manipulação de dados.             |
| `label`     | `string` | Sim         | Texto que será exibido como rótulo no formulário.                          |
| `type`      | `string` | Sim         | Tipo do campo. Pode ser: `text`, `select`, `textArea` (com "A" maiúsculo). |
| `options`   | `array`  | Condicional | Lista de opções, obrigatório quando `type` for `select`.                   |

## Exemplo da Estrutura

```{
  "section": "Status e Dados",
  "fields": [
    {
      "name": "funcionamento",
      "label": "Funcionamento",
      "type": "select",
      "options": ["Em plena operação", "Em operação parcial", "Desligado ou desativado"]
    },
    {
      "name": "marcaRep",
      "label": "Marca do Relógio",
      "type": "select",
      "options": ["Madis", "Proveu", "ControlID"]
    },
    {
      "name": "modelo",
      "label": "Modelo",
      "type": "text"
    }
  ]
}
```


## Estrutura do JSON de Template

| Propriedade | Tipo     | Obrigatório | Descrição                                                                                              |
| ----------- | -------- | ----------- | ------------------------------------------------------------------------------------------------------ |
| `title`     | `string` | Sim         | Título da seção do template, que geralmente aparece como cabeçalho.                                    |
| `fields`    | `array`  | Sim         | Lista de campos que serão exibidos na seção do template. Cada campo é um objeto com `label` e `value`. |


## Estrutura dos campos em fields

| Propriedade | Tipo     | Obrigatório | Descrição                                                                                          |
| ----------- | -------- | ----------- | -------------------------------------------------------------------------------------------------- |
| `label`     | `string` | Sim         | Texto exibido para descrever o campo na interface (rótulo).                                        |
| `value`     | `string` | Sim         | Valor dinâmico que será exibido no campo, geralmente usando placeholders `{{}}` para substituição. |


```
{
  "title": "DADOS E STATUS",
  "fields": [
    { "label": "Estado de Funcionamento", "value": "{{funcionamento}}" },
    { "label": "Marca do Relógio", "value": "{{marcaRep}}" },
    { "label": "Modelo", "value": "{{modelo}}" }
  ]
}


```

