# ATL::IPersistPropertyBagImpl<CTDCCtl>::GetClassID(_GUID *)

- ea: `0x1800059a0`
- end: `0x1800059b9`
- name: `?GetClassID@?$IPersistPropertyBagImpl@VCTDCCtl@@@ATL@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800059a0`

## pseudocode

```c
__int64 __fastcall ATL::IPersistPropertyBagImpl<CTDCCtl>::GetClassID(__int64 a1, GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = CLSID_CTDCCtl;
  return result;
}

```

## disassembly

```asm
0x1800059a0  test    rdx, rdx
0x1800059a3  jnz     short loc_1800059AB
0x1800059a5  mov     eax, 80004003h
0x1800059aa  retn
0x1800059ab  movups  xmm0, xmmword ptr cs:CLSID_CTDCCtl.Data1
0x1800059b2  xor     eax, eax
0x1800059b4  movdqu  xmmword ptr [rdx], xmm0
0x1800059b8  retn
```
