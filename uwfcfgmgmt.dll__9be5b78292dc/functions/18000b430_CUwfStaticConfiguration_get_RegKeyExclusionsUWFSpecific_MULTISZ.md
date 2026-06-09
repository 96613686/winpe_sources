# CUwfStaticConfiguration::get_RegKeyExclusionsUWFSpecific(_MULTISZ * *)

- ea: `0x18000b430`
- end: `0x18000b443`
- name: `?get_RegKeyExclusionsUWFSpecific@CUwfStaticConfiguration@@QEAAJPEAPEAU_MULTISZ@@@Z`
- size: `19`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, struct _MULTISZ **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000e170`

## string_xrefs

- `0x18000b437`: `RegistryExceptionsUWFSpecific`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_RegKeyExclusionsUWFSpecific(
        CUwfStaticConfiguration *this,
        struct _MULTISZ **a2)
{
  return CUwfRegKey::QueryMultiSzValue(
           (CUwfStaticConfiguration *)((char *)this + 16),
           L"RegistryExceptionsUWFSpecific",
           a2);
}

```

## disassembly

```asm
0x18000b430  mov     r8, rdx; struct _MULTISZ **
0x18000b433  add     rcx, 10h; this
0x18000b437  lea     rdx, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x18000b43e  jmp     ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
```
