# ATL::CComBSTR::operator=(ATL::CComBSTR const &)

- ea: `0x18002d680`
- end: `0x18002d6e2`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `98`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003f3e0`
- `0x18003f480`
- `0x180041200`
- `0x180041470`
- `0x180041630`
- `0x1800416d0`

## callees

- `0x18002d680`
- `0x180039524`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002d698`
- `OLEAUT32!__imp_SysFreeString` at `0x18002d698`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002d6c4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002d6c4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002d6cf`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002d6cf`

## pseudocode

```c
OLECHAR **__fastcall ATL::CComBSTR::operator=(OLECHAR **a1, BSTR *a2)
{
  OLECHAR *v4; // rcx
  BSTR v5; // rax
  UINT v7; // eax

  v4 = *a1;
  if ( v4 != *a2 )
  {
    SysFreeString(v4);
    if ( *a2 )
    {
      v7 = SysStringByteLen(*a2);
      v5 = SysAllocStringByteLen((LPCSTR)*a2, v7);
    }
    else
    {
      v5 = 0;
    }
    *a1 = v5;
    if ( *a2 && !v5 )
      ATL::PrivateAtlThrow(-2147024882);
  }
  return a1;
}

```

## disassembly

```asm
0x18002d680  mov     [rsp+arg_0], rbx
0x18002d685  push    rdi
0x18002d686  sub     rsp, 20h
0x18002d68a  mov     rdi, rcx
0x18002d68d  mov     rbx, rdx
0x18002d690  mov     rcx, [rcx]; bstrString
0x18002d693  cmp     rcx, [rdx]
0x18002d696  jz      short loc_18002D6B6
0x18002d698  call    cs:__imp_SysFreeString
0x18002d69e  mov     rcx, [rbx]; bstr
0x18002d6a1  test    rcx, rcx
0x18002d6a4  jnz     short loc_18002D6C4
0x18002d6a6  xor     eax, eax
0x18002d6a8  mov     [rdi], rax
0x18002d6ab  cmp     qword ptr [rbx], 0
0x18002d6af  jz      short loc_18002D6B6
0x18002d6b1  test    rax, rax
0x18002d6b4  jz      short loc_18002D6D7
0x18002d6b6  mov     rbx, [rsp+28h+arg_0]
0x18002d6bb  mov     rax, rdi
0x18002d6be  add     rsp, 20h
0x18002d6c2  pop     rdi
0x18002d6c3  retn
0x18002d6c4  call    cs:__imp_SysStringByteLen
0x18002d6ca  mov     rcx, [rbx]; psz
0x18002d6cd  mov     edx, eax; len
0x18002d6cf  call    cs:__imp_SysAllocStringByteLen
0x18002d6d5  jmp     short loc_18002D6A8
0x18002d6d7  mov     ecx, 8007000Eh; int
0x18002d6dc  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
