# DllMain

- ea: `0x180008cd0`
- end: `0x180008f0f`
- name: `DllMain`
- size: `575`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180053fa4`

## callees

- `0x180008cd0`
- `0x180008f18`
- `0x180008f50`
- `0x180008f78`
- `0x180008fb0`
- `0x180054130`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180008e3f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180008e3f`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008e94`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180008e94`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008ebb`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180008ebb`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180008e1e`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180008e1e`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180008edf`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180008edf`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180008d5d`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180008d5d`

## pseudocode

```c

```
