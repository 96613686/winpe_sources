# SCRIPTMAP_REGISTER_MANAGER::FixForbiddenHandlerForV1(ASPNETVER *,ushort *)

- ea: `0x180034da8`
- end: `0x180034f5f`
- name: `?FixForbiddenHandlerForV1@SCRIPTMAP_REGISTER_MANAGER@@AEAAJPEAVASPNETVER@@PEAG@Z`
- size: `439`
- prototype: `int(SCRIPTMAP_REGISTER_MANAGER *__hidden this, struct ASPNETVER *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180033bd0`

## callees

- `0x180034da8`
- `0x18004d030`
- `0x18004f024`
- `0x18004f098`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180034e7d`
- `KERNEL32!lstrlenW` at `0x180034e94`
- `KERNEL32!lstrlenW` at `0x180034ebd`
- `KERNEL32!lstrlenW` at `0x180034e7d`
- `KERNEL32!lstrlenW` at `0x180034e94`
- `KERNEL32!lstrlenW` at `0x180034ebd`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180034ea3`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180034ea3`
- `ucrtbase_clr0400!wcsncmp` at `0x180034eef`
- `ucrtbase_clr0400!wcsncmp` at `0x180034f11`
- `ucrtbase_clr0400!wcsncmp` at `0x180034eef`
- `ucrtbase_clr0400!wcsncmp` at `0x180034f11`

## string_xrefs

- `0x180034e07`: `.config,`

## pseudocode

```c

```
