# UnEncryptPassword(ushort *,ulong)

- ea: `0x180020dcc`
- end: `0x180020f56`
- name: `?UnEncryptPassword@@YAXPEAGK@Z`
- size: `394`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001ffc4`

## callees

- `0x180013690`
- `0x180020dcc`
- `0x180045f80`
- `0x18004d350`
- `0x1800653ba`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180020e2e`
- `KERNEL32!lstrlenW` at `0x180020ebc`
- `KERNEL32!lstrlenW` at `0x180020e2e`
- `KERNEL32!lstrlenW` at `0x180020ebc`
- `KERNEL32!LocalFree` at `0x180020f32`
- `KERNEL32!LocalFree` at `0x180020f32`
- `ucrtbase_clr0400!_wcsicmp` at `0x180020e59`
- `ucrtbase_clr0400!_wcsicmp` at `0x180020e59`
- `CRYPT32!CryptUnprotectData` at `0x180020ef3`
- `CRYPT32!CryptUnprotectData` at `0x180020ef3`

## string_xrefs

- `0x180020e47`: `registry`
- `0x180020eab`: `ASP.NET Password from Machine.config file entropy`

## pseudocode

```c

```
