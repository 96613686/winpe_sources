# ComputeService::Resources::DuplicateNetworkHandle(void *)

- ea: `0x1400fe9d0`
- end: `0x1400feae5`
- name: `?DuplicateNetworkHandle@Resources@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140261194`

## callees

- `0x140080180`
- `0x1400fe9d0`
- `0x1401332f0`
- `0x140134048`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400fea21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400fea21`
- `WS2_32!WSASocketW` at `0x1400fea87`
- `WS2_32!WSASocketW` at `0x1400fea87`
- `WS2_32!WSADuplicateSocketW` at `0x1400fea37`
- `WS2_32!WSADuplicateSocketW` at `0x1400fea37`

## string_xrefs

- `0x1400fea47`: `onecore\vm\compute\shared\computesystem\ServerResources.h`
- `0x1400feaac`: `onecore\vm\compute\shared\computesystem\ServerResources.h`

## pseudocode

```c

```
