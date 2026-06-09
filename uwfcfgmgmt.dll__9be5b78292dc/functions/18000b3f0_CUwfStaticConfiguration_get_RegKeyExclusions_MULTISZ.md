# CUwfStaticConfiguration::get_RegKeyExclusions(_MULTISZ * *)

- ea: `0x18000b3f0`
- end: `0x18000b41b`
- name: `?get_RegKeyExclusions@CUwfStaticConfiguration@@QEAAJPEAPEAU_MULTISZ@@@Z`
- size: `43`
- prototype: `int __fastcall(CUwfStaticConfiguration *this, struct _MULTISZ **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000b3f0`
- `0x18000e170`

## string_xrefs

- `0x18000b40a`: `RegistryExceptionsUserDefined`

## pseudocode

```c
int __fastcall CUwfStaticConfiguration::get_RegKeyExclusions(CUwfStaticConfiguration *this, struct _MULTISZ **a2)
{
  if ( a2 )
    return CUwfRegKey::QueryMultiSzValue(
             (CUwfStaticConfiguration *)((char *)this + 16),
             L"RegistryExceptionsUserDefined",
             a2);
  else
    return -2147467261;
}

```

## disassembly

```asm
0x18000b3f0  sub     rsp, 28h
0x18000b3f4  test    rdx, rdx
0x18000b3f7  jnz     short loc_18000B403
0x18000b3f9  mov     eax, 80004003h
0x18000b3fe  add     rsp, 28h
0x18000b402  retn
0x18000b403  mov     r8, rdx; struct _MULTISZ **
0x18000b406  add     rcx, 10h; this
0x18000b40a  lea     rdx, aRegistryexcept_0; "RegistryExceptionsUserDefined"
0x18000b411  call    ?QueryMultiSzValue@CUwfRegKey@@QEAAJPEBGPEAPEAU_MULTISZ@@@Z; CUwfRegKey::QueryMultiSzValue(ushort const *,_MULTISZ * *)
0x18000b416  add     rsp, 28h
0x18000b41a  retn
```
