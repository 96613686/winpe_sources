# CToken::CompareCapabilitySids(ushort const *,bool,AppModel::RuntimeBehavior)

- ea: `0x180030490`
- end: `0x1800306d4`
- name: `?CompareCapabilitySids@CToken@@QEAAJPEBG_NW4RuntimeBehavior@AppModel@@@Z`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f160`

## callees

- `0x180030490`
- `0x180034260`
- `0x1800669a0`
- `0x18008172c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800304e5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800305a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800304e5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800305a6`
- `KERNELBASE!LocalAlloc` at `0x18003056f`
- `KERNELBASE!LocalAlloc` at `0x18003056f`
- `KERNELBASE!AppXGetPackageCapabilities` at `0x180030633`
- `KERNELBASE!AppXGetPackageCapabilities` at `0x180030633`
- `KERNELBASE!AppXFreeMemory` at `0x1800306b4`
- `KERNELBASE!AppXFreeMemory` at `0x1800306b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003069f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18003069f`

## string_xrefs

- `0x180030559`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180030616`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180030552`: `CToken::CompareCapabilitySids`
- `0x18003060f`: `CToken::CompareCapabilitySids`

## pseudocode

```c

```
