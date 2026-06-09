# CUwfStaticConfiguration::set_RegKeyExclusionsUWFSpecific(_MULTISZ *)

- ea: `0x18000cd30`
- end: `0x18000cd5f`
- name: `?set_RegKeyExclusionsUWFSpecific@CUwfStaticConfiguration@@QEAAJPEAU_MULTISZ@@@Z`
- size: `47`
- prototype: `__int64 __fastcall(CUwfConfiguration **this, struct _MULTISZ *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000c680`
- `0x18000c960`

## callees

- `0x18000a240`

## string_xrefs

- `0x18000cd44`: `RegistryExceptionsUWFSpecific`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_RegKeyExclusionsUWFSpecific(
        CUwfConfiguration **this,
        struct _MULTISZ *a2)
{
  unsigned int updated; // ecx
  __int64 result; // rax

  updated = CUwfConfiguration::UpdateMultiSzValue(
              this[4],
              (struct CUwfRegKey *)(this + 2),
              L"RegistryExceptionsUWFSpecific",
              a2,
              1);
  result = 0;
  if ( updated != 1 )
    return updated;
  return result;
}

```

## disassembly

```asm
0x18000cd30  sub     rsp, 38h
0x18000cd34  mov     r9, rdx; struct _MULTISZ *
0x18000cd37  mov     [rsp+38h+var_18], 1; bool
0x18000cd3c  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000cd40  mov     rcx, [rcx+20h]; this
0x18000cd44  lea     r8, aRegistryexcept; "RegistryExceptionsUWFSpecific"
0x18000cd4b  call    ?UpdateMultiSzValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGQEAU_MULTISZ@@_N@Z; CUwfConfiguration::UpdateMultiSzValue(CUwfRegKey &,ushort const *,_MULTISZ * const,bool)
0x18000cd50  mov     ecx, eax
0x18000cd52  xor     eax, eax
0x18000cd54  cmp     ecx, 1
0x18000cd57  cmovnz  eax, ecx
0x18000cd5a  add     rsp, 38h
0x18000cd5e  retn
```
