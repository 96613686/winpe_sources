# GetDllPathFromScriptMaps(IMSAdminBaseW *,ulong,ushort *,ushort * *)

- ea: `0x1800272a0`
- end: `0x18002739d`
- name: `?GetDllPathFromScriptMaps@@YAJPEAUIMSAdminBaseW@@KPEAGPEAPEAG@Z`
- size: `253`
- prototype: `__int64 __fastcall(struct IMSAdminBaseW *, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180027028`
- `0x1800274a0`
- `0x180027ae0`

## callees

- `0x1800272a0`
- `0x1800350e0`
- `0x18004d754`
- `0x18004e168`
- `0x18004e5a8`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800272ec`
- `KERNEL32!lstrlenW` at `0x1800272ec`
- `ucrtbase_clr0400!wcstok_s` at `0x180027323`
- `ucrtbase_clr0400!wcstok_s` at `0x18002733f`
- `ucrtbase_clr0400!wcstok_s` at `0x180027323`
- `ucrtbase_clr0400!wcstok_s` at `0x18002733f`

## string_xrefs

- `0x1800272f2`: `aspnet_isapi.dll`

## pseudocode

```c

```
