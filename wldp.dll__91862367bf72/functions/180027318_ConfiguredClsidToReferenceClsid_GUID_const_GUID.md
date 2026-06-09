# ConfiguredClsidToReferenceClsid(_GUID const &,_GUID *)

- ea: `0x180027318`
- end: `0x1800273c5`
- name: `?ConfiguredClsidToReferenceClsid@@YAJAEBU_GUID@@PEAU1@@Z`
- size: `173`
- prototype: `int __fastcall(GUID *guid, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800289a0`

## callees

- `0x180022a10`
- `0x180027318`

## import_xrefs

- `ntdll!RtlFindActivationContextSectionGuid` at `0x180027362`
- `ntdll!RtlFindActivationContextSectionGuid` at `0x180027362`

## pseudocode

```c

```
