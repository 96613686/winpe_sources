# UnBCL::RegistryKey::GetValue(UnBCL::String const *)

- ea: `0x18004e120`
- end: `0x18004e1d8`
- name: `?GetValue@RegistryKey@UnBCL@@QEAAKPEBVString@2@@Z`
- size: `184`
- prototype: `unsigned int __fastcall(UnBCL::RegistryKey *__hidden this, const struct UnBCL::String *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000225c`
- `0x180009e7c`
- `0x1800477d0`
- `0x18004e120`
- `0x1800641a0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18004e16a`
- `ADVAPI32!RegQueryValueExW` at `0x18004e16a`

## string_xrefs

- `0x18004e1b2`: `unsigned long __cdecl UnBCL::RegistryKey::GetValue(const class UnBCL::String *)`

## pseudocode

```c

```
