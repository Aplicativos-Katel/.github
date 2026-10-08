# Política de runners — Aplicativos-Katel

**Regra obrigatória para GitHub Actions deste repositório:** utilizar exclusivamente runners próprios (**self-hosted**) da organização.

- **Prioridade 1:** Windows, runner **MUQUITONA** (labels de SO: `self-hosted`, `Windows`, `X64`).
- **Prioridade 2:** Linux, runner **Katel-Linux** (labels: `self-hosted`, `Linux`, `X64`).
- **Fila:** quando os runners estiverem indisponíveis ou ocupados, aguardar em self-hosted; não executar automaticamente em runners hospedados pelo GitHub.
- **Proibido como fallback:** `ubuntu-latest`, `windows-latest`, `macos-latest` e outros GitHub-hosted.
- A preferência Windows → Linux exige seletor/dispatcher apropriado; uma lista simples em `runs-on` NÃO implementa fallback.
- Verificar compatibilidade de scripts, shells e ferramentas com cada sistema operacional antes de habilitar alternância.
- Não alterar, remover nem desativar builds e deploys existentes sem revisão.

**Esta política é documentação, não muda automaticamente os workflows existentes.** Para aplicar, revisar cada arquivo em `.github/workflows/` e testar o pipeline.
