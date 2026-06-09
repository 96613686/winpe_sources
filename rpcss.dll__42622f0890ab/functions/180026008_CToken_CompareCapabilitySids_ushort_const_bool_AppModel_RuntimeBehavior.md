# CToken::CompareCapabilitySids(ushort const *,bool,AppModel::RuntimeBehavior)

- ea: `0x180026008`
- end: `0x18002621b`
- name: `?CompareCapabilitySids@CToken@@QEAAJPEBG_NW4RuntimeBehavior@AppModel@@@Z`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024e48`

## callees

- `0x180026008`
- `0x180034540`
- `0x18006145c`
- `0x18007e3d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026116`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002605d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002610c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002605d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002610c`
- `KERNELBASE!LocalAlloc` at `0x1800260db`
- `KERNELBASE!LocalAlloc` at `0x1800260db`
- `KERNELBASE!AppXGetPackageCapabilities` at `0x18002618d`
- `KERNELBASE!AppXGetPackageCapabilities` at `0x18002618d`
- `KERNELBASE!AppXFreeMemory` at `0x180026202`
- `KERNELBASE!AppXFreeMemory` at `0x180026202`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800261f3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800261f3`

## string_xrefs

- `0x1800260c5`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180026170`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800260be`: `CToken::CompareCapabilitySids`
- `0x180026169`: `CToken::CompareCapabilitySids`

## pseudocode

```c

```
