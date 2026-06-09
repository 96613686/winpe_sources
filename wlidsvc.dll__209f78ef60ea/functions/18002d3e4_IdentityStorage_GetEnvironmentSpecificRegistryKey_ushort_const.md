# IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)

- ea: `0x18002d3e4`
- end: `0x18002d6d3`
- name: `?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z`
- size: `751`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180072a74`
- `0x18010d5a8`
- `0x18010d764`
- `0x18010dca0`

## callees

- `0x18000ed04`
- `0x180013fb4`
- `0x180015860`
- `0x180019690`
- `0x18001ad00`
- `0x18001b050`
- `0x18002cf1c`
- `0x18002d36c`
- `0x18002d3e4`
- `0x18004afcc`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002d679`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002d679`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d557`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d557`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d691`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002d691`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d465`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d465`

## string_xrefs

- `0x18002d5b5`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x18002d5e3`: `onecoreuap\ds\ext\live\identity\lib\utilitieslite\registryhelper.cpp`
- `0x18002d428`: `IdentityStorage::GetEnvironmentSpecificRegistryKey`
- `0x18002d67f`: `IdentityStorage::GetEnvironmentSpecificRegistryKey`
- `0x18002d64d`: `Reading current environment failed, using production as default`
- `0x18002d4ed`: `ServiceEnvironment`

## pseudocode

```c

```
