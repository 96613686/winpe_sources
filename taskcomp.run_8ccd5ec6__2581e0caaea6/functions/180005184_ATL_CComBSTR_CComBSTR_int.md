# ATL::CComBSTR::CComBSTR(int)

- ea: `0x180005184`
- end: `0x1800051be`
- name: `??0CComBSTR@ATL@@QEAA@H@Z`
- size: `58`
- prototype: `__int64 __fastcall(ATL::CComBSTR *__hidden this, int)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003cec`
- `0x180003fb8`
- `0x1800053e8`
- `0x180019f10`
- `0x18001a394`
- `0x18001bf80`
- `0x18001c3ac`

## callees

- `0x180005184`
- `0x18001c148`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800051a4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800051a4`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, UINT a2)
{
  BSTR v4; // rax
  int v5; // ecx

  if ( a2 )
  {
    v4 = SysAllocStringLen(0, a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::PrivateAtlThrow(v5);
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
0x180005184  push    rbx
0x180005186  sub     rsp, 20h
0x18000518a  mov     rbx, rcx
0x18000518d  test    edx, edx
0x18000518f  jnz     short loc_1800051A2
0x180005191  mov     qword ptr [rcx], 0
0x180005198  mov     rax, rbx
0x18000519b  add     rsp, 20h
0x18000519f  pop     rbx
0x1800051a0  retn
0x1800051a2  xor     ecx, ecx; strIn
0x1800051a4  call    cs:__imp_SysAllocStringLen
0x1800051ab  nop     dword ptr [rax+rax+00h]
0x1800051b0  mov     [rbx], rax
0x1800051b3  test    rax, rax
0x1800051b6  jnz     short loc_180005198
0x1800051b8  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
