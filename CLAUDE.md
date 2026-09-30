## Matriz de modelos

| Etapa | Modelo | Confronta código |
|---|---|---|
| Levantamento | Fable | Sim |
| Plano e spec | Sonnet | Não, usa o briefing |
| Validação do plano | Opus | Sim |
| Execução | Sonnet | Não |
| Validação da entrega | Fable | Sim |

Nenhum modelo valida o que ele mesmo escreveu.

Escopo obrigatório: Fable e Opus recebem apenas os arquivos do
escopo mais o contrato do módulo, nunca o repositório inteiro.
A validação da entrega olha o diff e a saída dos testes.

Briefing com mais de 24 horas ou com commits no meio é refeito,
não reaproveitado.

Fluxo curto, para bug pequeno e correção óbvia: Sonnet escreve
o teste que reproduz, corrige, e o Fable valida apenas os
bloqueadores. Duas etapas.

### Checklist bloqueador (100 por cento, sem exceção)

Cada linha exige arquivo ou teste que comprove.

1. Contrato do módulo intacto, nenhuma assinatura pública
   alterada sem versionamento
2. Isolamento de dados entre clientes preservado, nenhuma
   consulta sem o filtro que o separa
3. Existe teste que falha sem a mudança e passa com ela
4. Migração reversível, nenhuma operação destrutiva sem
   rollback
5. Nenhum arquivo fora do escopo declarado foi tocado

### Checklist de qualidade (mínimo 80 por cento)

1. Caminho de erro coberto por teste
2. Sem duplicação de lógica já existente no módulo
3. Nomes e padrões seguindo o projeto
4. Sem TODO e sem código morto
5. Teste de navegador cobrindo o fluxo principal, quando houver
   interface

### Formato do veredito

Item, aprovado ou reprovado, arquivo ou teste que comprova, uma
linha de justificativa. Percentual apenas ao final e apenas
como sinal de alerta. O portão é o binário. Item que não pode
ser respondido com sim ou não está grande demais e deve ser
quebrado.
