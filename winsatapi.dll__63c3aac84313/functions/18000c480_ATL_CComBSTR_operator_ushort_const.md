# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x18000c480`
- end: `0x18000c4d6`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `86`
- prototype: `OLECHAR **__fastcall(OLECHAR **, const OLECHAR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c60`
- `0x18001e970`
- `0x18002d0c0`

## callees

- `0x18000c480`
- `0x1800171e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c4a6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c4a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c498`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c498`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        ATL::AtlThrowImpl(-2147024882);
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
0x18000c480  mov     [rsp+arg_0], rbx
0x18000c485  push    rdi
0x18000c486  sub     rsp, 20h
0x18000c48a  mov     rbx, rcx
0x18000c48d  mov     rdi, rdx
0x18000c490  mov     rcx, [rcx]; bstrString
0x18000c493  cmp     rdx, rcx
0x18000c496  jz      short loc_18000C4B4
0x18000c498  call    cs:__imp_SysFreeString
0x18000c49e  test    rdi, rdi
0x18000c4a1  jz      short loc_18000C4C2
0x18000c4a3  mov     rcx, rdi; psz
0x18000c4a6  call    cs:__imp_SysAllocString
0x18000c4ac  mov     [rbx], rax
0x18000c4af  test    rax, rax
0x18000c4b2  jz      short loc_18000C4CB
0x18000c4b4  mov     rax, rbx
0x18000c4b7  mov     rbx, [rsp+28h+arg_0]
0x18000c4bc  add     rsp, 20h
0x18000c4c0  pop     rdi
0x18000c4c1  retn
0x18000c4c2  mov     qword ptr [rbx], 0
0x18000c4c9  jmp     short loc_18000C4B4
0x18000c4cb  mov     ecx, 8007000Eh; int
0x18000c4d0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
