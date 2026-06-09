# WriteAspnetDllOnOneScriptMap(IMSAdminBaseW *,ulong,ushort const *,ushort const *)

- ea: `0x1800361d0`
- end: `0x18003636a`
- name: `?WriteAspnetDllOnOneScriptMap@@YAJPEAUIMSAdminBaseW@@KPEBG1@Z`
- size: `410`
- prototype: `int(struct IMSAdminBaseW *, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18003422c`

## callees

- `0x180002584`
- `0x180007824`
- `0x18001c338`
- `0x180033afc`
- `0x1800361d0`
- `0x18004d754`
- `0x18004d7d4`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180036244`
- `KERNEL32!lstrlenW` at `0x18003624f`
- `KERNEL32!lstrlenW` at `0x18003625a`
- `KERNEL32!lstrlenW` at `0x180036266`
- `KERNEL32!lstrlenW` at `0x180036244`
- `KERNEL32!lstrlenW` at `0x18003624f`
- `KERNEL32!lstrlenW` at `0x18003625a`
- `KERNEL32!lstrlenW` at `0x180036266`

## string_xrefs

- `0x18003622d`: `,PUT,DELETE`

## pseudocode

```c

```
