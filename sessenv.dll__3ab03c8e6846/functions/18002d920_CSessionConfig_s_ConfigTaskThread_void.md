# CSessionConfig::s_ConfigTaskThread(void *)

- ea: `0x18002d920`
- end: `0x18002d9a5`
- name: `?s_ConfigTaskThread@CSessionConfig@@CAKPEAX@Z`
- size: `133`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003f30`
- `0x18002c890`
- `0x18002d920`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d940`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002d940`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d992`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002d992`

## string_xrefs

- `0x18002d94c`: `CSessionConfig::s_ConfigTaskThread`
- `0x18002d977`: `CSessionConfig::s_ConfigTaskThread`
- `0x18002d981`: `ConfigTaskThread failed: 0x%x in %s`

## pseudocode

```c

```
