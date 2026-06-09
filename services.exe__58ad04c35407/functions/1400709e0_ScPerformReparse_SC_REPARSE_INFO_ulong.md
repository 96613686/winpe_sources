# ScPerformReparse(_SC_REPARSE_INFO *,ulong)

- ea: `0x1400709e0`
- end: `0x140070e56`
- name: `?ScPerformReparse@@YAKPEAU_SC_REPARSE_INFO@@K@Z`
- size: `1142`
- prototype: `unsigned int __fastcall(struct _SC_REPARSE_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `22`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1400714d0`
- `0x1400717a0`

## callees

- `0x140002890`
- `0x1400037c8`
- `0x140003e54`
- `0x140004428`
- `0x140004c58`
- `0x140004c98`
- `0x140005824`
- `0x140007130`
- `0x1400108c0`
- `0x140011ba0`
- `0x140013f60`
- `0x140015020`
- `0x1400188fc`
- `0x140019014`
- `0x140024988`
- `0x14002a44c`
- `0x14002e930`
- `0x140043e64`
- `0x1400443d8`
- `0x1400709e0`
- `0x140073bb8`
- `0x14007bffc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140070b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140070b9b`
- `ntdll!RtlAcquireResourceExclusive` at `0x140070a21`
- `ntdll!RtlAcquireResourceExclusive` at `0x140070a21`
- `ntdll!RtlReleaseResource` at `0x140070d6f`
- `ntdll!RtlReleaseResource` at `0x140070d91`
- `ntdll!RtlReleaseResource` at `0x140070d6f`
- `ntdll!RtlReleaseResource` at `0x140070d91`

## pseudocode

```c

```
