# MigrateStoredPasswords(IServiceExecutionContext *,HKEY__ *)

- ea: `0x1800436c0`
- end: `0x180043baf`
- name: `?MigrateStoredPasswords@@YAXPEAVIServiceExecutionContext@@PEAUHKEY__@@@Z`
- size: `1263`
- prototype: `void __fastcall(struct IServiceExecutionContext *, HKEY)`
- caller_count: `2`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180078a50`
- `0x1800bb090`

## callees

- `0x18000a354`
- `0x18000a36c`
- `0x18000ed04`
- `0x180013fb4`
- `0x1800143a4`
- `0x1800151c4`
- `0x180015860`
- `0x1800172e0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18002b370`
- `0x18003a398`
- `0x1800436c0`
- `0x1800793b4`
- `0x1800841b0`
- `0x18009e718`
- `0x1800a3b60`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043917`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043917`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180043998`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180043998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043a2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043aab`

## string_xrefs

- `0x18004375b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\migratepasswords.cpp`
- `0x18004384d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\migratepasswords.cpp`
- `0x180043a73`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\migratepasswords.cpp`
- `0x180043aed`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\migratepasswords.cpp`
- `0x180043a66`: `CredDeleteW: failed with hr=0x%x`
- `0x180043b26`: `UpdateDone`

## pseudocode

```c

```
