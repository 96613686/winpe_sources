# EncryptPassword(ushort *)

- ea: `0x180020294`
- end: `0x180020462`
- name: `?EncryptPassword@@YAXPEAG@Z`
- size: `462`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180020f58`

## callees

- `0x180020294`
- `0x180026bfc`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`
- `0x1800653ba`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180020303`
- `KERNEL32!lstrlenW` at `0x18002033a`
- `KERNEL32!lstrlenW` at `0x180020358`
- `KERNEL32!lstrlenW` at `0x180020429`
- `KERNEL32!lstrlenW` at `0x180020303`
- `KERNEL32!lstrlenW` at `0x18002033a`
- `KERNEL32!lstrlenW` at `0x180020358`
- `KERNEL32!lstrlenW` at `0x180020429`
- `KERNEL32!LocalFree` at `0x180020446`
- `KERNEL32!LocalFree` at `0x180020446`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800202f2`
- `ucrtbase_clr0400!_wcsicmp` at `0x180020325`
- `ucrtbase_clr0400!_wcsicmp` at `0x1800202f2`
- `ucrtbase_clr0400!_wcsicmp` at `0x180020325`
- `CRYPT32!CryptProtectData` at `0x180020395`
- `CRYPT32!CryptProtectData` at `0x180020395`

## string_xrefs

- `0x180020317`: `registry`
- `0x180020340`: `ASP.NET Password from Machine.config file entropy`
- `0x18002036b`: `ASP.NET Password from Machine.config file`

## pseudocode

```c

```
