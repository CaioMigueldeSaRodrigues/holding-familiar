# Holding Familiar — Dashboard Financeiro

Dashboard gerencial multiempresa, executável localmente no navegador, sem dependências externas.

## Como visualizar

1. Abra `index.html` no navegador.
2. Clique em **Importar dados** e selecione seu arquivo JSON privado de movimentações.
3. Navegue por **Consolidado**, **Realiza Gestão**, **Premium Locação**, **Atual Serviços Marítimos**, **Cardenes Participações**, **Serviços prestados** e **Qualidade dos dados**.
4. Filtre por mês e empresa; exporte apenas os registros necessários para CSV.

### Privacidade

**Este repositório é público e não contém os dados reais das empresas.** Nunca publique aqui arquivos bancários, nomes de colaboradores, planilhas de fluxo, dados JSON privados, CSVs de movimentações, informações bancárias ou credenciais. A amostra executiva gerada a partir das planilhas é distribuída **apenas por canal privado**, separadamente do código deste repositório.

O painel funciona no próprio navegador e não envia automaticamente o arquivo JSON selecionado a nenhum servidor. Para produção, será necessário implementar autenticação, autorização por CNPJ, dados criptografados, auditoria e infraestrutura privada.

### Fonte de dados

O JSON privado deve seguir o formato:

```json
{
  "transactions": [
    {"company":"realiza","period":"2026-01","date":"2026-01-15","category":"Receita operacional","group":"Receitas operacionais","description":"Cliente exemplo","direction":"entrada","amount":100,"nature":"operacional","source":"JANEIRO","row":7}
  ],
  "services": [],
  "anomalies": []
}
```

O trecho acima é apenas um **exemplo de formato** (dados fictícios, não usado como informação financeira). A versão privada do dashboard é abastecida exclusivamente com as planilhas fornecidas e destaca pendências de conciliação.

### Limites da versão de diagnóstico

- Apenas registros identificáveis das fontes foram contabilizados; números **não equivalem a DRE, contabilidade ou saldo bancário conciliado**.
- A aba Premium no arquivo Realiza não deve ser somada novamente à planilha Premium.
- Transferências internas, aportes e financiamentos precisam ser conciliados antes de uma consolidação contábil.
- Cardenes Participações precisa de fluxo próprio para indicadores completos.
- Dados comerciais de serviços não são somados ao caixa bancário.
