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
