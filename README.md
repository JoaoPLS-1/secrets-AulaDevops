# Secrets - Aula DevOps

Atividade para verificar o mascaramento de uma secret pelo GitHub Actions.

A secret `CHAVE_MESTRA` fica em **Settings > Secrets and variables > Actions**.
Seu valor fica armazenado no GitHub e nao deve ser incluido nos arquivos ou commits.

O workflow `.github/workflows/verificar-secret.yml` executa em pushes para `main`
e tambem pode ser iniciado em **Actions > Verificar protecao da secret > Run workflow**.
Ele verifica se a secret esta preenchida e usa `echo` para imprimir seu valor.

Para conferir o resultado, abra a execucao em **Actions**, selecione o job
**Exibir secret com mascaramento** e abra **Validar e exibir CHAVE_MESTRA**.
A linha esperada no log disponibilizado pelo GitHub e:

```text
CHAVE_MESTRA=***
```

O mascaramento e aplicado pelo GitHub ao publicar o log. A verificacao deve ser
feita no log da execucao; o processo no runner ainda recebe o valor original.
