# CCloudFileSystemApplier::ValidateReconcilable(IFspFile *,IFileConcurrencyBlob * *)

- ea: `0x180096628`
- end: `0x180096926`
- name: `?ValidateReconcilable@CCloudFileSystemApplier@@AEAAJPEAUIFspFile@@PEAPEAUIFileConcurrencyBlob@@@Z`
- size: `766`
- prototype: `int(CCloudFileSystemApplier *__hidden this, struct IFspFile *, struct IFileConcurrencyBlob **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180093800`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180011314`
- `0x180058d88`
- `0x180096628`
- `0x18009991c`
- `0x18009a0e0`
- `0x18009d66c`
- `0x1800bb594`
- `0x18013e010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18009687a`
- `KERNEL32!CompareFileTime` at `0x18009687a`
- `ntdll!NtClose` at `0x1800968e8`
- `ntdll!NtClose` at `0x1800968e8`

## pseudocode

```c

```
