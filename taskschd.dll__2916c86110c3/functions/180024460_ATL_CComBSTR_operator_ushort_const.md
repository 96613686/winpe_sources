# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x180024460`
- end: `0x1800244b6`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `86`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022e10`
- `0x1800231d0`
- `0x180024080`
- `0x180024140`
- `0x1800241e0`
- `0x180024280`
- `0x180024320`
- `0x1800243c0`
- `0x180034060`
- `0x18003a264`
- `0x18003f340`
- `0x18003f3e0`
- `0x18003f480`
- `0x18003f530`
- `0x18003f6e0`
- `0x180041170`
- `0x180041200`
- `0x1800412b0`
- `0x180041470`
- `0x180041510`
- `0x1800415a0`
- `0x180041630`
- `0x1800416d0`
- `0x180041770`
- `0x1800430c8`
- `0x180043154`
- `0x1800431d8`
- `0x18004325c`
- `0x1800432dc`
- `0x1800458f0`
- `0x180045c30`

## callees

- `0x180024460`
- `0x180039524`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180024486`
- `OLEAUT32!__imp_SysAllocString` at `0x180024486`
- `OLEAUT32!__imp_SysFreeString` at `0x180024478`
- `OLEAUT32!__imp_SysFreeString` at `0x180024478`

## pseudocode

```c
OLECHAR **__fastcall ATL::CComBSTR::operator=(OLECHAR **a1, const OLECHAR *a2)
{
  OLECHAR *v4; // rcx
  BSTR v5; // rax

  v4 = *a1;
  if ( a2 != v4 )
  {
    SysFreeString(v4);
    if ( a2 )
    {
      v5 = SysAllocString(a2);
      *a1 = v5;
      if ( !v5 )
        ATL::PrivateAtlThrow(-2147024882);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180024460  mov     [rsp+arg_0], rbx
0x180024465  push    rdi
0x180024466  sub     rsp, 20h
0x18002446a  mov     rbx, rcx
0x18002446d  mov     rdi, rdx
0x180024470  mov     rcx, [rcx]; bstrString
0x180024473  cmp     rdx, rcx
0x180024476  jz      short loc_180024494
0x180024478  call    cs:__imp_SysFreeString
0x18002447e  test    rdi, rdi
0x180024481  jz      short loc_1800244AD
0x180024483  mov     rcx, rdi; psz
0x180024486  call    cs:__imp_SysAllocString
0x18002448c  mov     [rbx], rax
0x18002448f  test    rax, rax
0x180024492  jz      short loc_1800244A2
0x180024494  mov     rax, rbx
0x180024497  mov     rbx, [rsp+28h+arg_0]
0x18002449c  add     rsp, 20h
0x1800244a0  pop     rdi
0x1800244a1  retn
0x1800244a2  mov     ecx, 8007000Eh; int
0x1800244a7  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1800244ad  mov     qword ptr [rbx], 0
0x1800244b4  jmp     short loc_180024494
```
