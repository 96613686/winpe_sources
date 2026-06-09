# IsSASRequired(_WLSM_GLOBAL_CONTEXT *)

- ea: `0x1400160c4`
- end: `0x14001627c`
- name: `?IsSASRequired@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(struct _WLSM_GLOBAL_CONTEXT *)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140011490`
- `0x140015ba0`
- `0x14001a618`
- `0x1400516a0`
- `0x1400625d0`
- `0x140062e20`
- `0x1400858e0`

## callees

- `0x1400160c4`
- `0x14002e100`
- `0x140037740`
- `0x140037b00`
- `0x140041c34`
- `0x14004effc`
- `0x140056348`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016218`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016218`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016252`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140016252`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001625d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001625d`
- `ntdll!RtlGetNtProductType` at `0x1400161ca`
- `ntdll!RtlGetNtProductType` at `0x1400161ca`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x14001614a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x14001614a`

## pseudocode

```c

```
