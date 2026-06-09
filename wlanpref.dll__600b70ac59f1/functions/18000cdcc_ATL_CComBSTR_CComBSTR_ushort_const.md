# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x18000cdcc`
- end: `0x18000ce02`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000eea0`
- `0x180023550`
- `0x1800262e4`
- `0x18002a410`
- `0x18002c1d0`
- `0x18002c458`
- `0x18002c8a8`
- `0x18002d3f0`
- `0x18002d458`
- `0x18002d520`

## callees

- `0x1800054a0`
- `0x18000cdcc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000cde9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cde9`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  BSTR v4; // rax

  if ( a2 )
  {
    v4 = SysAllocString(a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    *(_QWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18000cdcc  push    rbx
0x18000cdce  sub     rsp, 20h
0x18000cdd2  mov     rbx, rcx
0x18000cdd5  test    rdx, rdx
0x18000cdd8  jnz     short loc_18000CDE6
0x18000cdda  mov     [rcx], rdx
0x18000cddd  mov     rax, rbx
0x18000cde0  add     rsp, 20h
0x18000cde4  pop     rbx
0x18000cde5  retn
0x18000cde6  mov     rcx, rdx; psz
0x18000cde9  call    cs:__imp_SysAllocString
0x18000cdef  mov     [rbx], rax
0x18000cdf2  test    rax, rax
0x18000cdf5  jnz     short loc_18000CDDD
0x18000cdf7  mov     ecx, 8007000Eh; int
0x18000cdfc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
