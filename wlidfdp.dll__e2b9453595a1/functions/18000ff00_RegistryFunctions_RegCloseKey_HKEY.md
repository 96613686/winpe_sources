# RegistryFunctions::RegCloseKey(HKEY__ *)

- ea: `0x18000ff00`
- end: `0x18000ff0a`
- name: `?RegCloseKey@RegistryFunctions@@UEAAJPEAUHKEY__@@@Z`
- size: `10`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff03`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegCloseKey(RegistryFunctions *this, HKEY a2)
{
  return RegCloseKey(a2);
}

```

## disassembly

```asm
0x18000ff00  mov     rcx, rdx
0x18000ff03  jmp     cs:__imp_RegCloseKey
```
