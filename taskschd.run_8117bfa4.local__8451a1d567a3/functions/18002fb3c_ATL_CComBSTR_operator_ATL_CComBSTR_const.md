# ATL::CComBSTR::operator=(ATL::CComBSTR const &)

- ea: `0x18002fb3c`
- end: `0x18002fbb1`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `117`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800429a0`
- `0x180042a50`
- `0x180044900`
- `0x180044b90`
- `0x180044d70`
- `0x180044e20`

## callees

- `0x18002fb3c`
- `0x18003c664`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002fb54`
- `OLEAUT32!__imp_SysFreeString` at `0x18002fb54`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002fb87`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002fb87`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002fb98`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18002fb98`

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
0x18002fb3c  mov     [rsp+arg_0], rbx
0x18002fb41  push    rdi
0x18002fb42  sub     rsp, 20h
0x18002fb46  mov     rdi, rcx
0x18002fb49  mov     rbx, rdx
0x18002fb4c  mov     rcx, [rcx]; bstrString
0x18002fb4f  cmp     rcx, [rdx]
0x18002fb52  jz      short loc_18002FB78
0x18002fb54  call    cs:__imp_SysFreeString
0x18002fb5b  nop     dword ptr [rax+rax+00h]
0x18002fb60  mov     rcx, [rbx]; bstr
0x18002fb63  test    rcx, rcx
0x18002fb66  jnz     short loc_18002FB87
0x18002fb68  xor     eax, eax
0x18002fb6a  mov     [rdi], rax
0x18002fb6d  cmp     qword ptr [rbx], 0
0x18002fb71  jz      short loc_18002FB78
0x18002fb73  test    rax, rax
0x18002fb76  jz      short loc_18002FBA6
0x18002fb78  mov     rbx, [rsp+28h+arg_0]
0x18002fb7d  mov     rax, rdi
0x18002fb80  add     rsp, 20h
0x18002fb84  pop     rdi
0x18002fb85  retn
0x18002fb87  call    cs:__imp_SysStringByteLen
0x18002fb8e  nop     dword ptr [rax+rax+00h]
0x18002fb93  mov     rcx, [rbx]; psz
0x18002fb96  mov     edx, eax; len
0x18002fb98  call    cs:__imp_SysAllocStringByteLen
0x18002fb9f  nop     dword ptr [rax+rax+00h]
0x18002fba4  jmp     short loc_18002FB6A
0x18002fba6  mov     ecx, 8007000Eh; int
0x18002fbab  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
