# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x18001d79c`
- end: `0x18001d7d2`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `54`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e798`
- `0x18001fae0`
- `0x18001fd50`
- `0x18001fec0`
- `0x180020dcc`
- `0x180023a94`

## callees

- `0x1800171e0`
- `0x18001d79c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d7b9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d7b9`

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
0x18001d79c  push    rbx
0x18001d79e  sub     rsp, 20h
0x18001d7a2  mov     rbx, rcx
0x18001d7a5  test    rdx, rdx
0x18001d7a8  jnz     short loc_18001D7B6
0x18001d7aa  mov     [rcx], rdx
0x18001d7ad  mov     rax, rbx
0x18001d7b0  add     rsp, 20h
0x18001d7b4  pop     rbx
0x18001d7b5  retn
0x18001d7b6  mov     rcx, rdx; psz
0x18001d7b9  call    cs:__imp_SysAllocString
0x18001d7bf  mov     [rbx], rax
0x18001d7c2  test    rax, rax
0x18001d7c5  jnz     short loc_18001D7AD
0x18001d7c7  mov     ecx, 8007000Eh; int
0x18001d7cc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
