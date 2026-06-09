# GetDebuggerInfoForUser(void *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x180011258`
- end: `0x1800116b4`
- name: `?GetDebuggerInfoForUser@@YAJPEAXPEBG11PEAPEAG2@Z`
- size: `1116`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010e04`

## callees

- `0x18000c3f8`
- `0x18000ce5c`
- `0x18001037c`
- `0x180011258`
- `0x180012e64`
- `0x180012eb4`
- `0x1800210f8`
- `0x180025088`
- `0x180072c6c`
- `0x180089758`
- `0x180095c0c`
- `0x18009e160`
- `0x1800b7ac0`
- `0x1800cc71c`
- `0x1800cc878`
- `0x18010171c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180011322`
- `ntdll!RtlInitUnicodeString` at `0x180011322`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001144e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011469`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011484`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001149f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001144e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011469`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011484`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001149f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800112c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800112c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800113b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800113c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800113fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800113b2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800113c8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800113fa`

## string_xrefs

- `0x1800112d9`: `\REGISTRY\User\%s\Software\Classes\PackagesDebug`
- `0x1800113dd`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180011433`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180011503`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800115d1`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x180011655`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x1800115a7`: `DebugPath`

## pseudocode

```c

```
