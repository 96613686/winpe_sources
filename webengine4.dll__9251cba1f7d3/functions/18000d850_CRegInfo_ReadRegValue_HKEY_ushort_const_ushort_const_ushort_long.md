# CRegInfo::ReadRegValue(HKEY__ *,ushort const *,ushort const *,ushort * *,long)

- ea: `0x18000d850`
- end: `0x18000d9ef`
- name: `?ReadRegValue@CRegInfo@@SAJPEAUHKEY__@@PEBG1PEAPEAGJ@Z`
- size: `415`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 **@<r9>, int)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c6c4`
- `0x18000c978`
- `0x18000d43c`
- `0x18000d794`
- `0x180035040`
- `0x18003f800`

## callees

- `0x180002584`
- `0x180007824`
- `0x18000d850`
- `0x18003abe4`
- `0x18003acd4`
- `0x18004d690`
- `0x18004d754`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18000d90f`
- `KERNEL32!lstrlenW` at `0x18000d91a`
- `KERNEL32!lstrlenW` at `0x18000d90f`
- `KERNEL32!lstrlenW` at `0x18000d91a`
- `ADVAPI32!RegQueryValueExW` at `0x18000d894`
- `ADVAPI32!RegQueryValueExW` at `0x18000d8e8`
- `ADVAPI32!RegQueryValueExW` at `0x18000d894`
- `ADVAPI32!RegQueryValueExW` at `0x18000d8e8`

## string_xrefs

- `0x18000d981`: `Reading the registry: `
- `0x18000d99c`: `Reading the registry: `
- `0x18000d988`: `CRegInfo::ReadRegValue`
- `0x18000d9a7`: `CRegInfo::ReadRegValue`

## pseudocode

```c

```
